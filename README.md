# ORN Europe – handover site

A private handover site for Raj Kumar, served by GitHub Pages at
https://orngroup.github.io/ajaykawa/

Everything on the site (the handover text, the document list and every uploaded file) is
encrypted in the browser with AES-256 before it reaches GitHub. The repository only ever
holds `index.html`, this README and encrypted files (`keys.json`, `content.enc`, `vault/`).
Without a passphrase the files are unreadable, so the repository can stay public.

## One-off set-up (Ajay)

1. **Create the repository.** In the `orngroup` account create a repository called `ajaykawa`
   (Public – GitHub Pages is free for public repositories). Upload **only** `index.html` and
   `README.md`. Do **not** upload `handover-content.json` – it is not encrypted.
2. **Switch on Pages.** Settings → Pages → Source: *Deploy from a branch* → branch `main`,
   folder `/(root)` → Save. After a minute the site is live at the address above.
3. **Create an upload token.** github.com/settings/personal-access-tokens/new
   - Resource owner: `orngroup`
   - Repository access: *Only select repositories* → `ajaykawa`
   - Repository permissions → **Contents: Read and write** (nothing else)
   - Expiration: 90 days
   If `orngroup` is an organisation, an owner may need to approve the token
   (Organisation settings → Personal access tokens).
4. **Run set-up.** Open the site. It shows a set-up screen. Enter the token, your name,
   a passphrase of at least 14 characters, and choose `handover-content.json`. Click
   *Encrypt and save*. The handover text and the six Word documents are encrypted and saved.
5. **Give Raj access.** Admin → *Who can open the handover* → add **Raj** with his own
   passphrase. Tell him the passphrase by phone, not WhatsApp or email.
6. **Delete `handover-content.json`** from your Downloads once set-up has worked.

## Day to day

| Who | Needs | Can do |
|---|---|---|
| Raj (reader) | Site address + his passphrase | Read every section, view and download documents, print |
| Ajay (admin) | Passphrase + GitHub token (“Admin: connect GitHub” on the sign-in screen) | Everything above, plus upload and delete documents, edit page text, add or remove people |

- **Upload documents:** Admin → choose a section (e.g. *Staffing*, *ORN Europe office*,
  *GitHub files*) → choose files → *Encrypt and upload*. Up to about 50 MB per file.
- **Fill in red items:** open a page → *Edit this page* → click into the text or table and
  type → *Save changes*. The red count in the menu goes down as items are filled.
- **Updated handover from Claude:** Admin → *Update handover text* → choose the new JSON file.
  Uploaded documents are kept.

## Good to know

- The passphrase is the only lock. Use a long one (four or five random words works well).
  If every passphrase is lost the content cannot be recovered.
- Removing a person stops them opening the current site, but older copies of `keys.json`
  remain in the Git history. If someone must lose access completely, rebuild the site with a
  new passphrase (new repository, run set-up again, re-upload documents).
- The GitHub token gives write access. Never share it; Raj does not need one.
- Uploads normally appear for other people within a minute.
