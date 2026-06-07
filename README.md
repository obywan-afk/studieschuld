# DUO SF35 Studieschuld Calculator

An interactive Dutch student loan (SF35 leenstelsel) calculator — open in any browser, no server needed.

**Live:** [studieschuld.help](https://studieschuld.help)

## What it does

- **Bilingual NL / EN** — toggle in the header, preference saved in the browser
- **No ads, no tracking** — optional Buy-Me-a-Coffee support link, feedback flow, privacy page, `robots.txt`, and sitemap
- Calculates your monthly DUO payment (draagkracht vs wettelijk maandbedrag)
- Shows 35-year debt trajectory under three scenarios
- Models the ETF investment strategy (invest the freed-up amount instead of over-paying DUO)
- **Return sensitivity** (3 / 5 / 7 %) and inflation-adjusted "today's euros" values
- **Box-3 wealth tax** optionally applied to the investment portfolio
- **Partner & abroad context** — combined income with the partner threshold, foreign-income reporting note
- **Smart signals** — €0 reality check, overpayment detector, peiljaarverlegging eligibility
- Explains the three income zones: debt grows / shrinks / fully amortised
- Compares Strategy A (min payment + kwijtschelding 2060) vs Strategy B (always pay full annuity)
- Accounts for the SF35 €5 floor rule (Art. 6.10 lid 3 WSF 2000)
- Date-based interest lock calculation from your aanloopfase start year

## Key SF35 rules implemented

| Rule | Detail |
|---|---|
| Draagkracht | `4% × (inkomen − drempel) / 12` |
| €5 floor | Only pay if draagkracht > €5/mnd |
| Drempel 2026 | €26.819,42 (single) / €38.351,77 (partner) |
| Rate lock | 5 years from aanloopfase start, based on Oct–Sep 5yr bond avg |
| Kwijtschelding | Automatic after 35 years (Art. 6.16 lid 1 WSF 2000) |
| Aflosvrije periode | Max 60 months, extends end date 1:1 |

## Monetization

**Status: removed / parked.** The site currently ships **no ads and no tracking**. The earlier AdSense + sponsor-placeholder layer was pulled because it was only a placeholder — there is no verified ad partner and no cookie-consent flow yet. Shipping a "Advertentie / this space is reserved" box and loading the AdSense script before any of that exists added a third-party tracker for nothing.

What was removed (commit history has the full implementation at `f4d8343` if you want to restore it):

- the two `ad-card` placeholder `<aside>` blocks (top + bottom)
- the AdSense loader `<script>` in `<head>` and in `privacy.html`
- the `MONETIZATION` config object and `setupMonetization()` in `index.html`
- the `ad*` i18n strings and the `footerMonetization` footer line
- `ads.txt`

What stays: the voluntary **Buy Me a Coffee** support card, the feedback flow, `privacy.html`, `robots.txt`, and `sitemap.xml`.

### Before re-enabling ads

1. Have a real ad partner (approved Google AdSense account with live ad-unit slot IDs, or a signed direct sponsor).
2. Add a proper cookie-consent banner and update `privacy.html` **before** any tracking script loads.
3. Re-add `ads.txt` at the domain root with your real publisher ID.
4. Only then restore the placements (see `f4d8343`).

Lower-friction alternatives that need none of the above: the existing **Buy Me a Coffee** link, or **direct sponsorships** disclosed inline. Avoid anything that makes the calculator look like financial advice.

## Feedback collection

The feedback card opens the Tally form at `https://tally.so/r/81M5oo`. The site passes `source`, `lang`, and `page` query parameters so the form can capture where feedback came from if matching hidden fields are added in Tally.

## Sources

- [DUO Terugbetalen](https://www.duo.nl/particulier/terugbetalen/)
- [DUO Renteoverzicht](https://www.duo.nl/particulier/rente/rente-voor-terugbetalers.jsp)
- [WSF 2000](https://wetten.overheid.nl/BWBR0011453)

## Disclaimer

Scenario model only. Not legal or financial advice. Always verify via [Mijn DUO](https://mijn.duo.nl).
Post-lock rate (2,33%) is the 2026 published SF35 rate used as a scenario assumption — the actual 2028+ rate is unknown.
