## Preamble

    NIP: <to be assigned>
    Title: NRC-5 CommodityType
    Author: jaycen@nori.com
    Type: Meta
    Status: Draft
    Created: 2018-02-22

## Simple Summary
A generalized specification guideline for CommodityInterface implementations, henceforth called a CommodityType

## Abstract
A CommodityType is any contract which fully implements the standard CommodityInterface [NRC-4] 

This specification does not propose implementation requirements (outside of them needing to implement the CommodityInterface), but instead provides guidelines for implementing a CommodityType.

## Motivation
There exist valid use cases where a CommodityType might be a valid purchasing instrument for another CommodityType within a Market or where Different types of CommodityType implementations might need to coexist within or outside the context of Nori’s ecosystem components. However, this NIPs main purpose is to allow for the discussion of third parties who might explore implementing their own CommodityTypes in their own ecosystem so that a common implementation standard can be developed, therefore increasing likelihood of third party support.

## Specification
A CommodityType must fully implement the CommodityInterface [NRC-4].

The main storage part of any CommodityType is inside of its Commodity struct. Outside of creating a standard identifier and lookup design for CommodityTypes (and perhaps transferability function implementations), it is possible that most third party applications might remain agnostic to the other functional parts of a CommodityType. As such the following defines a common structure for CommodityTypes.
```solidity
   struct Commodity {
       // The commodity variants identifier number. These can be different grades of a commodity based on validity (eg the level of guarantee that a particular claim that a real world event happened), or an entirely different commodity all together (eg a Carbon Removal Claim  and a Methane Removal Claim)
       uint64 category;

       // The timestamp from the block where this commodity came into existence
       uint64 timeRegistered;

       // The ID of the parent of this commodity (e.g. the commodity id before it was split
       // set to 0 for brand new commodities which have never been split. This is used for tracking commodities through time and as a restrictor for disallowing multiple transfers
       uint64 parentId;

       // The value stored in this particular commodity token. Since it is not feasible to create a new commodity, a batch type implementation might be valuable where multiple commodities come into existence at the same time
       uint64 value;

      // This attribute is used to prevent multiple transfers of commodities. Once a commodities
      // has been transferred once, this attribute is set to true and cannot be transferred again
       bool locked;

       // reserved for misc. data needed for future commodity types. Set to 0 for commodities
       // with no misc. Data. This is the primary field for data lookup and should implement a multihash (IPFS/IPLD) or other content addressable format
       bytes data;
   }
```
  
## Rationale
Defining the above qualities in a commodity are necessary fields. While other fields might be necessary for unique CommodityTypes, it should be preferred to utilize the misc field and store data in an external decentralized construct such as IPFS.

A forthcoming NIP will define how the misc field should be constructed.

A forthcoming NIP will demonstrate how to utilize the parentId to split commodities, and retire them (prevent transferability).

A forthcoming NIP will define how to leverage commodityKind to grade validity of a real world commodity claim.

## Backwards Compatibility
To be completed

## Test Cases
To be completed

## Implementation
To be completed (reference NoriCommodity)

## Copyright
Copyright and related rights waived via [CC0](https://creativecommons.org/publicdomain/zero/1.0/).
