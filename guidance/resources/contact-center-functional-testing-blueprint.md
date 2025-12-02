---
title: Functional Testing Guide for Dynamics 365 Contact Center
description: Optimize your Dynamics 365 Contact Center deployment with this blueprint for functional testing. Test voice, chat, and integrations for a reliable experience.
author: edupont04
ms.author: reedw
ms.reviewer: edupont
ms.date: 12/02/2025
ms.topic: concept-article
---

# Blueprint for functional testing of solutions with Dynamics 365 Contact Center with both voice and chat

This blueprint provides a structured approach to *functional testing* for an enterprise deployment of Dynamics 365 Contact Center with Voice and Chat channels. Functional testing ensures that your contact center solution meets business requirements and works end-to-end. In particular, it verifies that *customer interactions follow the intended flows*, that *agents have the necessary information and tools*, and that *the technical environment (telephony, network, devices, integrations)* supports a reliable experience.

The blueprint is organized into key test areas, each with common considerations and guiding questions to include in your test plan:

- **IVR setup and call flows** – Test the Interactive Voice Response (IVR) menus and call flow logic.
- **Call routing and queues** – Verify call distribution, queue behavior, and overflow handling.
- **Chat workflows** – Validate live chat initiation, bot hand-offs, and chat routing.
- **Agent desktop experience** – Ensure agents' interface, call controls, and data capture work properly.
- **Integration and environment** – Check network, hardware, telephony integration, and other system interfaces.

Each section in this article outlines the purpose of that test area and provides a checklist of questions and criteria to guide your testing strategy. Using these checklists, you can develop detailed test cases and expected outcomes for your organization's specific scenarios.

## IVR setup and voice call flows

The purpose of this step is to verify that the Interactive Voice Response (IVR) is configured correctly and guides callers through the expected options before reaching an agent. This verification includes greetings, menu prompts, input handling, and special scenarios such as after-hours calls.

- **Are the correct greetings and hold messages played to callers?**  

  Ensure the initial welcome greeting plays as configured. If a caller is placed on hold or in a queue, the correct music or announcement plays at the appropriate intervals. Test various call scenarios (normal business hours, hold in queue, call transfers) to confirm the caller hears the right messages.

- **Does the IVR accept and process inputs (DTMF or voice commands) correctly?**  

  Verify that the IVR detects when callers press keys on their phone or speak responses, and that IVR responds with the proper action. For example, if the menu says "Press 1 for Sales, 2 for Support," pressing 2 routes the call to the Support flow. Test both valid inputs and invalid inputs (or no input) and verify the IVR provides helpful error messages or repeats the prompt when needed.

- **Do all IVR menu options lead to the intended call paths?**  

  Walk through each IVR menu branch to confirm the call flow matches the design. For instance, if a caller selects the option for **Billing Support**, the IVR eventually transfers the call to the Billing support queue (and not somewhere else). If the IVR offers any self-service (like checking account balance via an automated voice bot), verify that those flows work end-to-end and allow the caller to reach an agent if needed.

- **Is the after-hours or holiday call behavior working as expected?**  

  Simulate calls outside of normal operating hours. The system recognizes off-hours and plays the designated closure message or offers alternatives (like voicemail or callback scheduling). Ensure that the correct off-hours greeting plays and that any voicemails are properly recorded and accessible to the team the next business day.

- **Are special scenarios (for example, emergencies or downtime) handled appropriately by the IVR?**  

  Check if there are contingency prompts for critical scenarios. For example, if a customer dials an emergency line (if your system has one) or if the contact center application is down, the IVR might bypass normal menus and play a special message (like "For emergencies, please dial 911" or "We're experiencing technical difficulties."). Verify that these scenarios trigger the correct IVR behavior.

- **If a post-call survey or feedback is enabled, is it triggered correctly?**  

  Many contact centers offer a survey at the end of a call. Confirm that once an agent disconnects, the call is transferred to the survey (or a text message is sent, depending on configuration). The survey only initiates under the right conditions (for example, not when the call was abandoned or dropped). If the survey is via IVR, test completing it; if via a different channel, ensure the handoff works (for example, the caller gets the SMS link).

