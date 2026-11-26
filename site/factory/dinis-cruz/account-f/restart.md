# Restart

1. Read `CLAUDE.md`, then `site/factory/dinis-cruz/account-f/agent.json` and `now.md`.
2. Read the newest debrief in `board/customers/debriefs/` and `history/PROVENANCE.md` for where each file came from.
3. Make a new session key if the old one is gone (openssl, P-256 signing, RSA-4096 encryption; private halves mode 600 outside the repository), publish the public half in `site/keys/` alone in its own commit, and set git to sign with it (`gpg.format ssh`, `gpg.ssh.program ssh-keygen`, `commit.gpgsign true`).
4. Attach PrompTugal__News__Website (push) beside this repository and follow its CLAUDE.md.
5. Work on `dev` only. Trailers on every commit: `Agent: cl-6.customers@PrompTugal.dinis` and `Claude-Session: <session URL>`.
6. Update `agent.json` before ending.
