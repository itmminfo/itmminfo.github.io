# Static site deploy package

Folder: outputs/static-site

## Co zawiera

- `/` - strona główna kierująca do kalkulatora.
- `/kalkulator-kosztu-obslugi-zamowien/` - kalkulator ROI.
- `/pakiet-roi-automatyzacji-ecommerce/` - strona sprzedażowa produktu.
- `/klub-roi-automatyzacji-ecommerce/` - strona membership MRR z CTA do `intent=klub_roi`.
- 3 strony SEO wspierające ruch organiczny.
- `robots.txt`
- `sitemap.xml`
- `_headers` - nagłówki bezpieczeństwa dla Cloudflare Pages.
- `_redirects` - kanoniczne redirecty na URL-e z końcowym slashem.
- polityka prywatności i regulamin dla wersji MVP.

## Ważne

Ten folder jest publiczny. Nie wrzucaj tutaj ZIP-a płatnego produktu. Plik produktu trzymaj osobno i dostarczaj go przez Gumroad, Stripe albo inny checkout.

## Przed publikacją

1. Podmień BaseUrl i linki launchu na prawdziwe wartości:

```powershell
.\work\build-static-site.ps1 `
  -BaseUrl "https://twojadomena.pl" `
  -ProductCheckoutUrl "https://gumroad.com/l/twoj-produkt" `
  -LeadFormUrl "https://tally.so/r/twoj-formularz"
```

2. Jeśli nie podajesz ich jako parametrów, w kalkulator-kosztu-obslugi-zamowien/index.html ustaw ręcznie:

- `formEndpoint`,
- `leadFormUrl`,
- `productCheckoutUrl`,
- prawdziwą politykę prywatności,
- GA4/GTM, jeśli używasz.

3. Po publikacji dodaj sitemap.xml do Google Search Console.

## Direct upload na Cloudflare Pages

Jeśli używasz Cloudflare Pages bez repo:

1. Spakuj albo wskaż folder outputs/static-site.
2. Build command: puste.
3. Build output directory: / albo outputs/static-site, zależnie od sposobu uploadu.
4. Po deployu sprawdź /robots.txt, /sitemap.xml i /kalkulator-kosztu-obslugi-zamowien/.
