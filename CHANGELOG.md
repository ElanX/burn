# $tockBurn changelog

Every published build of $tockBurn (https://elanx.github.io/burn/), newest first. Each entry is dated and keyed to the build's in-app stamp; older entries also carry the git commit hash. Going forward, an entry is added in the same commit as the build it describes. Infrastructure-only commits (deployment retries, plumbing) are not listed.
## November 10, 2026 · build 20261110T530000Z
- The Robinhood button now opens the Robinhood app directly in Home Screen mode instead of showing the stock's web page in an overlay; if the app is unavailable, it falls back to the web page as before.
## November 10, 2026 · build 20261110T510000Z
- Small groups on the map now show their name as a tag even when they are too small for a full header, so grouped views no longer show large unlabeled areas that look like one big Uncategorized group.
## November 10, 2026 · build 20261110T500000Z
- The first load of each new day now opens on the 1D period, whatever period was left selected the day before; later loads the same day keep your chosen period.
## November 10, 2026 · build 20261110T490000Z
- Pinching back out to the full map no longer leaves it short of the bottom of the screen: the map now measures its fit cleanly when a zoom ends, and re-checks its size for a few seconds afterward.
## November 10, 2026 · build 20261110T480000Z
- Rotating to landscape after loading in portrait no longer leaves a blank band at the top: the portrait brand strip now releases its space the moment the phone turns, and the map resizes to match.

## November 10, 2026 · build 20261110T470000Z
- The map no longer stops short of the bottom of the screen after rotating the phone or switching back to the app: it re-fits itself as the screen size settles.
## November 10, 2026 · build 20261110T460000Z
- The map now spans the full width of the screen on every device. The controls above it keep their current width.
- A cold open now lands on the correct layout right away: the first paint waits for the true screen size instead of trusting the size reported at launch.
- The index boxes at the top are wider, so the session tag fits inside the box next to the value.
- After hours, the S&P and Nasdaq 100 boxes always show a session tag, like the Nasdaq box already did.

## November 10, 2026 · build 20261110T450000Z
- Full width restored at phone and foldable widths: the side gutters are a flat 6 px again, no longer floored by the reported safe-area insets, which on some launches inset the whole app by roughly 80 px and left the right side of the map unfilled.

## November 10, 2026 · build 20261110T440000Z
- First paint now waits for the screen size to settle: on foldable launches that begin with the wrong posture's size, the app holds on the black boot screen for a fraction of a second and then paints once, at the correct size, instead of painting wrong and snapping.
- The brand strip at the top is decided by that same settled size, so its space is never reserved when the strip itself is off.

## November 10, 2026 · build 20261110T430000Z
- Cold open, third pass: the layout freeze is reverted, so map size is derived from the live screen on every render, as in the morning builds, instead of being pinned before data loads. A wrong-size launch now corrects on the next render instead of locking in.
- No reload can fire after the app has booted: the automatic reload refuses once boot completes, and a new version found during an active session now applies between viewings instead of blanking the page mid-view.
- At phone and foldable widths the side gutters shrink from 13/28 px to 6 px, so controls and map run essentially edge to edge. Desktop keeps its wider margins.

## November 10, 2026 · build 20261110T410000Z
- Quote card in the detail sheet now displays at its fitted width, centered, instead of stretching to the sheet's width.
- Quote card polish: "Today" now sits tight under the % move as a caption and renders in 50% grey, and the $tockBurn lockup tucks into the bottom-right corner at 50% opacity.

## November 10, 2026 · build 20261110T400000Z
- Quote card: the % move now stands alone on its line, with "Today" on its own smaller line underneath and the price below that, all centered on one axis.
- Quote card: the width now fits the card's content instead of a fixed size, so typical cards are narrower and a little taller. Type sizes are unchanged.

## November 10, 2026 · build 20261110T390000Z
- Cold-open recovery rebuilt: a small guardian at the very top of the page now watches the boot, and every automatic reload shares one budget of two per session, so the app can never reload in a loop. If a boot still cannot finish, the page shows a plain message with a Reload button instead of hanging silently.
- The wrong-size launch fix no longer rewrites the viewport setting while the page runs (that rewrite is what pulled the layout in from the screen edges). A stuck-size launch now spends one of the budgeted reloads instead, and the layout runs edge to edge again.

## November 10, 2026 · build 20261110T370000Z
- Fix for a cold open that could come up squeezed to part of the screen with nothing loaded: when the phone hands the app the wrong screen size at launch, the app now spots the mismatch and corrects it, re-applying the viewport and reloading once if it persists.
- If the first paint ever stalls, the app now reloads itself once instead of sitting on "Fetching the latest delayed quotes" forever, and says so in plain text if it still cannot load.

## November 10, 2026 · build 20261110T360000Z
- Lighter boot: quotes from a cache less than 5 minutes old are used as-is with no new pull (reload, the Refresh button, and pull-to-refresh still force a fresh pull).
- 52-week data: the same-day saved baseline is used directly, and any new 52-week fetch now covers only the stocks in the current view instead of the whole market.
- The daily check for newly listed stocks runs at most once a day, a few seconds after the map paints, and never during a first-ever session.
- Searching Filters for a stock that is not on the map yet now looks it up live and offers to add it, so a brand-new listing can join the map the day it starts trading.

## November 10, 2026 · build 20261110T350000Z

- The page now lays out at its final size before any data loads: controls, stats, and the map no longer change height or width as quotes arrive.
- Quote card: everything is centered, "Today" is small, the corners outside the rounded border are transparent for pasting on any background, and a small $tockBurn logo sits at the bottom right.

## November 10, 2026 · build 20261110T340000Z

- Quote card redesigned: the ticker and the % move are now the same size, only the % number is colored (Today is white), the card height fits its content, and the whole card gets a green or red border matching the day's direction.

## November 10, 2026 · build 20261110T330000Z

- Stock and index details now open with a shareable quote card (logo, ticker, company, the % move as the headline, price), with Share and Copy buttons that send just that card as an image.
- A Robinhood app icon on the detail page opens the stock in Robinhood; the S&P 500 opens VOO and the Nasdaq 100 opens QQQ.
- Fixed the map rendering shorter for a moment after a pinch zoom; its height now stays put while zoomed.

## November 10, 2026 · build 20261110T320000Z

- While pinch-zoomed, a floating 1x button (same style as the fullscreen exit button) appears on the map; tapping it returns to the full view.

## November 10, 2026 · build 20261110T310000Z

- Pinch zoom now goes to 20x (was 6x), so the smallest tiles can be opened up to full readable size.

## November 10, 2026 · build 20261110T300000Z

- The Gradient grouping is now named "Gradient AX". Label only; the layout and saved settings are unchanged.

## November 10, 2026 · build 20261110T290000Z

- Fixed pinch zoom snapping back to the full view on its own: refreshes and small layout shifts no longer reset a zoom, stray clicks after a pan can no longer be misread as a double-tap, and a new build arriving no longer reloads the page out from under an active zoom.

## November 10, 2026 · build 20261110T280000Z

- Pinch zoom is smooth now: no more shaking, ghosting, or the map flashing tiny during zoom. The sharp layout swaps in invisibly once your fingers lift, and panning glides without redrawing until you reach an edge.

## November 10, 2026 · build 20261110T270000Z

- Roku fix, second pass: the quote feed was dating its after-hours placeholder with the current day, which let a delisted name's final session pass as a live trade. The extended date now counts only when that quote is actually live, and symbols the feed explicitly reports as having no quote are marked not traded, so delisted names reliably go inert.

## November 10, 2026 · build 20261110T260000Z

- Pinch to zoom on the map (touch devices): pinch 1x to 6x and the map re-lays out sharply at the new size, drag to pan while zoomed, double-tap toggles 1x / 2.5x. New Appearance toggle "Pinch zoom" (on by default) turns it off and resets any zoom.

## November 10, 2026 · build 20261110T250000Z

- Delisted or halted stocks whose quote feed still serves their last session (Roku was the visible case) are now treated like names that did not trade today: no daily move, no 52-week marks, and no place in the map under Price x Vol sizing, judged by the quote's own last-trade date against the most recent trading day.

## November 10, 2026 · build 20261110T240000Z

- Loads are instant now: every open paints immediately from the newest quotes saved on the device, whatever their age, then fresh quotes update the map in place. No more black, empty map while waiting.
- The 52-week highlights, tile borders, and the near/trophy pills are there from the first paint on a same-day reload, using today's saved 52-week baseline until the live pull confirms it. A previous day's baseline is never reused.

## November 10, 2026 · build 20261110T230000Z

- Fixed the near and new-extreme pills and tile borders going missing on loads served from the 5-minute quote cache: those loads now also pull the 52-week baseline so the marks can be judged, instead of waiting for the next full refresh.

## November 10, 2026 · build 20261110T220000Z

- Fixed the near-52-week pill (and the trophy pill) going missing on desktop: the stats row's space-trimming pass could hide them even when there was room. The trimming now only applies at phone widths.

## November 10, 2026 · build 20261110T210000Z

- The stats line's flat count no longer carries the "/ unknown" wording; it reads just "N flat" again. Counts are unchanged.

## November 10, 2026 · build 20261110T200000Z

- Tapping or clicking anywhere on the detail panel besides its buttons now closes it (a drag or scroll on the panel does not).
- The Show dropdown gains Top 250 and Top 1000.
- Zero-volume guard: a stock that has not traded today (no volume and no extended-hours print in the live quotes) no longer earns 52-week high/low marks, no longer appears on the map under Price × Vol sizing, and no longer shows a daily move. Names that traded, including premarket, are unaffected.

## November 10, 2026 · build 20261110T170000Z

- Stock detail layout: Daily move is now top-left, Market cap top-right, and Price sits bottom-left directly under the move.
- The Daily move value is colored neon green when up and fire truck red when down (grey only at exactly 0%); the index detail's Move value uses the same coloring.
- Fixed the detail header alignment: the logo no longer inherits the tile logo nudge, so it lines up exactly with the ticker and company name.

## November 10, 2026 · build 20261110T160000Z

- In the stock detail, the session range and 52-week range scales now stack as full-width rows of the same width (the session scale no longer sits squeezed in a half-width column), and the price label on each scale can no longer overlap the "% of range" text at any position.
- The index detail view (S&P, Nasdaq Composite, Nasdaq 100) now shows the same two range scales: a session range from the day's low and high, and a 52-week range wired from the quote feed, shown when the feed supplies it.

## November 10, 2026 · build 20261110T140000Z

- Tapping a stock now opens its full details directly. The old first panel still exists as a hover preview on computers with a mouse; on touch devices a tap goes straight to details.
- The detail sheet is smaller and cleaner: it fits its content with no blank space at the top, the close button floats in the corner, there is no heading, no blur or dim over the map behind it, and the delayed-quotes disclaimer line is gone (the Quotes fetched row stays).
- Session low and high are now a line scale with the current price marked, in the same style as the 52-week range. The Price × Vol and Volume rows were removed.
- The index detail view (S&P, Nasdaq Composite, Nasdaq 100) now uses the same sheet and layout as the stock detail.
- 52-week high/low marks are judged against the quote feed's own 52-week range, captured fresh each session, instead of stored data that could go stale. A stock that set its extreme yesterday no longer shows a false "new high today", and the detail view's range scale uses the same feed range.
- An open detail view now refreshes itself when live quotes arrive, so the range scales appear as soon as the first quote pull lands.

## November 10, 2026 · build 20261110T120000Z

- The Nasdaq Composite header figure now calculates its own extended-hours move from its constituent stocks (weighted by market value, the same construction the index itself uses), so it no longer sits on the previous day's move while the S&P and Nasdaq 100 show extended quotes. It is tagged EXT when calculated, and REG when it falls back to the regular close: very early premarket, after 8 PM, and on weekends.
- The map now keeps its own stock list current with no outside help: in the background (first open each day, hourly while open, and on pull to refresh) it checks the full exchange listings and adds anything new, so an IPO joins the map the same day it starts trading. New Nasdaq listings also join the Composite calculation automatically once they trade.
- A short line in the Nasdaq Composite detail view shows when the figure is calculated from constituents and how much of the index the calculation covers.

## November 9, 2026 · build 20261110T100000Z

- SpaceX (SPCX) now uses the official SpaceX X logo in white on black, drawn large so it stays recognizable on small tiles.
- Industry emoji updates: Semiconductors now 🖲️, Electronic Components 🔩, Natural Gas Distribution ⛽. The fire emoji no longer marks any group.
## November 9, 2026 · build 20261110T090000Z

- Tiles never show a % move by itself anymore: the ticker outlasts the %, and wide flat tiles put logo, ticker, and % on one line.
- Treemap layout caps tile shapes at about 4:1, so tall unreadable slivers get readable width from their neighbors; group totals and areas are unchanged.
- New Appearance option: a Price tile toggle (off by default) that shows the stock price under the ticker on tiles with room for it.
- Sector and industry group headers now start with an emoji. Industries without a good match stay plain.
- The near 52W high/low filter pill now shows the Within % it filters by, and updates live when the setting changes.
- SpaceX has a new logo, a big white X on black. The Apple, Tesla, and Nvidia logos are recentered in their circles.
- On desktop, the fill button now fills the browser window instead of taking over the whole monitor.
- Starting defaults: marks glow set to Inner, Near 52W marks on with Within 3%, marks border 1px.
- Control dropdowns line up evenly with the other controls; labels now read Price × Vol, % Move, and All Moves.
## Nov 9, 2026 · stamp 20261110T040000Z
- Quick Moves gains a ±0.5%+ option (All moves, ±0.5%+, ±1%+, ±2%+, ±5%+).
- The index dropdown's All US option now reads "🇺🇸 All US".
- New starting defaults: 52-week marks glow starts at Inner, and Near 52W starts on with Within at 5%. Settings you already saved on a device are unchanged.

## Nov 9, 2026 · stamp 20261110T030000Z
- The ~ on the near filter button is sized up to match the trophy, so the two buttons read as a pair.
- Dropdown text is centered in every closed dropdown.
- The header fits on one row when there is room: on the folded phone, the brand, the three index cells, and the share and refresh buttons share a single row instead of the buttons dropping to their own line. On narrow phones that cannot fit it, the buttons keep their own row.

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
