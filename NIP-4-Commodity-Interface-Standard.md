## Preamble

    NIP: <to be assigned>
    Title: NRC-4 Commodity Interface Standard
    Author: jaycen@nori.eco
    Type: Meta
    Status: Draft
    Created: 2017-12-18

## Simple Summary
A generalized specification guideline for Commodity Interface proposals/designs/implementations

## Abstract
This specification does not propose implementation requirements, but instead provides a standard to be followed when creating new Commodity interface. This standard proposes that future Commodities wishing to be fully interoperable with the Market Ecosystem Components be designed and implemented in a structure which will be described as a generalized interface similar to [EIP-20](https://github.com/ethereum/EIPs/blob/master/EIPS/eip-20-token-standard.md), [ERC-223](https://github.com/ethereum/EIPs/issues/223) and [ERC-721](https://github.com/ethereum/EIPs/issues/721).

## Motivation
There are several types of potential commodities that can exist in a [NRC-2](https://github.com/nori-dot-eco/NIPs/issues/2) Market Ecosystem and as such there needs to be a standard guideline across Commodity Interfaces in order to allow a Commodity Registry [NRC forthcoming] to successfully leverage basic calls using interface signatures. 

## Specification
To be completed

### methods
To be completed 

## Rationale
While there are a number of functions that will generally be required across commodity types, the specification only outlines requirements to define each commodity by its name and any other functionalities are optional and can be defined in their own standard document.

There are many different types of Commodity Interfaces such as [EIP-20](https://github.com/ethereum/EIPs/blob/master/EIPS/eip-20-token-standard.md), [ERC-223](https://github.com/ethereum/EIPs/issues/223) and [ERC-721](https://github.com/ethereum/EIPs/issues/721) which follow the basic specification outlined here. 

Following this guideline allows for many different types of Commodities to be created in a Market Ecosystem whilst staying interoperable with the Commodity Registry smart contract for a particular Market without directly affecting contract requirements or dependencies in other places

## Backwards Compatibility
Changes to this specification will directly affect and existing or planned Commodity contract which implements this interface and will likely have an effect on the Commodity Registry as well.

## Test Cases
N/A

## Implementation
To be completed

## Copyright
Copyright and related rights waived via [CC0](https://creativecommons.org/publicdomain/zero/1.0/).

