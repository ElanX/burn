# $tockBurn changelog

Every published build of $tockBurn (https://elanx.github.io/burn/), newest first. Each entry is dated and keyed to the build's in-app stamp; older entries also carry the git commit hash. Going forward, an entry is added in the same commit as the build it describes. Infrastructure-only commits (deployment retries, plumbing) are not listed.

## Nov 9, 2026 · stamp 20261110T010000Z
- Marks filter buttons are always combined, at every screen width: one near button (~ counts) and one trophy button (new highs/lows counts). The four separate pills are gone. Filters saved as a single side (near highs only, for example) load converted to the combined filter.
- Control rows stretch to the full width evenly: no more blank space trailing off on the right of the control groups, on wide screens or phones.
- NAS 100 in the header no longer hides at a fixed screen width. It hides only when the header row genuinely overflows, so it stays visible on the folded phone; it never hides while Nasdaq 100 is the selected index.
- The brand strip now appears only on the Duo unfolded in portrait, which is the one pose it protects. It no longer appears when the phone is folded; there the brand sits on the header row like everywhere else.

## Nov 9, 2026 · stamp 20261109T230000Z
- The Within % control is a dropdown now (1%, 3%, 5%, 10%, 20%, 50%); no more fighting a text field that reformatted while typing.
- Every stats pill is a filter: tap new highs, new lows, near highs, or near lows to filter the map to just those tiles. Counts always describe the full set, filters stack with the up/down filter, and tapping the total pill clears everything. Near buttons come before the new-extremes button, which always carries a 🏆 and shrinks to 🏆 plus a total count when space is tight.
- The map heading is one line: index flag or name, the pills, the period as a short code (1D, 1D EXT, 1D COM), and the full-screen button. All US listings shows as 🇺🇸. Wordy text removed: no grouping caption, no "USD", no descriptive notes in the Appearance panel.
- Controls take less room, so more map shows on load (about 87px more at phone width): shorter dropdown labels (Sector, Gradient, Mkt cap, From 52W high), the view dropdowns share one row, session buttons read Reg / Ext / Com on small screens, the All US dropdown moved into the Filters/Appearance row, session buttons hide when the period is not 1D, and row spacing is tighter.
- On narrow screens: the Solo/Duo toggle hides (Duo comes back on wider screens), the "by @ELAN" byline hides, and the NAS 100 header cell hides unless Nasdaq 100 is the selected index.

## Nov 9, 2026 · stamp 20261109T150000Z
- 52-week marks are now session-gated: on a trading day they only ever describe that day's session, and only once it opens. Before the bell, the previous session's marks no longer show (this morning's map would have carried Friday's extremes into Monday). On weekends and holidays the last session's marks stay visible, and the detail tag names the day ("New 52W low Fri") instead of saying "today".
- Detail panel gains Session low / Session high rows, dated when they are not from today, so the number behind a mark is right there to check.
- New proximity marks (off by default): a "Near 52W high/low" toggle with an adjustable "Within %" (default 1%) in the marks group. Stocks within the threshold of their 52-week high or low get a border only (never glow), outline count pills in the stats line, and a detail tag with the exact distance ("Within 0.4% of 52W high"). A true new extreme always wins over proximity. Open question: whether proximity should be exclusive with the new-extreme marks (one or the other) rather than stacking.

## Nov 7, 2026 · stamp 20261109T023000Z · bd71e00
- 52-week marks get their own colors: "New high color" and "New low color" pickers in the marks group (defaults fluorescent green #2BFF5E and fire truck red #FF2A1E), driving tile borders and glow, the stats-line count pills, and the detail panel tag.
- Appearance dock reorganized: most-used controls on top (Map size + Color by, then Full color at + Grey within). No control sits alone on a full-width row; % move cap pairs with Tile text just above the themes.
- Stats total pill fixed: it always shows the full direction-neutral count (it is the tap-to-clear-filter button) and reads "Top N" when the screen is wide enough.

## Nov 8, 2026 · cfff2f2
- 52-week marks defaults settled: master toggle on, glow None (border only), border width 0.5px.

## Nov 7, 2026 · d22af2d
- Opening session rule refined: before the 9:30 AM open the app opens on Extended (just the extended-hours move), not Combined. Combined remains the default after the close and on non-trading days.

## Nov 7, 2026 · a968062
- Closing the stock detail panel now clears the tile's white selection border.
- (Superseded the same day by d22af2d: opening session before the bell changed from Combined to Extended.)

## Nov 7, 2026 · d2c2685
- 52-week new high / low marks added: tiles that print an intraday new 52-week high or low get an edge treatment, with counts in the stats line and a range line plus tag in the detail panel. Appearance gains a marks group (toggle, glow mode, border width).

## Nov 7, 2026 · a03f955
- Split view renamed Solo / Duo.
- New grouping: "Gainers top, Losers bottom" as a loose flowing layout (an earlier rigid-rows version was scrapped), plus "Green to Red gradient".
- New Size by option: Equal size. New Color by option: distance from 52-week high.
- App opens on the current trading session.

## Nov 6, 2026 · 3d781cb (with 0c22320)
- Tile % move restored during Regular session (it had been hidden by session gating) and put behind the "% move" Appearance toggle, default on.
- Appearance tile toggles: Logo, Ticker, Company, % move.
- Fit screen map sizing now ignores the text below the map.
- Pages deployment jam cleared (two infra commits, not listed).

## Nov 6, 2026 · stamp 20261106T230000Z · 69f24f2
- Three header index cells: S&P, NAS (Nasdaq Composite), NAS 100, all following the Period control.
- Nasdaq Composite added as an index option (membership from the feeds' exchange data).
- Appearance and Filters become half-height docks: the page scrolls behind them, changes apply live, OK closes, no map redraw.
- Orange accents replace lavender everywhere.
- Stats line becomes tappable pill buttons (up / down / total) with active fills.
- Gainers / Losers grouping added.
- Map size gains Square and percentage heights; Full color becomes a dropdown with Custom; font ranges widened.
- Fill mode group zoom gains a back button.
- Export Text size becomes a three-position control: Min, As-is, Max-fit.
- Data and Import removed entirely.

## Nov 5, 2026 · stamp 20261106T041500Z · d9f0338
- Header cells follow the Period control for 1W and longer: they show the cash index's period move, no EXT or FUT tags. 1D behavior unchanged.

## Nov 5, 2026 · stamp 20261106T030000Z · 1c3e401
- Header basis fix: Extended and Combined now use the SPY/QQQ extended-hours segment move (EXT tag), with futures only as the overnight and weekend fallback (FUT tag). Fixes Combined double-counting the day's move.
- Themes cleaned to 12: Vivid, Acid, Jewel, Deep removed (devices on them fall back to Classic), Ember renamed Forge, Ultraviolet's negative extreme deepened to navy.
- Tile text default becomes Contrast.

## Nov 5, 2026 · de79477
- Auto color scale: saturation point follows the 98th percentile of the moves actually on screen.
- Eight new themes plus a Custom theme from two picked colors; theme rows get example strips.
- Tile text setting added (Contrast, White, Black, Negative).
- Second tap on the selected header cell opens the index detail popup.

## Nov 5, 2026 · 76aa645
- % move sizing becomes linear with an optional cap in Appearance (default 25%, scaled per period, can be off).
- Direction filter now applies after the Top N cut.

## Nov 5, 2026 · 876273e
- Tappable up/down direction filter added.
- % move sizing introduced (square-root form; made linear later the same day).
- Folded portrait: Export and Refresh move to the index row, clear of the floating status widget.

## Nov 5, 2026 · the Duo fixes (06e63f4, 6d253cc, 3f98bb1, 84fa669, 168a180, 7c89062, d11c921)
- iOS Home Screen app mode in unfolded portrait reserves a dead strip at the top that swallows taps. Fix: in exactly that mode, an 82px brand strip holds the $tockBurn lockup and clears the dead zone; sheets start below it.
- Fill-screen mode restructured as a layer over the intact page so the map reaches the physical bottom edge; scroll held by guards instead of a lock.
- Duo verdict from Elan: "Much better"; fill confirmed working in both orientations. A copy of that morning's build lives at /old/ for comparison.

## Nov 5, 2026 · e006aa8, a7773e2, 2766711, b9c5af5
- Fill-screen map mode added; group sectors checkbox removed.
- S&P and NAS header cells become tappable index selectors.
- Pull-to-refresh added.
- Early attempts at the Duo dead-zone fix (header inset and stacking hardening), later bisected and replaced by the brand strip above.

## Nov 5, 2026 · af41475, c6f8290
- Self-update check added: the page notices a newer published build and swaps to it once.
- Export header redesigned as a three-zone band (counts, brand lockup, index boxes).
- Header index cells added (S&P and NAS first), futures-aware with the FUT tag.

## Nov 4, 2026 · 067d335, 7ea165b, 9f3d552
- Three session modes added: Regular, Extended, Combined (compounded, not added).
- Tile text overhaul: all three elements on small tiles, scaled padding, one-decimal percents on small tiles, font and padding sliders.
- Flaming-$ favicon and apple-touch icon.

## Nov 4, 2026 · ae847bf
- Renamed from MarketHeat to $tockBurn: fire branding, "$tockBurn by @ELAN", tagline "Stocks on fire", repo renamed to ElanX/burn (URL elanx.github.io/burn). Artifact slug and on-device settings keys intentionally unchanged so settings survive.

## Nov 3 to 4, 2026 · beginnings
- First MarketHeat builds published to GitHub Pages (repo ElanX/heat) through a browser upload plus Actions rename flow, after the web editor proved unable to handle the 3 MB single file. The deploy-key git flow replaced it on Nov 4 and is the publish path ever since.
