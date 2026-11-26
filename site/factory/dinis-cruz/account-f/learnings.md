# Learnings (from the history; see `history/board/team/customers/debriefs/`)

- Never print a lane or inbox token, even when debugging: it happened once (6 Nov) and is on the record in `history/board/team/customers/incidents/`.
- Apple's buy pages load prices by script, but the price data is in the page source (`"fullPrice"`); read it with curl and a small parser.
- Apple Business Manager is now "Apple Business"; use support.apple.com/guide/business/ for its guides.
- A personal Apple Account for an agent is not what Apple's terms describe, and a released device must be erased: both limit a "set-up iPad" product.
- riskmandate.ai's own price levels constrain any bundle: check a proposal against them.
- Relayed briefs come as session messages from the conductor; the memo committed on dev is the record of Dinis's words.
- A `.html` source in the gate is treated as a page: keep deck sources as `.htm`.
- Setup: `ssh-keygen` may be missing in the container; `apt-get install -y openssh-client` fixes it. Key fingerprints are the first 16 hex of sha256 over the DER public key.
