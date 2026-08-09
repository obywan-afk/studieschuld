# studieschuld

A bilingual calculator for people repaying a Dutch DUO student loan under the
SF35 system.

**Try it:** [studieschuld.help](https://studieschuld.help)

It runs entirely in the browser. There is no account, server-side calculation,
advertising, or tracking.

## What it helps with

- Estimate the monthly payment from the statutory amount and draagkracht
- See a 35-year repayment path under different income and return assumptions
- Compare minimum repayment with paying the full annuity
- Account for partner income, living abroad, Box 3 tax, inflation, and the
  `€5` payment floor
- Check situations such as a `€0` payment or possible peiljaarverlegging

The calculator is available in Dutch and English. The interface and calculation
live in plain HTML, CSS, and JavaScript, so you can also download the repository
and open `index.html` locally.

## Sources

- [DUO: Terugbetalen](https://www.duo.nl/particulier/terugbetalen/)
- [DUO: Renteoverzicht](https://www.duo.nl/particulier/rente/rente-voor-terugbetalers.jsp)
- [Wet studiefinanciering 2000](https://wetten.overheid.nl/BWBR0011453)

## Note

This is a scenario tool, not legal or financial advice. Check the result against
[Mijn DUO](https://mijn.duo.nl), especially when your situation is unusual or a
rate has changed.
