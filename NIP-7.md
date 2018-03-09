
## Risk Mitigation Balance NIP-???
  
## Preamble
    NIP: NIP-7
    Title: Risk Mitigation Balance
    Author: Aldyen Donnelly, Jaycen Horton, Paul Carduner
    Type: Standard Track
    Categroy: Core
    Status: Draft
    Created: February 28, 2018
    Replaces: N/A

## Simple Summary
The Risk Mitigation contract is how Nori upholds its commitment to the buyers which is that each NORI token retires 1 TCO2e (+/-10%) (CRC)[NMP-2]

## Abstract
A Risk Mitigation Balance in Nori is a balance within the Nori Market (Nori Marketplace)[NIP-???] that programatically witholds NORI tokens and then can only spend its balance on CRCs of Tier 1 (`category=1`) within the Market contract, at the end of the FIFO queue. Once those CRCs are purchases they are transfered to the buyer who's balance contains the CRCs of Tier 0 (`category=0`)

## Motivation
When a buyer purchases a CRC, the buyer is guaranteed that the NORI tokens they spent on CRCs will, at some point, be equivalent to the NORI they spent on a 1 TCO2e = 1 NORI basis (within an acceptable +/- percent range defined within the NMP associated with the CRCs purchased). 

The motivation behind the Risk Mitigation Balance is to allow this guarantee by following an example like the following:
- Bob Creates 100 CRCs which are not of Tier 1 (`category=1`) and lists them on the market
- Alice Buys 100 CRCs from Market, which happen to be the 100 CRCs which Bob created
- At a later time an (auditor)[NIP-???] asserts that 50 of Bobs CRCs are currently of Tier 1 (`category=1`) and therefore valid, but 50 of Bobs CRCs are of Tier 0 (`category=0`) and therefore invalid 
- Bob does not get the remaining 50 restrcited NORI tokens
- Alice however still has 100 CRCs of both Tier 1 and Tier 0 and Bob has 50 NORI tokens
- the Risk Mitigation Balance has 50 NORI tokens
- If we query alices account we can see that the 100 CRCs Alice owns came from Bob, but 50 of those CRCs are to be replaced at a later date (indicated as Tier 0 CRCs)
- Carol creates 50 CRCs of Tier 1 and lists them on the market
- The restericted balance is then used to satisfy the guarantee by purchasing those CRCs and transfering them to Alice incrementing her __CRC of Tier 1 balance__ from 50 CRCs of Tier 1 to 100 CRCs of Tier 1

## Specification
NORI tokens inside the Risk Mitigation Balance MUST be used to purchase CRCs of Tier 1 (`category=1`).

At any point in time the combination of NORI tokens and CRCs of Tier 1s that are being held in the risk mitigation account will have a current market value of one of the following:
* less than the estimate of the cost of commitment to the CRC buyers
* greater than or equal to 

## Rationale
To be completed 

## Backwards Compatibility
To be completed 

## Test Cases
To be completed

## Implementation
To be completed 
