## Preamble

  NIP: NIP-1

  Title: FIFO MarketType Formalization

  Author: Aldyen Donnelly, Jaycen Horton, Chrsitophe Jospe, Ross Kenyon, Paul Carduner, Jacob Farny, Paul Gambil

  Type: Standard Track

  Category: Core

  Status: Draft

  Created: March 19, 2018

  Replaces: N/A

  Requires: [ERC-820](https://github.com/ethereum/EIPs/issues/820), [MarketType](), [MarketInterface]()


## Simple Summary
The FIFO Market inside of the Nori ecosystem allows [suppliers]() to list their [CRCs]() in a first in first out ordering. 

## Abstract
When a [supplier]() generates a CRC, they can list their CRC for sale in the Nori Marketplace. The Nori marketplace currently only enables FIFO purchases and sales, so when a supplier chooses to sell their CRC, they do so by authorizing the FIFO market contract an an approved operator of a particular CRC index(see [authorizeOperator in CRC formalization]()). In doing this, the FIFO market updates its array of sales, appending that particular CRC at the end of the list. 

When a [buyer]() comes along and choses to purchase CRCs using their NORI, he initiates a purchase in a way similar to a CRC sale, except that the process revolves around authorizing the FIFO market contract an an approved operator  of a particular amount of NORI (see [authorizeOperator in CRC formalization]()). 

If the first available CRC (the earliest one listed on the market) has a value (see [value attribute in CRC formalization]()) of 100, and the buyer is seeking to purchase that entire CRC, they must then authorize thee FIFO market contract as an operator of 100 NORI. In cases which the buyer is seeking to purchase less or more than that amount, the process of [CRC splitting]() can be invoked to achieve this.

After both of these actions have been taken, a swap of the ownership takes place where the supplier is given 100 NORI and the buyer is given the CRC of value 100 by way of invoking the CRCs send/transfer function which MUST then retire the CRC and disallow future transfers or market listings.

## Motivation
A FIFO market is important to establish a universal price on CO2 removal. In a spot market you have bids/asks causing the price of CO2 removal fluctuates. In Nori, a CRC representing 1 TCO2e removed is always equivalent to 1 [NORI](NIP-???). This fact, in combination with a FIFO type market, forces buyers and sellers to not care about the novelties associated with particular carbon removal practices. In such, 1 ton removed is 1 ton removed, is 1 ton removed.
 
FIFO ensures that Nori enables the growth of the market of the FIFO buyers to take place in a way that spot markets or the current market doesn’t allow.

## Specification
The FIFO Market is a [NIP-??? MarketType]() implementing the [NIP-??? MarketInterface](). 

## Rationale

## Backwards Compatibility
To be completed

## Test Cases
To be completed

## Implementation
To be completed

## Copyright
Copyright and related rights waived via [CC0](https://creativecommons.org/publicdomain/zero/1.0/).


