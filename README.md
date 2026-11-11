# stardome-sead-remote-signer

Public mirror of the **Stardome SEAD remote signer**: a software attestation
signer for hosts that cannot carry a Stardome hardware module (VPS, pod,
container). It produces attestations per schema **2.0.1** — the software-process
variant of the Stardome attestation scheme — as a vertical, sign-only tool that
sits *along the data chain*.

> **Status: planning.** No implementation has been published here yet. The design
> is being specified through OpenSpec changes in the SEAD repositories; see the
> public SEAD docs at
> [Stardome-technology/stardome-sead](https://github.com/Stardome-technology/stardome-sead)
> for the attestation scheme family (`stardome-cbor-schemes`).

## Git workflow
This repository follows GitHub Flow (https://docs.github.com/en/get-started/using-github/github-flow).
The authoritative rules for contributors and agents are in the `## Git workflow`
section of [AGENTS.md](AGENTS.md).
