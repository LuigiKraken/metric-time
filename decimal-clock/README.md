# Decimal Clock Widget

The way we divide time is largely arbitrary — a patchwork of Babylonian base-60, Roman calendar reforms, and religious epoch choices. This clock keeps the familiar names (months, days) but reorganizes everything into a clean base-10 structure that actually makes sense:

- **10 months** per year (365 days, alternating 36/37 days)
- **10 weeks** per month
- **10 days** per week
- **10 hours** per day
- **100 minutes** per hour
- **100 seconds** per minute

The year count is offset so that year 0 aligns with roughly 100,000 years ago — the era of early shared human culture in prehistory, a more honest anchor for "when civilization started" than the birth of any one figure. You don't need to remember the offset; you just prepend a 10 to your life. 2026 becomes 102,026.

## Themes

Cycle through styles with the **Style** button:
- **CRT** — green phosphor scanline
- **Dark** — amber glow
- **Minimal** — clean light
- **7-SEG** — red seven-segment LED display

## Use as Home Screen Widget

1. **Serve the app** (required for iOS Add to Home Screen):
   ```bash
   npx serve .
   ```
   Or use any local web server. Open the URL on your phone.

2. **Add to Home Screen:**
   - **iOS:** Safari → Share → Add to Home Screen
   - **Android:** Chrome → Menu (⋮) → Add to Home screen

3. Open the icon for a full-screen decimal clock.
