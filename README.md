# Personality AI

**Nothing has been built here yet.** This repository is a reserved name for
a personality-AI property. It holds one workflow — secret scanning, through the estate's shared
template — and this file.

An empty repository with no README is indistinguishable from an abandoned one,
which is the only reason this file exists. When the first real push lands, it
should be replaced by a description of what the property actually is.

## Before code lands here

Two things are wrong today and are cheaper to fix now than after there is a
deploy to disturb.

**The default branch is `claude/gord-directory-spec-3jx7zk`**, an agent's scratch branch. Work
pushed to `main` in a repository like this deploys nothing and is read by
nobody, and the failure is silent — the push succeeds. Whoever starts work here
should set the default to a real trunk first. Only a person can: it is a GitHub
setting, and Vercel carries a separate Production Branch setting that has to
agree with it.

**It is not in the mesh.** A property in this estate holds six things — a
charter, that charter served at `/.well-known/flashyos-charter.json`, a
`flashyos/1` handshake, a `frontdoor/1` door, both record emitters, and a
directory fragment that declares its served surfaces. `docs/onboarding.md` in
flashyos is the plan and the order; `npx @flashyos/conformance init` writes the
first three.

Estate-wide house rules are in `CLAUDE.md`.
