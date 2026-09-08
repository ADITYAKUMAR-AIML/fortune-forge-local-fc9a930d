# Hooker & Millions — finish the playable frontend

## Goal

Turn the existing local game engine into a complete, playable desktop-first browser game at `/`, without adding backend services, authentication, network calls, or changing the game into a marketing page.

## Build scope

1. **Playable game shell**
   - Replace the blank home placeholder with the actual game screen.
   - Add a persistent left navigation and compact top status bar for day, lifestyle, reputation, cash, bank, net worth, market condition, and the main “Advance day” action.
   - Add responsive fallback behavior so the same screens remain usable on narrower displays.

2. **All planned screens**
   - Dashboard: wealth summary, income/expense pulse, progression toward the next lifestyle, current modifiers, recent events, and recent transactions.
   - Acquire: catalogue-only fictional adult collection, with search, country/category/tier/rarity/price filters, sorting, locked/available/owned states, requirements, local placeholder imagery, and safe acquire actions. Keep every character 18+ and strictly non-explicit.
   - Businesses: purchase cards, ownership/locked states, level, daily income/cost, upgrade cost, and upgrade actions.
   - Stock Market: market condition, sector/company rows, live prices from state, risk/volatility, owned shares, average cost, profit/loss, and buy/sell controls with integer-share validation.
   - Investments: principal, type, expected return/risk, duration, liquidity, active/matured status, locked-term messaging, and investment actions.
   - Properties and Assets: reusable catalogue cards with price, maintenance, lifestyle/reputation bonuses, requirements, ownership, and purchase actions.
   - Events and Transactions: separate readable activity views with day, category, description, amount, and balance-after details.
   - Save and Debug: export/import/reset controls, last-saved status, manual day advance, money adjustment, market forcing, random event trigger, and a collapsible current-state inspection area clearly labeled DEBUG.

3. **Frontend wiring and guardrails**
   - Extend the existing `useGame` action surface only where the planned controls need it, including market forcing and safe debug-only money adjustments.
   - Keep all mutations routed through the existing engine/economy functions so duplicate purchases, insufficient funds, invalid shares, locked investments, and requirements remain protected.
   - Show clear in-game feedback after successful or rejected actions without introducing a backend or external API.
   - Use the existing localStorage save system and browser file APIs for persistence.

4. **Visual direction and local media**
   - Refine the existing tokens into the requested black, burgundy, deep magenta, dark purple, silver/white, and gold-highlight luxury palette; keep all component styling token-based.
   - Add restrained glitter/particle texture, glass panels, glowing borders, shadows, and motion that support scanning the game rather than obscuring controls.
   - Add local placeholder media files for every referenced image path under the planned asset directories, with no external image URLs and no final artwork generation.

5. **Metadata and cleanup**
   - Give the home route its own Hooker & Millions title, description, Open Graph title/description/type, and Twitter card metadata.
   - Replace the generic root metadata so the app no longer presents as “Lovable App” or “Lovable Generated Project.”
   - Update the roadmap to reflect the completed foundation, playable screens, and verification status.

## Verification

- Open `/` and confirm the placeholder is gone and the dashboard renders with the initial state.
- Exercise navigation, acquire/purchase/upgrade actions, duplicate protection, stock buy/sell, locked investment behavior, advance-day income/expenses/events, lifestyle changes, save/export/import/reset, debug market forcing, and debug money adjustment.
- Check desktop and narrower layouts, browser console/runtime diagnostics, and the production build.
- Confirm all images resolve locally and no backend, authentication, database, API, cloud, or external network dependency was introduced.
