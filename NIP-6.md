# NIP-??

## Preamble

  NIP: NIP-???

  Title: CRC and NORI token transfers for multi-tiered CRCs

  Author: Aldyen Donnelly

  Type: Standard Track

  Categroy: Core

  Status: Draft

  Created: February 22, 2018

  Replaces: N/A


### Initial Tiered CRC and NORI token transfer

NORI tokens may be restricted (they cannot move from one wallet to another) or unrestricted
(they can move from one wallet to another). 

 * _unrestricted tokens_ can be exchanged for other currencies (fiat, crypto, etc.)
 
 * _restricted tokens_ can not be exchanged for other currencies.

Tiered CRCs have an associated rating equal to the short-term estimation error
of the model used to measure the ongoing carbon removal and storage.

For example, a CRC with a short-term estimation error of 40% with be a lower tier
than a CRC with a short-term estimation error of 20%.

Depending on the short-term estimation error of a CRC, an exchange of NORI
tokens for that CRC will result in a share of the NORI tokens being restricted.

The share of restricted tokens will equal the short-term estimation error.

Restricted tokens can be transitioned to unrestricted status. This process
is covered in the sections below.

### Incremental lifting of restrictions

Depending on processes dictated by the methodology associated with a retired CRC,
the short-term estimation error of that retired CRC can decrease.

When the short-term estimation error of a retired CRC is reduced, then the quantity
of restricted NORI tokens transfered during the sale of that CRC will be reduced
by the same amount by lifting restriction on some of those tokens.

For example, when 100 NORI tokens are exchanged for 100 CRCs with a +/- 40% short-term
estimation error, 40 of those NORI tokens will be restricted upon deliver to the
supplier. If after auditing, or some other process, that estimation error is reduced
10%, the restriction will be lifted on 30 of the NORI tokens.

_Note_: It's possible that the lowest acheivable estimation error will be greater
than +/- 0%, and we need to make sure that aspect is communicated.

### Surplus CRC Creation

In the event that final auditing indicates that more CO2 was removed and stored
than was reflected in the historical CRC generation, then additional CRCs will
be created.

These surplus CRCs will be tier-1 rated, and will be immediately tradeable.

These surplus CRCs will be split between the original supplier and
the [market risk mitigation account](section-???).

_Note_: The exact amount that is split between supplier and market risk
mitigation account still needs to be determined and may be dependent
on market dynamics, methodology, specific projects, etc.

_Note_: One way to calculate the split between supplier and mitigation account
is based on the size of the mitigation account. As it gets bigger, the
suppliers of a surplus retain more of the surplus.

### Deficit Settlement process

In the event that final auditing indicates that _less_ CO2 was removed and stored
than was reflected in the historical CRC generation, then the remaining restricted
NORI tokens will be used to purchase and retire additional CRCs.

If there are not enough remaining NORI tokens to cover the deficit, then
additional CRCs from the [market risk mitigation account](section-???) will
be retired to coer the rest.

_Note_: The only time the purchase of a CRC does not result in that CRC
being retired is when the purchase is performed by the market risk mitigation
account.

For example:

100 CRCs
--> 60 unrestricted NORI, 40 restricted NORI
--> audit says only 70 TCO2e were removed (30 CRC deficit)
--> 10 unrestricted NORI transfered to the supplier account, remaining 30 restricted NORI are transferred to the Risk Mitigation Account(NIP-???)[]
--> 30 restricted NORI used to retire 30 additional CRCs to cover the deficit queuing the tokens in the Market contract

100 CRCs
--> 60 unrestricted NORI, 40 restricted NORI
--> audit says only 50 TCO2e were removed (50 CRC deficit)
--> the 40 restricted NORI are transferred to the Risk Mitigation Account(NIP-???)[] used to retire 40 additional CRCs to cover the deficit
--> additional 10 CRCs of Tier 1 (`estimationTier=1`) retired from the risk mitigation account

100 CRCs
--> 60 unrestricted NORI, 40 restricted NORI
--> audit says 120 were removed (20 CRC surplus)
--> the 40 restricted NORI are transferred to the supplier's account
--> 20 CRCs are minted of Tier 1 (`estimationTier=1`) and transfered to the Suppliers account

_Note_: These are "strawdog discountrates. We need to talk about different estimation Tiers, what
each means in terms of estimation error/uncertainty and relate these
different verification procedures to the CRC Quality rating and unrestricted/restricted token ratios.
I need to include other folks in such a discussion.
