```
  NIP: 1
      Title: NIP Purpose and Guidelines
      Status: Draft
      Type: Meta
      Author: Jaycen Horton<jaycen@nori.com>
      Created: 2017-12-07
```

What is a NIP?
--------------

NIP stands for Nori Improvement Proposal. At the most basic level a NIP is a proposal to modify, add, remove or interface in a standard way with the functionality that governs Nori’s underlying code or the interfaces that operate upon them. A NIP is a design document providing information to the Nori community, or describing a new feature for Nori or its processes or environment. The NIP should provide a concise technical specification of the feature and a rationale for the feature. The NIP author is responsible for building consensus within the community and documenting dissenting opinions.

NIP Rational
------------

We intend NIPs to be the primary mechanisms for proposing new features, for collecting community input on an issue, and for documenting the design decisions that have gone into Nori. Because the NIPs are maintained as text files in a versioned repository, their revision history is the historical record of the feature proposal.

NIPs are a convenient way to track the progress of the implementation of a feature, change or standard acceptance. Ideally each implementation maintainer would list the NIPs that they have implemented. This will give end users a convenient way to know the current status of a given implementation or library.

NIP Types
---------

There are three types of NIP:

-   A **Standard Track NIP** describes any change that directly changes the way Nori functions, such as a change to the smart contracts, a change in standards or requirements for interacting with Nori, proposed application standards and conventions for interfacing with Nori, or any change that directly affects logic that is served to external applications interfacing with Nori. Furthermore Standard NIPs can be broken down into the following categories.
    -   **Core** - improvements requiring an application fork, smart contract implementation of a core component such as a Carbon Removal Credit Commodity standard, or a smart contract upgrade, as well as changes that are not necessarily application critical but may be relevant to “core dev” discussions.
    -   **Interface** - includes improvements around client [API/SDK] specifications and standards, and also certain language-level standards like method names and [contract ABIs].
     -   **NRC** - application-level standards and conventions, such as report or data standards for Commodities (such as a [CRC]() report whose data is handled externally (such as in IPFS) but does not directly require a change in the smart contract logic itself, extensions to participant identity registry standards, URI schemes, library/package formats, IOT standards or standards relating to devices communicating or interfacing with Nori.

-   An **Informational NIP** describes a Nori design issue, or provides general guidelines or information to the Nori community, but does not propose a new feature. Informational NIPs do not necessarily represent Nori community consensus or a recommendation, so users and implementers are free to ignore Informational NIPs or follow their advice.

-   A **Meta NIP** describes a process surrounding Nori or proposes a change to (or an event in) a process. Process NIPs are like Standards Track NIPs but apply to areas other than the Nori platform itself. They may propose an implementation, but not to Nori's codebase; they often require community consensus; unlike Informational NIPs, they are more than recommendations, and users are typically not free to ignore them. Examples include procedures, guidelines, changes to the decision-making process relating to whitelisting or blacklisting projects or methodologies, and changes to the tools or environment used to interface with Nori APIs in a standard way. Any meta-NIP is also considered a Process NIP.

-   An **Methodology NIP** describe any Nori methodology process related to removing CO2 from the atmosphere. These define how Nori and community can account for the output of a particular methodology process. It does not or should not deal specifically with the process itself, and should instead define standards relating to the output from such. Methodologies can be broken into the following types.
    -   **Record Keeping**
    -   **Reporting**
    -   All Methodology types must define a sub-type referencing the process it is used for. **Sub-Type: I.E. Soil/Direct Air Capture/etc.**

NIP Workflow
-------------
The NIP repository Collaborators change the NIPs status. Please direct all NIP-related communications to the NIP Collaborators, which are listed under NIP Editors below. Also see NIP Editor Responsibilities & Workflow.

The NIP process begins with a new idea for Nori. It is highly recommended that a single NIP contain a single key proposal or new idea. The more focused the NIP, the more successful it tends to be. A change to one client doesn't require an NIP; a change that affects multiple clients, or defines a standard for multiple apps to use, does. The NIP editor reserves the right to reject NIP proposals if they appear too unfocused or too broad. If in doubt, split your NIP into several well-focused ones.

Each NIP must have a champion - someone who writes the NIP using the style and format described below (feel free to start with the template NIP), shepherds the discussions in the appropriate forums, and attempts to build community consensus around the idea.

Vetting an idea publicly before going as far as writing an NIP is meant to save the potential author time. Asking the Nori community first if an idea is original helps prevent too much time being spent on something that is guaranteed to be rejected based on prior discussions (searching the Internet does not always do the trick). It also helps to make sure the idea is applicable to the entire community and not just the author. Just because an idea sounds good to the author does not mean it will work for most people in most areas where Nori is used. Examples of appropriate public forums to gauge interest around your NIP include [the Nori subreddit], [the Issues section of this repository], and [one of the Nori chat rooms]. In particular, [the Issues section of this repository] is an excellent place to discuss your proposal with the community and start creating more formalized language around your NIP. 

Once the champion has asked the Nori community whether an idea has any chance of acceptance a draft NIP should be presented as a [pull request]. This gives the author a chance to continuously edit the draft NIP for proper formatting and quality. This also allows for further public comment and the author of the NIP to address concerns about the proposal.

If the NIP collaborators approve, the NIP editor will assign the NIP a number (generally the issue or PR number related to the NIP), label it as Standards Track, Informational, or Meta, give it status “Draft”, and add it to the git repository. The NIP editor will not unreasonably deny an NIP. Reasons for denying NIP status include duplication of effort, being technically unsound, not providing proper motivation or addressing backwards compatibility, or not in keeping with the Nori philosophy.

Standards Track NIPs consist of three parts, a design document, implementation, and finally if warranted an update to the [formal specification]. The NIP should be reviewed and accepted before an implementation has begun, unless an implementation will aid people in studying the NIP. Standards Track NIPs must be implemented in the main Nori repository master branch before it can be considered Final.

For an NIP to be accepted it must meet certain minimum criteria. It must be a clear and complete description of the proposed enhancement. The enhancement must represent a net improvement. The proposed implementation, if applicable, must be solid and must not complicate the platform unduly.

Once an NIP has been accepted, the implementations must be completed. When the implementation is complete and accepted by the community, the status will be changed to “Final”.

A NIP can also be assigned status “Deferred”. The NIP author or editor can assign the NIP this status when no progress is being made on the NIP. Once an NIP is deferred, the NIP editor can re-assign it to draft status when progress or updates return.

A NIP can also be “Rejected”. Perhaps after all is said and done it was not a good idea. It is still important to have a record of this fact.

NIPs can also be superseded by a different NIP, rendering the original obsolete.

The possible paths of the status of NIPs are as follows:




![](https://www.lucidchart.com/publicSegments/view/fc7322af-c2ac-4084-baf0-5b1d2cd6bdcf/image.jpeg)


Some Informational and Process NIPs may also have a status of “Active” if they are never meant to be completed. E.g. NIP 1 (this NIP).


What belongs in a successful NIP?
---------------------------------
Each NIP should have the following parts:

-   Preamble - RFC 822 style headers containing metadata about the NIP, including the NIP number, a short descriptive title (limited to a maximum of 44 characters), the names, and optionally the contact info for each author, etc.

<!-- -->

-   Simple Summary - “If you can’t explain it simply, you don’t understand it well enough.” Provide a simplified and layman-accessible explanation of the NIP.

<!-- -->

-   Abstract - a short (~200 word) description of the technical issue being addressed.

<!-- -->

-   Motivation (*optional) - The motivation is critical for NIPs that want to change the Nori market protocols, designs or behaviors. It should clearly explain why the existing protocol specification is inadequate to address the problem that the NIP solves. NIP submissions without sufficient motivation may be rejected outright.

<!-- -->

-   Specification - The technical specification should describe the syntax and semantics of any new or changed feature and its source. The specification should be detailed enough to describe any affected Nori components, such as internal smart contracts or external API impacts.

<!-- -->

-   Rationale - The rationale fleshes out the specification by describing what motivated the design and why particular design decisions were made. It should describe alternate designs that were considered and related work, e.g. how the feature might impact third party infrastructure such as client APIs. The rationale may also provide evidence of consensus within the community, and should discuss important objections or concerns raised during discussion.

<!-- -->

-   Backwards Compatibility - All NIPs that introduce backwards incompatibilities must include a section describing these incompatibilities and their severity. The NIP must explain how the author proposes to deal with these incompatibilities. NIP submissions without a sufficient backwards compatibility treatise may be rejected outright.
<!-- -->

-   Test Cases - Test cases for an implementation are mandatory for NIPs that are affecting core marketplace components or protocols that allow fluent participation and operation of all current participants or induce backwards compatibility issues. Other NIPs can choose to include links to test cases if applicable.
<!-- -->

-   Implementations - The implementations must be completed before any NIP is given status "Final", but it need not be completed before the NIP is accepted. While there is merit to the approach of reaching consensus on the specification and rationale before writing code, the principle of "rough consensus and running code" is still useful when it comes to resolving many discussions of API details.
<!-- -->

-   Copyright Waiver - All NIPs must be in public domain. See the bottom of this NIP for an example copyright waiver.

NIP Formats and Templates
-------------------------

NIPs should be written in [markdown] format. Image files should be included in a subdirectory for that NIP.

NIP Header Preamble
-------------------
Each NIP must begin with an RFC 822 style header preamble. The headers must appear in the following order. Headers marked with "*" are optional and are described below. All other headers are required.

` NIP: ` <NIP number> (this is determined by the NIP editor)

` Title: `<NIP title>

` Author: `<list of author's real names and optionally, email address>

` * Discussions-To: ` <email address>

` Status: `<Draft | Active | Accepted | Deferred | Rejected | Withdrawn | Final | Superseded>

` Type: `<Standards Track (Core, Interface, NRC)  | Informational | Process>

` Created: `<date created on, in ISO 8601 (yyyy-mm-dd) format>

` * Replaces: `<NIP number>

` * Superseded-By: `<NIP number>

` * Resolution: `<url>

The Author header lists the names, and optionally the email addresses of all the authors/owners of the NIP. The format of the Author header value must be

Random J. User &lt;address@dom.ain&gt;

if the email address is included, and

Random J. User

if the email address is not given.

Note: The Resolution header is required for Standards Track NIPs only. It contains a URL that should point to an email message or other web resource where the pronouncement about the NIP is made.

While an NIP is in private discussions (usually during the initial Draft phase), a Discussions-To header will indicate the mailing list or URL where the NIP is being discussed. No Discussions-To header is necessary if the NIP is being discussed privately with the author.

The Type header specifies the type of NIP: Standards Track, Meta, or Informational. If the track is Standards please include the subcategory (core, networking, interface, or ERC).

The Created header records the date that the NIP was assigned a number. Both headers should be in yyyy-mm-dd format, e.g. 2001-08-14.

NIPs may have a Requires header, indicating the NIP numbers that this NIP depends on.

NIPs may also have a Superseded-By header indicating that an NIP has been rendered obsolete by a later document; the value is the number of the NIP that replaces the current document. The newer NIP must have a Replaces header containing the number of the NIP that it rendered obsolete.

Auxiliary Files
---------------

NIPs may include auxiliary files such as diagrams. Such files must be named NIP-XXXX-Y.ext, where “XXXX” is the NIP number, “Y” is a serial number (starting at 1), and “ext” is replaced by the actual file extension (e.g. “png”).

Transferring NIP Ownership
--------------------------
It occasionally becomes necessary to transfer ownership of NIPs to a new champion. In general, we'd like to retain the original author as a co-author of the transferred NIP, but that's really up to the original author. A good reason to transfer ownership is because the original author no longer has the time or interest in updating it or following through with the NIP process, or has fallen off the face of the 'net (i.e. is unreachable or not responding to email). A bad reason to transfer ownership is because you don't agree with the direction of the NIP. We try to build consensus around an NIP, but if that's not possible, you can always submit a competing NIP.
If you are interested in assuming ownership of an NIP, send a message asking to take over, addressed to both the original author and the NIP editor. If the original author doesn't respond to email in a timely manner, the NIP editor will make a unilateral decision (it's not like such decisions can't be reversed).

NIP Editors
-----------

The current NIP editors are

` * Jaycen Horton (@jaycenhorton)`
` * Paul Carduner (@pcardune)`

` * Paul Gambill (@paulgambill)`

` * Aldyen Donnelly`

` * Christophe Jospe (@cjospe)`

` * Ross Kenyon`
` * Alexsandra Guerra`

NIP Editor Responsibilities and Workflow
--------------------------------------
For each new NIP that comes in, an editor does the following:

-   Read the NIP to check if it is ready: sound and complete. The ideas must make technical sense, even if they don't seem likely to be accepted.
-   The title should accurately describe the content.
-   Edit the NIP for language (spelling, grammar, sentence structure, etc.), markup (Github flavored Markdown), code style

If the NIP isn't ready, the editor will send it back to the author for revision, with specific instructions.

Once the NIP is ready for the repository, the NIP editor will:

-   Assign a NIP number (generally the PR number or, if preferred by the author, the Issue # if there was discussion in the Issues section of this repository about this NIP)

<!-- -->

-   Accept the corresponding pull request

<!-- -->

-   List the NIP in [README.md](https://github.com/nori-dot-eco/NIPs/blob/master/README.md)

<!-- -->

-   Send a message back to the NIP author with next step.

Many NIPs are written and maintained by developers with write access to the Nori codebase. The NIP editors monitor NIP changes, and correct any structure, grammar, spelling, or markup mistakes we see.

The editors don't pass judgment on NIPs. We merely do the administrative & editorial part.

History
-------

This document was derived heavily from [Bitcoin's BIP-0001] written by Amir Taaki which in turn was derived from [Python's PEP-0001]. In many places text was simply copied and modified. Although the PEP-0001 text was written by Barry Warsaw, Jeremy Hylton, and David Goodger, they are not responsible for its use in the Nori Improvement Process, and should not be bothered with technical questions specific to Nori or the NIP. Please direct all comments to the NIP editors.

December 8, 2017: First draft

Copyright
---------

Copyright and related rights waived via [CC0](https://creativecommons.org/publicdomain/zero/1.0/).