> [!NOTE]
> Thorough IVR testing guarantees that callers are greeted properly, can navigate menus, and aren't left stuck due to a misconfigured prompt.

## Call routing and queue management

The purpose of this step is to make sure that incoming interactions route to the appropriate **queue or agent** based on your configuration, and that no calls or chats are lost. This step covers skill-based routing rules, queue wait logic, overflow conditions, and agent availability settings.

- **Do incoming calls route to the correct queues and agents with the right skills?**  

  Verify that your **unified routing** rules and **work classification** settings function correctly. For each test call or chat scenario, the interaction should land in the expected queue. From there, the system should assign it to an available agent who meets the skill or role requirements. For example, a call from a Spanish-speaking customer should be routed to an agent who speaks Spanish if that skill is configured. Use sample data to ensure every defined rule (language, product expertise, priority customers, and so on) results in the correct routing outcome.

- **What happens if an agent doesn't answer or no one is available?**  

  Simulate scenarios where calls or chats go unanswered. The system should follow the defined **overflow or timeout strategy**. For instance, if no agent picks up a call within 30 seconds, perhaps it returns to the queue or escalates to a backup team. If the chat queue is full, maybe a message tells the user to try again later or deflects to a bot. Ensure that unanswered interactions aren't dropped. Test that the next available agent receives the rerouted call, or that the customer gets a prompt to leave a voicemail or request a callback when appropriate.

- **Are calls or chats ever getting dropped or stuck during routing?**  

  Pay attention to any point in the routing process where a customer could be unintentionally disconnected. After the IVR transfers the call to a queue, the caller should remain on the line (hearing hold music or periodic messages) until an agent answers. If the contact center transfers between queues, the call should stay connected. No interaction should vanish without a trace from the customer perspective. Use call logs or monitoring tools to ensure every routed call has a clear outcome (answered, went to voicemail, and so on) and none terminate abruptly due to misrouting.

- **Does the routing logic respect agent presence, capacity, and skill priority?**  

  Verify that agents only receive calls or chats when they're marked **Available** (or whatever presence state indicates readiness in Dynamics 365 Contact Center). For voice, if an agent toggles to **Busy** or **Away**, new calls should skip them. For chat, if an agent already has the maximum number of chats allowed ([capacity set in the system](/dynamics365/customer-service/administer/capacity-profiles)), other chats should queue or go to other agents. Also, if your system uses agent **capacity units** or similar to handle mixed workloads (for example, a voice call might count as 100% capacity, so the agent shouldn't get another chat simultaneously unless configured otherwise), test those scenarios. The distribution engine should follow the configured workload capacity rules so agents aren't overwhelmed or idle incorrectly.

> [!NOTE]
> Effective routing tests ensure that every customer reaches the right agent or queue without error. The tests also verify that your business rules for prioritizing and distributing work are realized in practice.

## Chat workflows

The purpose of this step is to validate the end-to-end workflow for **live chat** interactions, from initiation on the customer side (web chat or other channel) through any bot engagement, queue routing, and agent handling. Ensure that chat conversations follow the expected path and that the system captures the interaction details.

