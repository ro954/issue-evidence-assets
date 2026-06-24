# EVO Roulette B-only study - 2026-06-24

Scope: only the official EVO B window (`https://www.ouroreais.com/games/9952/play`). A/ours was not tested in this pass.

## Target

- Official B URL: `https://www.ouroreais.com/games/9952/play`
- Embedded EVO iframe: `babylonpegasea.evo-games.com/frontend/evo/mini/#provider=evolution&game=roulette&table_id=vctlz20yfnmp1ylr`
- Table: `vctlz20yfnmp1ylr`
- Visible balance during B study: `IDR 698.690`
- Visible total bet after settlement: `IDR 0`

## What was confirmed

1. B target lock is correct.
   - Evidence: `frames/round_006_b_target_reconfirm_official_170841.png`

2. B minimum live bet placement works for outside red.
   - Bet: `Merah / Red`, `IDR 10.000`
   - Evidence after bet: `frames/round_006_after_b_only_retry2_official_165807.png`
   - Evidence after settlement: `frames/round_006_result_b_only_official_165936.png`

3. B bottom control mapping:
   - Circular arrow button opens `Autoplay`; it was not started.
   - Bar-chart button opens `Statistik`.
   - Top clock/history button opens `RIWAYAT PERMAINAN`.
   - Evidence:
     - `frames/round_006_b_autoplay_panel_official_171018.png`
     - `frames/round_006_b_bottom_bar_button_official_171144.png`
     - `frames/round_006_b_top_clock_button_official_171248.png`

4. B game history and detail are available.
   - History list shows two `Rolet` records today, both `IDR 10.000` stake and `-IDR 10.000` result.
   - Evidence list: `frames/round_006_b_game_history_loaded_official_171316.png`

5. B latest history detail matches the B-only red bet loss.
   - Time shown by B UI: `24/6/2026 16.58.17`
   - ID game: `18bbf8a4c648d0c76dee48fe`
   - Result: `10`
   - Bet row: `Merah`, stake `Rp 10.000`, win `Rp 0`
   - Round total: total bet `IDR 10.000`, total win `IDR 0`, result `-IDR 10.000`
   - Expected rule check: result `10` is black, so red loses; net `-IDR 10.000` is UI-consistent.
   - Evidence: `frames/round_006_b_game_history_first_row_official_171351.png`

6. B older history detail uses the same structure.
   - Time shown by B UI: `24/6/2026 16.31.49`
   - ID game: `18bbf733fa22ec25526b5510`
   - Result: `10`
   - Bet row: `Merah`, stake `Rp 10.000`, win `Rp 0`
   - Round total: total bet `IDR 10.000`, total win `IDR 0`, result `-IDR 10.000`
   - Evidence: `frames/round_006_b_game_history_second_row_official_171543.png`

## Conclusion

B official EVO is now understood well enough for the current tool flow:

- Where to place a minimum official bet: selectable chips include `10k`; outside `Merah` accepts `IDR 10.000`.
- Where to view result history: top clock/history button -> `RIWAYAT PERMAINAN`.
- Where to view per-round detail: click a row in `RIWAYAT PERMAINAN` -> `RINCIAN PERMAINAN`.
- Which fields are available from B UI detail: game time, ID game, result number, bet type, stake, win, total stake, total win, net result.

This is still a B front-end/history audit only. It does not prove backend settlement correctness because no official/backend transaction JSON was available in this pass.
