## Preamble

    NIP: <to be assigned>
    Title: NRC-6 Carbon Removal Claim
    Author: jaycen@nori.com
    Type: Standard
    Category: Core
    Status: Draft
    Created: 2018-03-08

## Simple Summary
A Carbon Removal Claim ("CRC") is the main CommodityType implementation for Nori and represents the removal of CO2 from the atmosphere. 

## Abstract
CRCs are a CommodityType, implementing the CommodityInterface [NRC-4]. Each CRC represents a claim of an amount of CO2 having been removed from the atmosphere. It is made up attributes such as who is claiming the CO2 has been removed, which methodology it has employed, and anything else necessary to allow for its verification and audit. 

## Motivation
Participants in the Nori ecosystem can create new CRCs whenever CO2 has been removed from the atmosphere. However, when this happens it is subject to a specific process such that it can later be auditor for accuracy and validity.  This NIP does not aim to guide the processes surrounding those events, and instead simply clarifies the attributes necessary for existence within a Commodity Market, specifically the Nori Marketplace. 

## Specification
The CRC leverages Pseudo contract introspection and adds their ability to allow for a `callOperator` function which notifies a contract if it has been made an operator for a CRC.

Following the guidelines set in [NIP-5]() , the CRC leverages its Commodity struct as follows:

The estimation category based on tiers
```solidity
uint64 category;
```

A timestamp from the block in which this CRC was minted
```solidity
uint64 timeRegistered;
```

The index or ID of the CRC that created this CRC. This is used when CRCs are split into two new CRCs, each with smaller values. It is set to 0 for brand new CRCs which have never been split. 
```solidity
uint64 parentId;
```

This represents the total amount of CO2 claimed to have been removed from the atmosphere. Since it is not feasible to create a new CRC for every TCO2e removed, this field can be used to batch together multiple claims into one.
```solidity
uint64 value;
```

This attribute is used to prevent multiple transfers of CRCs. Once a CRC has been transferred once, this attribute is set to true and cannot be transferred again. 
```solidity
bool locked;
```

The IPFS/IPLD hash which can be used to look up data associated with a particular CRC
```solidity
bytes misc;
```


### Non-standard CommodityType Specs
Aside from the standard implementation of a CommoditityType, the following functions require some special logic:
```solidity
function _transfer(address _from, address _to, uint256 _tokenId) internal {
        // standard _transfer logic defined in ERC-721/777
        // ......
        // end standard transfer logic
       
        // retire/lock the CRC, preventing future transfers 
        commodities[_tokenId].locked = true
}
```
In calling transfer, the CRC must first call `revokeOperator` if there is one, this is used to remove listing of a CRC sale in the event that there is one
```solidity
function transfer(address _to, uint256 _tokenId) public{
       // require crc is not retired
        require(!commodities[_tokenId].locked);
       
        // revokeOperator implementation here
        
       // if it isn't retired, continue the transfer as usual
       _transfer(address _from, address _to, uint256 _tokenId);
}
```

The CRCs `callOperator` function is used to invoke the a market contract's flow for creating a new CRC sale.
```solidity
/** @dev Notify a recipient it has been made the operator for a CRC */
function callOperator(address _from, address _operator, uint256 _tokenId, bytes _userData) internal {
        address operatorImplementation = interfaceAddr(_to, "ITokenOperator");
        if (operatorImplementation != 0) {
            ITokenOperator(operatorImplementation).madeOperator(
                _from, _operator, _tokenId, _userData);
        }
}
```
When other addresses are made an operator for a CRC, the owner is restricted from invoking a transfer or authorizing another operator. If the owner wants to restore that function, it must first call `revokeOperator` (which is in addition used to cancel a sale from a market). 
```solidity
function authorizeOperator(address _operator, uint256 _tokenId, bytes _userData) public {
        // standard authorizeOperator functions defined in erc721/777
        callOperator(msg.sender, _operator, _tokenId, _userData)
}
```
A revokeOperator, opposite of authorizeOperator, is used to cancel a existing sale, if there is one, for this CRC
```solidity
function revokeOperator(address _operator, uint256 _tokenId, bytes _userData) public {
        //callOperator MUST be used to cancel market sale listing for this CRC
        callOperator(msg.sender, _operator, _tokenId, _userData)
        // if there was a sale and removing the listing succeeded
        // only then continue standard revokeOperator functions defined in erc721/777
}
```
## Rationale
This standard is a necessary base which will allow for the Operation of Nori's CRC:NORI marketplace.

## Backwards Compatibility
To be completed

## Test Cases
To be completed

## Implementation
To be made public

## Copyright
Copyright and related rights waived via [CC0](https://creativecommons.org/publicdomain/zero/1.0/).
