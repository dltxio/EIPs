---
eip: <to be assigned>
title: Blockchain based invoices
author: Lucas Cullen (@BitcoinBrisbane)
discussions-to: <URL>
status: Draft
type: <Standards Track (Core, Networking, Interface, ERC)  | Meta | Informational>
category (*only required for Standard Track): <Core | Networking | Interface | ERC>
created: 2020-03-03
---

## Simple Summary
Define a smart contract interface for PEPPOL Service Providers to implement the Australia-New Zealand extension of the PEPPOL BIS 3.0 Specification.  A-NZ PEPPOL BIS 3.0

## Abstract
Recently (Novemeber 2019), the Australian Tax Office (ATO) announced an XML specification for e-Invoicing.  The ATO states "E-invoices can be sent directly to a customer’s software if both systems are using the same standards, even if the buyer and supplier are using different software. In Australia, we are working with the software industry to use the Peppol standard, which is internationally established."

"Within this repository is a range of artefacts that will help PEPPOL Service Providers implement and adopt the Australia-New Zealand extension of the PEPPOL BIS 3.0 Specification."

## Motivation
If an invoice interface was standardised, it would allow development of smart contracts with respect to

* Debt financing
* Tax reporting obligations
* Smart contract based condtions, such as interest and other penalties


## Specification
<!--The technical specification should describe the syntax and semantics of any new feature. The specification should be detailed enough to allow competing, interoperable implementations for any of the current Ethereum platforms (go-ethereum, parity, cpp-ethereum, ethereumj, ethereumjs, and [others](https://github.com/ethereum/wiki/wiki/Clients)).-->
The technical specification should describe the syntax and semantics of any new feature. The specification should be detailed enough to allow competing, interoperable implementations for any of the current Ethereum platforms (go-ethereum, parity, cpp-ethereum, ethereumj, ethereumjs, and [others](https://github.com/ethereum/wiki/wiki/Clients)).


```javascript
contract Invoice {
  public unit IssueDate;
  public unit DueDate;
  public int InvoiceTypeCode;
  public int InvoicePeriod;
  public uint Price;
  
  public days PaymentTerms; //days
  
  
}
```

## Rationale
<!--The rationale fleshes out the specification by describing what motivated the design and why particular design decisions were made. It should describe alternate designs that were considered and related work, e.g. how the feature is supported in other languages. The rationale may also provide evidence of consensus within the community, and should discuss important objections or concerns raised during discussion.-->
The rationale fleshes out the specification by describing what motivated the design and why particular design decisions were made. It should describe alternate designs that were considered and related work, e.g. how the feature is supported in other languages. The rationale may also provide evidence of consensus within the community, and should discuss important objections or concerns raised during discussion.-->

The ATO has defined the interface using XML https://github.com/A-NZ-PEPPOL/A-NZ-PEPPOL-BIS-3.0/tree/master/Message%20examples.  This EIP aims to port that interface into `Solidity` based smart contracts.

## Backwards Compatibility
<!--All EIPs that introduce backwards incompatibilities must include a section describing these incompatibilities and their severity. The EIP must explain how the author proposes to deal with these incompatibilities. EIP submissions without a sufficient backwards compatibility treatise may be rejected outright.-->
All EIPs that introduce backwards incompatibilities must include a section describing these incompatibilities and their severity. The EIP must explain how the author proposes to deal with these incompatibilities. EIP submissions without a sufficient backwards compatibility treatise may be rejected outright.

## Privacy concerns

It is noted that a companies unqiue identifier, in this case the Australian Business Number (ABN).  If this is made public, competitor could calcuate business revenue, profit etc.

## Test Cases
<!--Test cases for an implementation are mandatory for EIPs that are affecting consensus changes. Other EIPs can choose to include links to test cases if applicable.-->
Test cases for an implementation are mandatory for EIPs that are affecting consensus changes. Other EIPs can choose to include links to test cases if applicable.

## Implementation
<!--The implementations must be completed before any EIP is given status "Final", but it need not be completed before the EIP is accepted. While there is merit to the approach of reaching consensus on the specification and rationale before writing code, the principle of "rough consensus and running code" is still useful when it comes to resolving many discussions of API details.-->
The implementations must be completed before any EIP is given status "Final", but it need not be completed before the EIP is accepted. While there is merit to the approach of reaching consensus on the specification and rationale before writing code, the principle of "rough consensus and running code" is still useful when it comes to resolving many discussions of API details.

### Relevante sections from the ATO xml

#### Payment Terms
https://github.com/A-NZ-PEPPOL/A-NZ-PEPPOL-BIS-3.0/blob/master/Message%20examples/AU%20Invoice.xml#L193

#### Tax Total
https://github.com/A-NZ-PEPPOL/A-NZ-PEPPOL-BIS-3.0/blob/master/Message%20examples/AU%20Invoice.xml#L213

## References
https://softwaredevelopers.ato.gov.au/e-invoicing
https://www.ato.gov.au/Business/E-invoicing/In-detail/E-invoicing-accredited-provider-list/
https://github.com/A-NZ-PEPPOL

## Copyright
Copyright and related rights waived via [CC0](https://creativecommons.org/publicdomain/zero/1.0/).
