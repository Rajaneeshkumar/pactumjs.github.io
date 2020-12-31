# Contract Testing

Contract Testing is a technique for testing interactions between applications (often called as services) that communicate with each other, to ensure the messages they send or receive conform to a shared understanding that is documented in a **contract**.

Contract Testing gives a way for services to enter into an agreement on how they are going to communicate with each other. Once the agreement is in place it provides a way to modify the agreement but before the change takes effect, the services need to sign off on the new contract.

Learn more about contract testing at [pact.io](https://docs.pact.io)

> Pactum is inspired by **pact.io**. Pactum works at the HTTP layer while pact.io works at the unit testing level.

## Table of contents

* [Terminology](#terminology)
* [Workflow](#workflow)
  * [Consumer Testing](#consumer-testing)
  * [Provider Verification](#provider-verification)
* [Interactions](#interactions)

## Terminology

* **Consumer** - An application that makes use of the functionality or data from another application to do its job.

* **Provider** - An application (often called a service) that provides functionality or data for other applications to use, often via an API.

* **Contract** - A contract is a documented form of shared understanding between a consumer & a provider. Pact creates this document in the form of a **JSON** file.

* **Pact** - A contract between a consumer and provider is called a pact. Each pact is a collection of interactions.

* **Interaction** - An individual message that combines a request sent by the consumer & minimal expected response replied by the provider.

* **Minimal Expected Response** - It describes the parts of the response the consumer wants the provider to return.

## Workflow

Pactum follows the same workflow of [pact.io](https://docs.pact.io)

Contract Testing has two steps

1. Defining Consumer Expectations (**Consumer Testing**)
2. Verifying Expectations on Provider (**Provider Verification**)

### Consumer Testing

Consumer Testing is performed at the consumer pipeline.

During consumer testing, a consumer will generate pacts with its provider using interactions. Consumer Pact tests operate on each interaction to say *"assuming the provider returns the expected response for this request, does the consumer code correctly generate the request and handle the expected response?"*.

Consumer Testing will

* Generate contracts (pact files) between a consumer & its providers
* Publishes the contract (pact files) to a shared location like [pact-broker](https://docs.pact.io/pact_broker)

### Provider Verification

Provider Verification is performed at the provider's pipeline.

During provider verification, each request is sent to the provider, and the actual response it generates is compared with the minimal expected response described in the consumer test.

Provider Verification will

* Fetch contracts (pact files) between a provider & its consumers from a shared location like [pact-broker](https://docs.pact.io/pact_broker)
* Validate each pact against the provider & publish the results.

----------------------------------------------------------------------------------------------------------------

<a href="#/component-testing" >
  <img src="https://img.shields.io/badge/PREV-Component%20Testing-orange" alt="Component Testing" align="left" style="display: inline;" />
</a>
<a href="#/consumer-testing" >
  <img src="https://img.shields.io/badge/NEXT-Consumer%20Testing-blue" alt="Consumer Testing" align="right" style="display: inline;" />
</a>