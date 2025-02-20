# Zebra Collaboration

In order to successfully deploy a protocol upgrade to Zcash with Crosslink many things have to come together. From the perspective of the Shielded Labs engineering team, (TODO: insert intro text here).

## Zebra Prototype

Our engineering work centers around creating a working prototype of the new Crosslink protocol using the `zebra` codebase. During this prototype phase, we are likely to have many changes to Zebra that would not be appropriate to merge into the main repository. Later, if the protocol changes are generally acceptable to the Zebra team and we've improved the prototype code to become production quality, we hope the Zebra team can merge those changes. 

During the prototype phase, we will be operating independent Cross-link-specific Continuous Integration, and also working to back/forward-porting some of our work between the repositories.

### Crosslink Continuous Integration

Our Continuous Integration approach has these elements:

1. We will have new, prototype-specific builds and testing automated by Github actions.
2. We will _not_ exercise most of the upstream CI.
  - Rationale:
    - It is complex and heavyweight both to configure, execute, and pay for.
    - It may be difficult to maintain and to ensure it is configured correctly without silent misconfiguration mistakes.
    - We prefer a quick automated test system for rapid iterations.
    - We believe we can rely on upstream CI on occasion (see next).
3. We would like to occasionally submit "Draft PRs" of our prototype to upstream to receive a thorough regression analysis, pending their cooperation.
  - When this process reveals regressions against upstream, we will create tightly-scoped automated deterministic regression tests to capture that in our prototype CI.

### Revision Control Management

#### Repostory Structure

We have created a github fork of [zebra](https://github.com/ZcashFoundation/zebra) which we call the "staging" which lives at `https://github.com/ShieldedLabs/zebra-crosslink-staging`. From the staging fork, we've created a "working" fork which lives at `https://github.com/ShieldedLabs/zebra-crosslink`. 

The motivation for this structure is to overcome a UX snag where the new PR creation flow, by default, targets the fork's immediate origin, so if we had only a single fork, it's likely we'd accidentally submit prototype PRs against upstream Zebra. 

#### Porting from Upstream

Our goal for the prototype phase, in addition to meeting all the Crosslink-specific goals, is to ensure we're prototyping on recent Zebra updates. Also, in the post-prototype phase we want to ensure we can easily submit PRs to upstream that are acceptable (thus they should incorporate recent upstream changes without conflict). To achieve these goals we will frequently rebase our changes against upstream.

This implies our prototype is maintained as a linear extension extending from upstream's `main`.

#### Submitting Changes to Upstream

Whenever we create/review a PR for our prototype, we want to ask "is this a non-crosslink specific change that upstream may merge nowish"?

If so, we prioritize submitting those changes to upstream, _even though_ in the short term this slows down prototype feature progress. In the long term we hope it pays off substantially by simplifying the eventual Crosslink PRs.

Our current manner of doing this will be to manually recreate the necessary changes to submit to upstream, rather than relying on cherry picking, github features, etc... We will refine the process as we learn from it.
