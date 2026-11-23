# CSI Robot Research Workspace

A password-encrypted research task board based on the CSI World workspace. Eight stages cover benchmark selection, model baselines, three harness toy experiments, optional PEAR LoRA training, held-out evaluation, and reporting. The initial vault contains 57 actionable tasks, each with a completion criterion. All experimental tasks start uncompleted; there are no fabricated performance results.

## Open and collaborate

Serve the repository root through HTTPS or localhost. Enter the separately supplied workspace password. Task checks, notes, stage ownership, dates, benchmark records, feedback and attachments are saved to encrypted browser-local IndexedDB. To share edits, use a fine-grained GitHub token scoped to this repository with Contents read/write permission: open collaboration settings, apply the token, fetch shared progress, then edit and publish. Tokens stay in page memory. The access password is not a GitHub account credential.

Unsaved-to-GitHub edits are local to that browser. Publishing checks the remote file SHA and stops on concurrent changes, exporting a backup instead of overwriting. Export encrypted backups regularly. All password holders have the same editing role.

## Encryption and files

Research content and attachments in `data/vault.json` are AES-256-GCM encrypted with PBKDF2-SHA256 (310,000 iterations, fresh random salt and IV). Source code contains no plaintext password or embedded GitHub credentials. Password strength determines offline resistance; this is an encrypted static workspace, not server authentication. Never paste API keys into notes. Single attachments are limited to 15 MB and the total to 35 MB; use links for large videos.

## Host

GitHub Pages can serve `main` from `/`. The repository starts private; publication never requires automatically making it public. If the organization plan does not support private-repository Pages, upgrade the plan or explicitly choose another hosting arrangement. To preview locally, run `python3 -m http.server 8000` in this directory.

## Experimental interpretation

Ld is the offline closed-model harness designer; Le is a closed runtime executor/checker. C-student uses a frozen PEAR checkpoint and a PEAR-specific harness with no closed runtime model. Toy D is optional LoRA on the same PEAR-27B, evaluated with a fixed harness and a matched ordinary-SFT control. Proposed episode counts are pilot budgets, not completed runs or a statistical power guarantee. Separate model pretraining exposure from this project's dev/validation/test split. All search, repeated incumbent runs, validation, collection, training and test costs must be accounted for.

Paper citation/star figures are a dated 2026-11-23 snapshot, not live counters. The encryption password must be provided separately. Changing it requires re-encrypting the vault and migrating backups.
