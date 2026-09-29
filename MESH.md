# On the FlashyOS mesh

Personality Ai is a site on the FlashyOS mesh — a generated property whose every claim is tied to a surface a stranger can reach.

Its AAO charter is [`flashyos.roles.json`](flashyos.roles.json) — the single source the mesh
handshake and the directory fragment derive from, so two hand-written files can
never disagree. It declares **five roles**, and five roles are five agents:

| Role | Family | Human approval at/above | What it is accountable for |
|---|---|---|---|
| `editor` | product | MEDIUM | Decides what the site says and keeps every claim tied to a surface a stranger can reach — no unverified audience claim, no number a test cannot assert. |
| `author` | support | MEDIUM | Writes and updates the content in the estate lexicon, and keeps a page current rather than letting it drift from what the product now does. |
| `engineering` | engineering | HIGH | Builds and maintains the site generator, and keeps the served output derived from source rather than hand-edited. |
| `release` | operations | MEDIUM | Deploys the site and verifies the change is actually live at the domain, because committed is not served until a fetch settles it. |
| `conformance` | risk | LOW | Runs the content, link and lexicon checks, and refuses a build that links a surface which does not exist. |

The charter validates against the estate's dependency-free AAO checker:

```bash
node vendor-aao-check.mjs validate flashyos.roles.json   # 0 issues
```

**Becoming a live organisation.** The charter is what a live org is provisioned
from. From a machine that holds `DATABASE_URL`:

```bash
npx tsx packages/api/scripts/provision-org-from-charter.ts \
  --charter flashyos.roles.json --tier FREE
```

The FREE tier allows five agents, which is exactly this charter's five roles.
Provisioning is a database write a person runs; committing the charter is the
half a repository can hold. The authoritative conformance check runs against the
live domain after deploy: `npx @flashyos/conformance <domain> --level 2`.

`directory.fragment.json` is this org's `directory/1` node: the org, one agent
per role, and the accountable person.
