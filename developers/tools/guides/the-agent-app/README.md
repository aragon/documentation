# How to use the Agent App

{% hint style="info" %}
This guide will show you how to <mark style="color:blue;">**install and use the Agent App**</mark>.
{% endhint %}

### Introduction

The Agent app (or Aragon Agent) is an Aragon app that can be installed in any Aragon DAO. It's main feature is its ability to perform arbitrary calls to contracts. This means it can be thought of as the **external interface of a DAO**.

Put another way:

{% hint style="info" %}
Aragon Agent is a fully-fledged Ethereum account owned by an Aragon organization. **It's like a multi-signature account on steroids that enables organizations to interact with any Ethereum contract or protocol.** For example trading tokens on 0x or Uniswap, opening a Maker CDP, managing names in ENS, owning digital LAND parcels, or even breeding digital cats.
{% endhint %}

In technical terms, it's a superset of the [Vault app](https://github.com/aragon/aragon-apps/tree/master/apps/vault), which means it can hold valuable assets (ETH and [ERC-20](https://en.wikipedia.org/wiki/ERC-20) tokens).

Concretely, the Agent app allows for things like:

* An Aragon DAO to interact with other Ethereum smart contracts or protocols without the need to implement a custom Aragon app for every protocol.
* Members of DAOs to identify themselves as their DAO when using any Ethereum dApp.
* An Aragon DAO to participate as a stakeholder in another DAO.

