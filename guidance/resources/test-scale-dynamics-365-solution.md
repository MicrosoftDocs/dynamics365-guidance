---
title: Set up and run load tests on Dynamics 365 solutions
description: Learn how to set up and run load tests on Dynamics 365 solutions with Azure Load Testing, using Java, Apache JMeter, and samples provided by Microsoft.
ms.date: 06/26/2023
ms.topic: how-to
author: edupont04
ms.author: darent
ms.custom:
 - ai-gen-docs-bap
 - ai-gen-desc
 - ai-seo-date:08/23/2023
 - bap-template
---

# Set up and run load tests for your Dynamics 365 implementation projects

***Applies to: Dynamics 365 Customer Service***

Load testing your Dynamics 365 solution can offer significant benefits for reliability, performance, and cost optimization, particularly during your preparation for go-live. Load tests are one of the tests that should be part of the [testing strategy](..//implementation-guide/testing-strategy.md) for your Dynamics 365 implementation projects.

Although many tools and services support load testing, the guidance in this article is based on [Azure Load Testing](/azure/load-testing/overview-what-is-azure-load-testing). The following instructions show you how to set up and run the [load test samples](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/tree/master/Customer%20Service/Testing/At%20Scale/Samples) that Microsoft provides in GitHub.

## Prerequisites

- Apache JMeter and Java SE Development Kit:

  - Azure Load Testing automatically generates an Apache JMeter script for your load test. Apache JMeter is an open-source, Java-based application for testing functional behavior and measuring performance. JMeter uses the [keytool](https://cwiki.apache.org/confluence/display/JMETER/TestRecording210) utility to create certificates and record HTTPS traffic.
  
  - If you plan to record HTTPS traffic, the Java SE Development Kit is also required. Download and install the latest Java SE Development Kit for your operating system at [https://www.oracle.com/java/technologies/downloads/](https://www.oracle.com/java/technologies/downloads/).

  To verify that Java is installed, enter the command `java -version` at a command prompt.

- Operating system: Apache JMeter runs on Windows, Linux, macOS, and Ubuntu.

- Azure subscription (optional): We recommend you use an active Microsoft Azure subscription. It's a requirement if you plan to load test in Azure or integrate load testing into your CI/CD pipelines.

## Get Apache JMeter

Install [Apache JMeter](https://jmeter.apache.org/) locally to create, edit, and debug load tests and load test scripts.

- [Get started with JMeter](https://jmeter.apache.org/usermanual/get-started.html).
- [Install JMeter](https://jmeter.apache.org/usermanual/get-started.html#lets_start).
- [Learn how to run JMeter](https://jmeter.apache.org/usermanual/get-started.html#running).

Apache JMeter has two modes, GUI mode and CLI mode.

- Use GUI mode for test creation, editing, and debugging.
- Use CLI mode to run a load test.

If you load the test script in JMeter in GUI mode, the test might not be ready to run against your application. When you use the samples from Microsoft, follow the instructions provided for each one. The instructions include the steps necessary to prepare the sample for execution against your application.

## Use Azure Load Testing

[Azure Load Testing](/azure/load-testing/overview-what-is-azure-load-testing) is a fully managed load-testing service in Azure that generates high-scale load. An Azure Load Testing resource makes it easy to generate high-scale load with a JMeter script. Use it to perform load testing without the need for complex infrastructure, and to integrate load testing into automated CI/CD pipelines to identify and address performance bottlenecks early in the development lifecycle.

- [Get started with Azure Load Testing](/azure/load-testing/quickstart-create-and-run-load-test).
- [Learn how to load test a website using a JMeter script in Azure Load Testing](/azure/load-testing/how-to-create-and-run-load-test-with-jmeter-script).

If you've defined your load tests in Apache JMeter, use the JMeter script .jmx file to [create a load test](/azure/load-testing/how-to-create-and-run-load-test-with-jmeter-script##create-a-load-test) in Azure Load Testing.

### Configure parameters

On the **Parameters** tab, you can add the following information:

- Enter any environment variables to be passed into the test from Azure Load Testing to JMeter user-defined variables (System.getenv); for example, a host name, URL, or parameters passed in through CI/CD automation.

- Enter any secrets to be passed into the test from Azure Load Testing. Secrets might be used in a test that runs against an API or function that requires authentication.

- Enter any certificates to be passed into the test from Azure Load Testing. Certificates might be used in a test that runs against a secure endpoint.

Azure Load Testing integrates with Azure Key Vault. We recommend you store secrets and certificates there.

### Configure the load

On the **Load** tab, configure the test engine instances to meet the target load for the test. The number of threads specified in the .jmx file represents the number of threads, or virtual users, run by one test engine instance.  

Network traffic to Power Platform applications goes through public networks.  

### Configure test criteria

On the **Test criteria** tab, you can add the following information:

- Define criteria for the performance expectations of the system under test. Use them to determine the failure conditions for the test when the criteria evaluate to true.

### Configure monitoring

On the **Monitoring** tab, you can add the following information:

- Add any Azure-hosted applications to monitor server-side performance when running a load test in Azure Load Testing.

### Run the test

After the validation has passed on the **Review + create** tab, you can run the load test. If you selected **Run test after create**, the test runs automatically.

## JMeter distributed testing

[JMeter distributed testing](https://jmeter.apache.org/usermanual/jmeter_distributed_testing_step_by_step.html) is a method of executing load test volume on multiple machines simultaneously. Distributed testing introduces the concept of a *controller node* and a *worker node*.

- The controller node is the primary system that runs JMeter (`jmeter.bat`) and controls the test.

- The worker node represents the systems that run Jmeter-server (`jmeter-server.bat`). It takes commands from the controller node to send requests to the target application.

Use distributed testing in any of the following situations:

- You want to simulate users accessing your application from different locations.
- You want to simulate a higher volume of users.
- Local CPU and memory resources are limited.

## Related resources

- [Scale load tests in Dynamics 365 implementations](test-load-tests-scaling.md)
- [Key concepts for new Azure Load Testing users](/azure/load-testing/concept-load-testing-concepts)
- [Getting started with JMeter](https://jmeter.apache.org/usermanual/get-started.html)
- [JMeter best practices](https://jmeter.apache.org/usermanual/best-practices.html)
- [Configure high-scale load tests](/azure/load-testing/how-to-high-scale-load)
- [Parameterize load tests](/azure/load-testing/how-to-parameterize-load-tests)
- [Distributed testing](https://jmeter.apache.org/usermanual/jmeter_distributed_testing_step_by_step.html)
- [Download Java](https://www.oracle.com/java/technologies/downloads/)
- [Sample scripts from Microsoft](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/tree/master/Customer%20Service/Testing/At%20Scale/Samples)
- [Implementation guide: Testing strategy](../implementation-guide/testing-strategy.md)

<!--## Tags

*Products:* Dynamics 365 Customer Service-->