- **Can customers initiate a chat and reach an agent through the intended path?**  

  Start a chat from the customer perspective (for example, via your website's chat widget or a messaging app). Check that the chat window loads and prompts the user correctly. If a bot is supposed to greet the user initially, verify the bot engages with the expected welcome message and dialog. If no bot is used, the chat request should go straight into the queue with an appropriate system greeting (like "Please wait for the next available agent…"). In either case, ensure that the transition from bot to human agent (or to queue waiting) happens as designed. For example, after a bot collects a customer's question and they ask for a human, the chat should transfer to a live agent queue seamlessly.

- **Is the chat virtual agent or self-service working as intended?**  

  If you implemented a chatbot for common inquiries, test its knowledge base and hand-off triggers. Ask the bot both simple questions (that it should answer on its own) and more complex ones. Confirm the bot answers where it can, and that it offers to connect to a human agent at the right time (based on confidence or customer request). When the bot does hand off to an agent, ensure it passes along context like the issue description or case number so the agent has that information. This test ensures that bot deflection is effective but not at the expense of user experience – customers should be able to seamlessly get to a person if needed, with their info carrying over.

- **Do live chat requests route to the correct team or agent group?**  

  As with voice, chat routing rules (workstream queue assignments, skills-based routing, etc.) need validation. If you have multiple chat queues (for example, Sales Chat vs. Support Chat, or different languages), initiate chats that should go to each and verify they end up in the right place. Additionally, if certain agents have higher skills or profile and should get certain chats first (priority routing), test that scenario. The unified routing engine in Dynamics 365 should create a **Conversation** record for the chat and assign it to an agent with matching skills who is available. Make sure parameters like agent capacity for concurrent chats are respected (for example, an agent set to handle up to two chats doesn't get a third one assigned).

- **Are chat interactions and customer data being captured correctly?**  

  Check that the platform logs the chat transcript and any related data. When a chat is complete, the full conversation should be available in the system (often attached to the Conversation record or a created Case). If your process is to create a support Case from each chat, verify that happens (either automatically via rules or manually by the agent). Also ensure the system records key events: chat start time, end time, agent name, customer info (like email if provided in pre-chat survey), and any classification (topic, sentiment, etc.). If the customer or agent uploads a file or image in the chat, confirm it's stored or linked properly. Essentially, your CRM should have a record of the chat just as it would for a phone call or email, so that nothing the customer said is lost.

- **Did you consider peak chat volumes and concurrency in your test plan?**  

  Because enterprise deployments might involve high volumes, it's important to include scenarios of multiple simultaneous chats. You might conduct a mini **load test** for chats: have several testers start chats around the same time, or use a tool to simulate 10+ concurrent chat sessions. Observe how the system handles the load – do all requests enter the queue properly? Do agents receive chats one after another without system lag? If the volume exceeds agent capacity, do chats remain queued (with users seeing appropriate wait messages)? While full performance testing might be separate, your functional test plan should at least validate that under normal peak conditions (for example, lunchtime surge with 50 chats in an hour), the chat channel works without errors or crashes. If any slowness or issues appear, note them so you can adjust configurations or environment (scaling up resources, etc.) before go-live.

> [!NOTE]
> By testing chat interactions thoroughly, you ensure digital channel customers get quick and correct responses, whether through AI or human service, and that every chat is accounted for in the system.

## Agent desktop experience

The purpose of this step is to confirm that customer service agents have a seamless experience handling voice calls and chats. When an interaction comes in, the agent's interface (for example, the Dynamics 365 Customer Service workspace) should display all relevant customer information and provide working controls for the agent to manage the conversation (hold, transfer, send chat replies, etc.). A positive agent experience is crucial for efficiency and customer satisfaction.

- **When a call or chat arrives, does the agent desktop show the necessary customer info and context?**  

  Emulate an incoming call to an agent and check what pops up on the agent's screen. The system should automatically display a **customer summary** (if the caller's number or chat ID is recognized and matched to a customer record) or prompt to create a new contact if it's unknown. Key information like the caller's name, contact history (recent cases or orders), and the IVR selections or reason for call (if passed along) should be readily visible. For chats, if the user filled a pre-chat form (name, account number, etc.) or if a bot gathered some details, those should be shown to the agent. Essentially, the agent shouldn't have to search manually for who the customer is or why they're contacting. Instead, the system should present that context as the session starts.

- **Does the system create and link the proper records (Interactions, Cases) for each conversation?**  

  In Dynamics 365 Contact Center, voice calls and chats are typically tracked as **Conversation** records or activities. Ensure that for each test call or chat, a conversation record is created logging the interaction. If your process requires a support Case to be created for each issue, verify that agents can easily create one (or that it auto-creates) and that it links to the ongoing conversation. If the conversation should be associated with an existing Case or Account, test that the agent can search and link it on the fly. After the call/chat ends, the transcripts, call recording, and agent's notes should all be saved in the system, attached to the conversation and/or case. This is important for after-call follow-up and reporting.

- **Can the agent use all voice call controls (hold, mute, consult, transfer, etc.) without issues?**  

  While on a test call, have the agent exercise each available function as described in the following table.

  |Function  |Description |
  |---------|---------|
  |**Hold** | The agent puts the call on hold and the caller hears the hold music or message. (Confirm the agent's interface indicates the call is on hold, and then take the caller off hold to resume the conversation.) Learn more at [Use agent dashboard and call controls in the voice channel](/dynamics365/contact-center/use/voice-channel-agent-experience).|
  |**Consult/Transfer** |The agent starts a consultation to conference or transfer the call to another representative or supervisor. Check that the consult call connects (the second agent gets the notification) and that the first agent can either conference everyone or transfer and drop off. The customer shouldn't be dropped during this process. After transfer, the new agent should be connected with the customer successfully. Learn more at [Use agent dashboard and call controls in the voice channel](/dynamics365/contact-center/use/voice-channel-agent-experience). |
  |**Mute/Unmute**| Verify that when muted, the customer can't hear the agent, and that unmute restores audio.|
  |**End Call**| Ending the call from the agent side disconnects the customer and properly ends the session in the app. (If an agent simply closes the session without hitting End, the system should treat that appropriately—typically it would keep the call active or reroute, so agents should be trained to use the End button.)|

- **Do chat-specific features (typing indicator, file share, quick replies) work for the agent?**  

  During a live chat test, check that the agent sees the **typing indicator** when the customer is typing (and vice versa, the customer sees one when agent is typing). If the chat allows file attachments or images, test sending a file from the customer side and ensure the agent can open or preview it. Likewise, have the agent send a file or an emoji to see if the customer receives it correctly. If your agents use **quick reply templates** or **knowledge base suggestions** in chat, verify those can be accessed and inserted into the conversation. Also, test the **end chat** function: when an agent or customer ends the chat, both sides should see the conversation closed, and the agent's session should wrap up appropriately (with an option to fill out any wrap-up notes or survey classification if configured).

- **Are agents receiving timely notifications for new incoming chats or calls?**  

  If an agent is marked available, they should be alerted when a new conversation is routed to them. Make sure the notification toast for an incoming voice call pops up on their screen (with ringtone sound) and that accepting the call works. For chats, an incoming chat notification should appear, possibly with a sound, allowing the agent to accept it. Test this when the agent is actively working in another area of the application (to ensure the notification grabs their attention). Also verify that if the agent is **Away/Offline**, they don't receive new conversations. New conversations must either route to other agents or stay in the queue. This confirms that presence is integrated with routing (as covered earlier) and that the agent app properly shows their status.

- **If call recording or transcription is used, can agents manage and view these?**  

  In many enterprise contact centers, calls are recorded and/or transcribed. If you have enabled *call recording and real-time transcription*, test that workflow. When a call connects, the system might auto-start recording or require the agent to select **Start Recording**. Ensure that works and that both the agent and customer are aware of any call recording announcement as required (usually a prompt like "This call is recorded"). If transcription is on, verify that the agent can see the live transcript during the call and that it accurately captures the conversation. Also test the *pause/resume recording* feature if agents need to skip sensitive info (for example, to avoid recording credit card numbers, the agent can pause recording while that info is spoken). Learn more at [Use agent dashboard and call controls in the voice channel](/dynamics365/contact-center/use/voice-channel-agent-experience). After the call, confirm the recording is saved and accessible (to a supervisor or for QA), and that the transcript is attached to the call's record. For chat, if your organization uses chat transcript email or download features, test that the agent can trigger those or that the customer can receive the transcript via email if appropriate.

> [!NOTE]
> Ensuring the agent desktop functions correctly means your team can focus on helping customers without fighting the tool. It's essential to test these agent interactions so that on go-live, agents are confident and efficient in using Dynamics 365 Contact Center.

## Integration and environment considerations

The purpose of this step is to confirm that all supporting technology and integrations for the contact center are working properly. This includes the network and hardware setup for voice (since Voice relies on internet connectivity), telephony integration (phone numbers, Session Border Controllers, etc.), and any external system integrations (like CRM data, Teams, or third-party apps). The goal is to **identify any environmental issues** that could impact functionality before going live.

- **Is the network connectivity robust and optimized for voice calls?**  

  Because voice calls use VOIP (Voice over IP) through Dynamics 365, a stable network is critical. Ensure agents have a reliable internet connection – ideally a wired Ethernet or strong Wi-Fi with low latency. *Bandwidth* should meet the recommended levels for audio; otherwise calls may sound choppy. (Refer to official system requirements for minimum bandwidth per call.) Test the quality of call audio in your network environment: listen for any jitter, delay, or echo. If issues arise, you might need to adjust network settings (like giving priority to voice traffic or checking for firewall bottlenecks). Also, verify that common network conditions (such as a VPN in use, or slightly constrained bandwidth) don't block the calls. A best practice is to use *wired connections and USB headsets with noise-canceling microphones* for agents, as this typically yields clear audio. Have a few agents test with the standard headset and perhaps one using a laptop's built-in mic to compare quality (the latter usually has more background noise). Learn more at [Best practices for setting up the voice channel](/dynamics365/customer-service/implement/voice-channel-best-practices).

- **Have the necessary URLs, ports, and services been allow-listed in security devices?**  

  Dynamics 365 Contact Center's voice and chat features rely on cloud services (for example, the voice channel uses Azure Communication Services (ACS) behind the scenes). Work with your IT security team to ensure all required domain URLs and ports are open in your firewalls and proxies. Find guidance at [Best practices for setting up the voice channel](/dynamics365/customer-service/implement/voice-channel-best-practices). This typically means allowing traffic to Azure service endpoints for voice media, signaling, and chat messages. If these aren't opened, agents might not receive calls or could have one-way audio. Once configured, perform a test call with a network monitoring tool to confirm the traffic isn't being blocked. Microsoft's documentation provides a list of endpoints to allow – double-check that your environment's network rules include all of them.

- **Are agent workstations and browsers configured for optimal performance?**  

  Verify that agents use a **supported browser** (such as Microsoft Edge or Google Chrome) for the Contact Center web app, and that the browser is up to date. Test the agent application in those browsers to ensure there are no UI glitches or excessive memory usage over time. If agents operate in a **virtual desktop infrastructure (VDI)** like Citrix or Azure Virtual Desktop, do a trial run there as well. In some VDI cases, the audio might have more latency. Microsoft provides a **Desktop Companion Application** to improve voice call handling in virtual environments (it helps reduce the delay in connecting calls). Learn more at [Best practices for setting up the voice channel](/dynamics365/customer-service/implement/voice-channel-best-practices). If your agents use VDI and you notice delays or audio issues during testing, consider using the companion app and include it in your test to see the improvement. Additionally, confirm that agents know how to select the correct microphone/speaker in the app's **Device settings** and that those settings persist between calls. Learn more at [Use agent dashboard and call controls in the voice channel](/dynamics365/contact-center/use/voice-channel-agent-experience). Any workstation power-saving settings that put devices to sleep should be adjusted so they don't interfere mid-call.

- **Does telephony integration (phone numbers and call routing infrastructure) function end-to-end?**  

  If you use Microsoft-provided telephone numbers (through the voice channel's default telephony) or Azure Communication Services for PSTN, test calls *into* those numbers and *out* from the agent to real phone lines. Every inbound number (toll-free, local, etc.) that is configured should ring through to the contact center. For outbound, have an agent dial an external number (like a personal mobile phone) to make sure outbound calls connect and show the correct caller ID. If your deployment involves a **Bring Your Own Telephony** approach (like using a Session Border Controller to connect an existing phone trunk, or integrating with Microsoft Teams for calling), perform integration tests for those as well. For example, if using Direct Routing via Teams, call the number that goes through your SBC and ensure it lands on the Dynamics agent, and test transferring a call from the Dynamics agent to a Teams user if that's part of your design. Any telephony-specific behaviors (call recording systems, compliance requirements like emergency call handling) should be verified in a controlled way. Even though these might go beyond Dynamics 365 itself, they're critical in an enterprise scenario.

- **Are integrations with other systems working as expected during interactions?**  

  Your Dynamics 365 Contact Center might integrate with other applications, such as a billing system (to fetch account info) or Microsoft Teams (for expert escalation), etc. Identify any such **integration points** that are part of the agent's workflow and include them in testing. For instance:

  - If the agent's screen is supposed to show data from an external CRM or database (via API calls) when a call comes in, place a call that should trigger this and see if the data loads correctly.

  - If agents can invite a **Teams** user (back-office expert) into a voice or chat, test that experience: the expert receives the Teams notification and can join the conversation, and audio/chat works with them in the loop.

  - If a Power Automate flow creates a task or sends an email after a conversation ends, check that those automations fire as intended.

    Essentially, ensure that no integration that your contact center relies on is failing silently. Each should be validated to make sure data flows between systems and the agent sees any external info needed.

- **Do you have monitoring and diagnostics in place, and have you checked them during testing?**  

  Enabling **telemetry and diagnostics** for your voice and chat system is a best practice. Learn more at [Best practices for setting up the voice channel](/dynamics365/customer-service/implement/voice-channel-best-practices). As you run through these tests, use the available dashboards or analytics (for example, the Omnichannel real-time analytics, or the Call Health Dashboard) to watch for errors or warnings. Verify that call quality metrics (latency, packet loss) are being captured. If you intentionally create a scenario with a known issue (like using a very low-bandwidth network for a test call), see if the telemetry reports reflect that (such as showing high latency). This helps ensure that when you go live, you can proactively catch and diagnose issues. Additionally, decide on the criteria for success for these tests – for example, "95% of test calls had a MOS score (voice quality rating) above 4" – and note any deviations for follow-up.

- **Can the system handle the expected load, and have you planned for performance testing?**  

  Finally, consider the scale of your contact center. If you expect, say, 100 concurrent voice calls and 50 concurrent chats at peak, your test plan should include a scenario (if possible) to simulate high throughput. While full load testing might require specialized tools or coordination with Microsoft (to not hit limits unexpectedly), you can start with a moderate volume test. Perhaps have 10 agents simultaneously handle voice calls, or use an auto-dialer to place 20 calls in quick succession, to observe system behavior. Monitor for any degradation in call setup time, audio quality, or agent app responsiveness. Ensure the system's capacity settings (like max concurrent sessions per agent, or max concurrent incoming calls in a queue) are tuned for your needs. If any bottleneck is identified (for example, a queue limit of 50 that you might exceed), you can address it before production. The goal is to confirm that as you scale up usage, the functional behavior remains consistent and reliable.

> [!NOTE]
> By validating the technical environment and integrations, you reduce the risk of encountering network, device, or external system issues during production. This proactive testing and configuration contribute to a smooth launch and ongoing operations.

## Conclusion

Following this blueprint helps ensure that your Dynamics 365 Contact Center deployment for voice and chat is thoroughly tested from end to end. Use the guiding questions in each area to develop specific test cases. For each test, document the expected result (for example, "Caller hears welcome greeting and is routed to Sales queue within 30 seconds") and compare it to the actual outcome during execution. Address any gaps or failures by refining configurations or working with Microsoft support if needed.

Remember, a comprehensive functional test plan not only validates the "happy path" scenarios but also covers edge cases and failure modes (like network drops or unattended calls) to verify the system's resilience. By investing this effort before go-live, you can deploy the contact center with confidence, knowing that customers receive a smooth experience on voice and chat, and agents have the tools they need to assist effectively.

Make sure you use Microsoft's official documentation and resources for any detailed setup steps or latest features (such as new voice preview features or updated best practices). The [Dynamics 365 documentation](/dynamics365/) on the Microsoft Learn website provides deep dives on specific capabilities, which can be useful references when writing your test cases or troubleshooting issues discovered in testing.

With a solid plan and thorough testing across IVR, routing, chat, agent experience, and integrations, your team will be well-prepared to deliver a reliable, high-quality contact center experience. Good luck with your testing and deployment. Find more information at [Best practices for setting up the voice channel](/dynamics365/customer-service/implement/voice-channel-best-practices).

## Dynamics 365 Contact Center functional testing checklist

Use the following checklist to verify key functional areas of your Dynamics 365 Contact Center (Voice & Chat) deployment. Each category aligns with the testing blueprint and includes checkboxes with brief descriptions of what to test in that area. Customers can refer to the full blueprint document for detailed definitions and context.

### IVR setup and call flows

Use this checklist to ensure your IVR (Interactive Voice Response) menus and call flows are functioning as intended:

- **Greetings and messages:** Verify the correct welcome greeting and hold/queue messages play for callers.

- **IVR input handling:** Confirm the IVR accepts and processes all inputs (DTMF/voice) and responds appropriately, including for invalid or missing input.

- **Menu option routing:** Ensure every IVR menu selection leads to the intended department or queue, and self-service options work end-to-end.

- **After-hours behavior:** Test calls outside business hours to confirm the IVR follows after-hours rules and provides correct options (such as voicemail or callback).

- **Special scenarios:** Verify the IVR handles emergencies or downtime by playing the correct special messages and bypassing standard menus.

- **Post-call survey trigger:** If enabled, ensure post-call surveys or feedback are triggered only under the right conditions (not for abandoned/dropped calls).

### Call routing and queues

Check that incoming calls (and chats) are routed correctly and queue behavior is as expected:

- **Correct queue/agent assignment:** Verify incoming calls and chats route to the correct queue and agent based on skills, language, or priority.

- **No-answer and overflow handling:** Simulate scenarios where agents don't answer; confirm overflow or timeout strategies work such as a backup queue and voicemail.

- **No dropped/stuck calls:** Ensure calls/chats remain connected during routing and transfers, with no unexpected disconnects.

- **Agent availability and capacity:** Confirm routing logic respects agent availability and workload limits; agents only receive interactions when marked available and within their capacity.

### Chat workflows

Validate the end-to-end process for live chat interactions, from initiation through agent handling:

- **Chat initiation path:** Start a test chat to ensure the customer is greeted and routed to a live agent as designed, including bot-to-agent handoff if applicable.

- **Virtual agent functionality:** Test chatbot responses to common questions and verify seamless handoff to a human agent with context transfer.

- **Chat routing rules:** Ensure live chat requests route to the correct queue or agent group, and agent concurrent chat limits are honored.

- **Transcript and data capture:** Verify chat transcripts and related records are saved, including customer info and any files exchanged.

- **Concurrent chat load:** Simulate multiple simultaneous chats to ensure the system handles high volume and displays appropriate wait messages.

### Agent desktop experience

Ensure that the agent-facing experience is smooth and all tools work during voice and chat handling:

- **Customer info screen pop:** Confirm agents see relevant customer info and context automatically when a call or chat arrives.

- **Record creation and linking:** Verify the system creates and links interaction records (Conversations, Cases) for each call/chat.

- **Voice call controls:** Test all call controls (Hold, Mute/Unmute, Consult/Transfer, End Call) to ensure they work as expected.

- **Chat tool features:** Ensure chat features (typing indicator, file sharing, quick replies) work for agents and customers, and chats end cleanly.

- **Incoming notifications:** Confirm agents receive timely notifications for new calls/chats and do not receive new assignments when marked Away/Offline.

- **Call recording/transcription:** Test call recording and transcription features, including announcements, pause/resume, and access to saved recordings/transcripts.

### Integration and environment

Verify that the surrounding environment and integrations support the Contact Center solution reliably:

- **Network readiness:** Check network stability and bandwidth for voice calls; address any quality issues before go-live.

- **Firewall/ports configuration:** Ensure all required URLs and ports for Dynamics 365 Contact Center are allow-listed in firewalls and proxies.

- **Agent devices and browser settings:** Verify agent workstations use supported browsers/apps and are configured for optimal performance; test in VDI environments if applicable.

- **Telephony integration:** Test inbound and outbound calls for all configured phone numbers, including integration with external systems (e.g., Teams, SBC).

- **External systems integration:** Confirm integrations with CRM, Teams, and automated workflows function correctly during interactions.

- **Monitoring and analytics:** Use monitoring tools to observe system health and ensure diagnostics capture relevant data and errors.

- **Performance at scale:** Simulate peak loads to confirm the system handles expected volume without delays or failures.

> [!TIP]
> Check off each item as you validate it. For detailed definitions and troubleshooting, refer to the full Functional Testing Blueprint.

## Related content

- [Best practices for setting up the voice channel](/dynamics365/customer-service/implement/voice-channel-best-practices)  
- [Use agent dashboard and call controls in the voice channel](/dynamics365/contact-center/use/voice-channel-agent-experience)  
- [Capacity profiles](/dynamics365/customer-service/administer/capacity-profiles)
