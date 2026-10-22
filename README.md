# auqr.no — statisk nettside

To sider, ingen byggesteg, ingen sporing, ingen tredjepartsskript. Driftes gratis på GitHub Pages;
eneste kostnad er domenet hos Domeneshop.

| Fil | Hva |
|---|---|
| `index.html` | Forside: hovedsetning + «Kontakt oss», inkl. schema.org-data (Organization) for Google og KI-søk |
| `om-oss.html` | Team med bilde og beskrivelse, navnet; kontaktinfo kun på Rune Stenseth |
| `bilder/` | Profilbilder (kvadratiske, ca. 400×400). Mangler et bilde, vises initialer |
| `bilder/bakgrunn.jpg` | Bryggene langs Nidelva, Trondheim. Foto: Arne Marius Kirknes, [Unsplash](https://unsplash.com/photos/_4bq-n5eTos) — Unsplash-lisens, fri kommersiell bruk |
| `logo.svg` | Auqr-logoen i originalfarger, tegnet etter offisiell logofil |
| `robots.txt`, `sitemap.xml`, `llms.txt` | For søkemotorer og språkmodeller. Oppdater `lastmod` i sitemap ved endringer |
| `CNAME` | Forteller GitHub Pages at siden skal svare på `www.auqr.no` |

Forhåndsvisning lokalt: `python -m http.server 8381 --directory auqr-nettside`

## Publisering

Repo: `Auqr-no/nettside`, GitHub Pages fra grenen `main`, rotmappen. En push til `main` publiserer
endringen i løpet av et minutt.

DNS hos Domeneshop:
- `www` CNAME → `auqr-no.github.io`
- `auqr.no` (uten www) A-poster → `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
  (GitHub sender da `auqr.no` videre til `www.auqr.no`)
- MX, SPF, DKIM og autodiscover (M365) skal ikke røres.

## Synlighet i søk og KI

1. **Google Search Console**: legg til domeneegenskap `auqr.no`, verifiser med TXT-post i Domeneshop,
   send inn `https://www.auqr.no/sitemap.xml`, be om indeksering av forsiden.
2. **Bing Webmaster Tools**: importer fra Search Console (ett klikk). Bing driver ChatGPT-søk og Copilot.
3. **LinkedIn-side** for Auqr AS som lenker til auqr.no; teamets profiler lenker til selskapssiden.
4. Når LinkedIn-siden finnes: legg URL-en inn som `"sameAs": ["https://www.linkedin.com/company/…"]`
   i JSON-LD-blokken i `index.html`.
5. Sjekk etter 1–2 uker: søk «Auqr» på Google og Bing, og spør ChatGPT/Claude med nettsøk «Hva er Auqr?».
