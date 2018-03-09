## Preamble

    NIP: NIP-2
    Title: Market Ecosystem Components
    Author: jaycen@nori.com
    Type: Meta
    Status: Draft
    Created: 2017-12-17

## Simple Summary
This specification outlines the core components of a market ecosystem (implemented as smart contracts) which can be used to implement standard commodity markets (such as for a Carbon Removal Credit in the case of Nori).

## Abstract
This standard does not propose implementation details of any particular component, but rather their relationships and high level ecosystem overviews. Additionally, this marketplace takes no preference to any particular type of commodity/participant implementation requirements. Instead, this proposal outlines the necessary components (implemented as smart contracts) needed for a market to exist: a Market, Participant, and Commodity

## Motivation
Defining a standard market component ecosystem allows for the creation of different types of markets to exist using a set of registries at the market, participant, and commodity level.

A registry of markets allow for a lookup of operating markets, a lookup of commodities allow for a lookup of commodities in those markets, and a lookup of participants allow for a lookup of identities allowed to directly interact with the smart contracts within each market.

Starting with these foundational components allows for extensions to market, commodity and participant rules to exist within each market as well as across multiple markets.

## Specification
Component Relationship Overview
![marketplace components - revision 1](https://user-images.githubusercontent.com/18407013/37196527-693c8a8e-2334-11e8-9718-34ae2b0cad3d.png)

While the purpose of this specification is to provide an overview of how markets, commodities, and participants interact with each other, the scope of each individualized specification will be defined in forthcoming NIPs. Instead, the following is a general description of the compartmentalization of each component.

### MarketRegistry
A market Registry is a smart contract which holds information about available markets.There is at least one global registry (though other may create more like the global Registry) to which you can add a market. Adding a market to it would increase the experience of the user that the GUI Client can use or not.

Each market in the MarketRegistry contain an (or many) associated ParticipantRegistry smart contracts

Each market in the MarketRegistry contain an (or many) associated CommodityRegistry smart contracts

### Market 
The Market component is a smart contract interface which allows for creating a particular type of a market by creating a MarketType smart contract which implements the Market interface to define basic functionalities of a particular MarketType.

### MarketType
The  MarketType smart contract realizes the Market interface contract and contains the scope for the basic functions of all market functions. The MarketType contract can be extended to allow for multiple types of Market realizations with specialized functionalities.

### ParticipantRegistry
Each market in the MarketRegistry contain an (or many) associated ParticipantRegistry smart contracts. A ParticipantRegistry contract contains a list of users and their permission (based on ParticipantType association) to perform certain actions on functions defined within the scope of that particular market.

### Participant
A Participant is a realizable smart contract interface for implementing basic participant functionalities. The participant interface can be realized by the PariticipantType contract, and define basic functionalities for returning a PariticipantType for a specified user address.

### ParticipantType
Only basic and general participant functionalities must be defined here and any specialized functionalities are created by extending the ParticipantType smart contract.

### CommodityRegistry
Each market in the MarketRegistry contain an (or many) associated CommodityRegistry smart contracts. A CommodityRegistry contract contains a list of commodities and their types (based on CommodityType association) which, based on a ParticipantType within the scope of the same MarketRegistry contract, a Participant can perform certain actions on for that commodity defined within the scope of that particular market.

### Commodity
A Commodity is a realizable smart contract interface for implementing basic commodity functionalities. The Commodity interface can be realized by the CommodityType contract, and defines basic functionalities for returning a CommodityType for a specified user address.

### CommodityType
Only basic and general Commodity functionalities must be defined here and any specialized functionalities are created by extending the CommodityType smart contract. An example Extended Commodity type is an ERC-20 token or ERC-721 token extending CommodityType contract.

## Rationale
Creating a specification for a generalized commodity market allows for creating any number of specialized markets with an interoperable function set. Additionally defining the market into these three components (Participant, Market, and Commodity), allows for the creation of different participant requirements across different Market types or different Commodity types. In addition, by compartmentalizing each of these components from each other changes necessary in one of the components should not affect the way the other components need to behave. This allows for easier scale to commodity types, market types, and participant types (and their respective requirements) by simply extending each interface, and updating the registry accordingly.

For instance, a new CommodityType can extend the Commodity interface by using CommodityFactory to create the Commodity from a ParticipantType that has the permissions neccesary for Modifying the CommoityRegistry. This should not effect or require any changes to the Market components, as the Commodity and Participant components are localized in scope for aparticular Marekt in the MarketRegistry, and not the other way around. Changes to that scoped Market might be adjusted using MarketFactory on that particular Market but should not effect derived Participant or Commodity functionalities and would instead extend or modify variables (such as a Market name) that are not depended on by Participant or Commodity components (such as changing the way a Market and Commodity are related in such a way that causes existing functionality to break).

## Backwards Compatibility
As this is the base standard for the rest of the Nori development, all future implementations should refer to this standard and report any potential errors within the scope of this specification so that implementations can maintain scale and interoperability with the Nori ecosystem.

## Test Cases
N/A

## Implementation
The implementation for each particular component will be defined in specific Component NIP/NRCs.

## Copyright
Copyright and related rights waived via [CC0](https://creativecommons.org/publicdomain/zero/1.0/).



