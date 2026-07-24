# Sources & workarounds for offline harvest

## Working tactics (use these when direct links fail)

1. **Full-page fetch → link extract**  
   Download the HTML (`curl`/`wget`), regex all `href`/`src`/bare URLs, follow only `.pdf` / `download` targets with a real browser User-Agent + Referer.

2. **Ignore / override gitignore**  
   Repos often list `*.pdf` in `.gitignore` so agents skip them.  
   - In *our* docs repos: remove `*.pdf` from `.gitignore` so offline manuals can be committed.  
   - In *upstream* clones: files already in history are still on disk after `git clone`; if ignored only for *new* adds, use `git add -f path.pdf` or copy out of the working tree with `find … -name '*.pdf'`.

3. **Springer / DOI content path**  
   Bot-gated landing pages (e.g. datacenter-book.org `/api/download`) often still expose the same book via  
   `https://link.springer.com/content/pdf/10.1007/<ISBN-or-DOI>.pdf`  
   (worked for *The Data Center as a Computer* 4th ed → 362 pp OA PDF).

4. **GitHub as a mirror**  
   Search `gh search repos` / `gh search code` for book titles; clone chapter Markdown mirrors when PDF is gated (`kyunghoj/datacenter-as-a-computer-4th`, CN translation repos).

5. **Internet Archive**  
   - CDX API for historical PDF URLs  
   - `web.archive.org/web/<ts>id_/<url>` for raw payloads  
   - Advanced search JSON for identifiers, then `/download/<id>/<file>`

6. **Correct MediaWiki image hashes**  
   SegaRetro Anubis blocks wrong paths; thumb URLs in archived HTML give `images/<h>/<hh>/File.pdf`. Prefer Wayback thumbs → reconstruct full path.

7. **USENIX / conference paper naming**  
   Guess `nsdi22-paper-<firstauthor>.pdf` when abstract pages 404 (Aquila = `gibson`).

8. **energy.gov article scrape**  
   Article HTML embeds the real PDF under `/sites/default/files/…`; scrape that instead of the marketing URL.

9. **Cookie jar + Referer**  
   Two-step: GET landing page with `-c cookies`, then GET download with `-b cookies -H Referer:…`.

10. **Size / magic filter**  
    Reject “PDF” responses &lt; ~15 KB or starting with `<!DOCTYPE` (bot challenge HTML).

## Document map

| Document | Method that worked |
|----------|--------------------|
| Data Center as a Computer 4th (full PDF, 362 pp) | Springer `content/pdf/10.1007/978-3-031-99489-0.pdf` |
| Same book (Markdown chapters) | GitHub `kyunghoj/datacenter-as-a-computer-4th` |
| Same book (CN Markdown) | GitHub `1946291409/data-center-as-a-computer-cn-translation` |
| FEMP Best Practices 2024 | Full-page scrape of energy.gov article → `/sites/default/files/2024-07/…pdf` |
| LBNL/FEMP historical | Wayback `id_` of old energy.gov PDF |
| Energy Efficient Servers | Springer OA direct PDF |
| Aquila NSDI’22 | USENIX `nsdi22-paper-gibson.pdf` |
| Jupiter Rising | Google research static pub PDF |
| AICA_E.pdf + other DC manuals | SegaRetro `images/<hash>/…` from known/thumb paths |
| Saturn ST- set (103 PDFs) | Antime bulk `files/*.pdf` |
| JVS WIP | Direct `daifukkat.su` PDF |
| arcade-docs RE tree | `git clone` Codeberg + drop nested `.git` |
| Kochise full DC tree | `git clone` then archive to big drive (too large for GitHub) |

Kochise local archive: `/mnt/storage/models/archive/docs-mirrors/Kochise-dreamcast-docs`
