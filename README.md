# NIPs
Nori Improvement Proposals (NIPs) describe standards for the Nori platform, including core protocol specifications, client APIs, and contract standards.

# Contributing
Reccomended:
 1. Review [NIP-1](NIP-1.md).
 2. Fork the repository by clicking "Fork" in the top right.
 3. Add your NIP to your fork of the repository. There is a [template NIP here](nip-X.md).
 4. Submit a Pull Request to Nori's [NIPs repository](https://github.com/nori-dot-eco/NIPs).
 
OR:

 1. Review [NIP-1](NIP-1.md).
 2. Add your NIP to the github [issues page](https://github.com/nori-dot-eco/NIPs/issues). There is a [template NIP here](nip-X.md).

Your first PR should be a first draft of the final NIP. It must meet the formatting criteria enforced by the build (largely, correct metadata in the header). An editor will manually review the first PR for a new NIP before merging it. Make sure you include a `discussions-to` header with the URL to a discussion forum or open GitHub issue where people can discuss the NIP as a whole, or the github issue it is linked to if that is the medium being leveraged.

If your NIP requires images, the image files should be included in a subdirectory of the `assets` folder for that NIP as follow: `assets/nip-X` (for nip **X**). When linking to an image in the NIP, use relative links such as `../assets/nip-X/image.png`.

Once your first PR is merged, we have a bot that helps out by automatically merging PRs to draft NIPs. For this to work, it has to be able to tell that you own the draft being edited. Make sure that the 'author' line of your NIP contains either your Github username or your email address inside <triangular brackets>. If you use your email address, that address must be the one publicly shown on [your GitHub profile](https://github.com/settings/profile).

When you believe your NIP is mature and ready to progress past the draft phase, you should do the following:

 - **When the draft of your NIP is complete**, open a PR [here](https://github.com/nori-dot-eco/nori/pulls) changing the state of your NIP to 'Final'. An editor will review your draft and ask if anyone objects to its being finalised. If the editor decides there is no rough consensus - for instance, because contributors point out significant issues with the NIP - they may close the PR and request that you fix the issues in the draft before trying again.

# NIP status terms
* **Draft** - a NIP that is open for consideration
* **Accepted** - a NIP that is planned for immediate adoption, i.e. expected to be included in the next major release
* **Final** - a NIP that has been adopted in a previous release
* **Deferred** - a NIP that is not being considered for immediate adoption. May be reconsidered in the future for a subsequent release
