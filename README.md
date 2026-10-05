# issue.fund public frontend

Static website served at **https://issue.fund/** through GitHub Pages. This repository starts with fresh history and contains only the reviewed public website artifacts and their font licenses.

## Contents and provenance

The initial export is based on the previously public Pages artifact at commit `36b8ec5456e1fe4e1c35c172877767db71865607`, built from source commit `175c8e782c1ea46c397331119207446971716a35`. The original Git history is not included.

The deployed HTML, JavaScript, CSS, images, fonts, public Gnosis deployment configuration and GitHub DKIM public key were copied from that artifact. Documentation links and the developer-access notice were adapted for the repository split. No application behavior, contract address, ABI, backend endpoint or wallet transaction logic was changed.

`site-version.json` identifies this static export. `SHA256SUMS` records its files. This is a compiled artifact repository; it does not include the private application build toolchain, backend, contract source, operational records, credentials or personal research files.

## Preview and validation

Serve the repository at a domain root, for example:

```sh
python3 -m http.server 4177 --bind 127.0.0.1
# Open http://127.0.0.1:4177/
shasum -a 256 -c SHA256SUMS
```

The bundle uses absolute `/assets/` and `/brand/` paths. A GitHub Pages repository-subpath URL is not a supported application preview. Pages publishes `main` at `/`, with `.nojekyll` and the custom domain `issue.fund`.

Verify the homepage, `/#docs`, a bounty deep link, the public configuration JSON, and all loaded assets over HTTPS after each update. Wallet transactions are not part of smoke testing.

## Documentation and source access

Public user guides are embedded in the frontend and available at https://issue.fund/#docs. Links to restricted core source and historical operator records explain the access requirement at `/source-access.html`. Core developer commands require authorized access. Website issues can be reported in this repository’s issue tracker. Do not include private credentials or personal email receipts.

## Updating the export

1. Build the static frontend in an authorized core checkout using its locked dependencies and static build instructions.
2. Stage only the HTML, required hashed JS/CSS, referenced images/fonts, font license files, and reviewed public runtime configuration in a clean temporary directory. Include no history, source maps, personal bookmarks, environment files or operational material.
3. Review every changed file and its links, scan for credential material, and apply the public source-access link policy. Retain the existing production addresses and endpoints unless separately authorized.
4. Update provenance and file hashes, validate the served site at a domain root, then commit the exact reviewed export here.
5. Verify the Pages build and live HTTPS site before considering the release complete. Retain the previous artifact commit for rollback.

The Inter, Space Grotesk and Anton license notices remain alongside their font files. No additional license is granted here for other materials.
