# «Захисти Світлячок» — game_assets

Все PNG с настоящей прозрачностью. Масштаб ×4 от логического размера брифа (кроме отмеченных).
Точные размеры каждого файла, точки поворота, дула, fps — в `manifest.json`.

## units/ — техника и угрозы
| Файл | Кадр px | Лог. | Анимация |
|---|---|---|---|
| def_pickup.png | 440×256 | 110×64 | — (привязка снизу) |
| def_gunner_mount.png / _f0.._f2 / _3x1 | 320×224 | 80×56 | отдача: f0 покой, f1 стволы назад, f2 возврат, 24 fps |
| def_gunner_flash_1..3 / _3x1 | 160×160 | 40×40 | случайный выбор; начало вспышки в (6,80) |
| def_casing.png | 24×40 | 6×10 | вращать кодом |
| def_tracer.png | 16×120 | 4×30 | растягивать кодом, голова вверху |
| def_aa_missile / _4x1 | 56×168 | 14×42 | пламя 4 кадра, 20 fps |
| enemy_shahed / _prop_4x1 | 208×184 | 52×46 | винт 4 фазы, 24 fps |
| enemy_shahed_light_2x1 | 208×184 | — | оверлей огонька: вкл/выкл, 2 fps |
| enemy_shahed_hit | 208×184 | — | белая вспышка, 1 кадр |
| enemy_cruise / _4x1 | 96×248 | 24×62 | пламя 4 кадра |
| enemy_jet / _4x1 | 160×208 | 40×52 | форсаж 4 кадра |
| enemy_ballistic / _4x1 | 80×256 | 20×64 | шлейф 4 кадра |
| warn_ballistic / _4x1 | 112×112 | 28×28 | пульс 4 кадра, 10 fps |
| def_radar_truck.png | 480×400 | — | декор (бонус) |

**Важно про зенитку:** стволы в исходном рисунке подняты примерно на 26° (`barrel_angle_deg` в manifest).
В коде: `drawAngle = aimAngle - barrel_angle_deg`. Точка поворота — `pivot_px`, дула — `muzzle_px`.

## fx/ — эффекты (листы: кадры слева направо, одного размера)
| Файл | Кадр | Кадров | fps | Цикл |
|---|---|---|---|---|
| fx_explosion_big_8x1 | 384 | 8 | 18 | нет |
| fx_explosion_med_6x1 | 256 | 6 | 20 | нет |
| fx_rocket_blast_8x1 | 512 | 8 | 18 | нет (с ударным кольцом) |
| fx_hit_spark_4x1 | 96 | 4 | 24 | нет |
| fx_smoke_puff_6x1 | 128 | 6 | 12 | нет |
| fx_fire_loop_6x1 | 160×224 | 6 | 12 | да, привязка снизу |
| fx_reb_waves_6x1 | 320 | 6 | 12 | да |
| fx_shield_ring | 320 | 1 | — | пульс кодом |
| fx_shield_dome, fx_smoke_trail, fx_bullet_ap | — | 1 | — | дополнительно |

## mascot/
mascot_happy / worried / off / cheer — 640×800, единый масштаб, привязка снизу.
mascot_pulse_4x1 — 320×400 на кадр (2×, чтобы лист был < 600 КБ), 6 fps цикл.

## ui/
ui_life_on/off 128×160 · bonus_bulb, bonus_reb 192 · ui_radar 256 ·
ui_btn_yellow_rocket, ui_btn_blue_shield 384×256 · ui_settings/stats/trophy/rating/refresh 176.

## objects/ — 4 объекта × ok/damaged/burning
600 px шириной (2×), общий масштаб внутри объекта, привязка снизу.
**Черновик:** вырезаны из атласа (~120 px) и увеличены ×4–5 — на телефоне чуть мыльные.

## bg/ — фоны 1080×1920 (векторная отрисовка)
{night,dusk,storm,dawn} × {sky, far_city, near_city, ground} — накладывать в этом порядке.
Общие: bg_moon, bg_cloud_a/b/c, bg_searchlight_beam (крутить от нижней точки).

## Чего ещё нет (по брифу)
ui_pause, ui_coin, ui_star_on/off, ui_lock, ui_medal_1..3, ui_panel (9-slice), ui_btn_ghost,
_pressed-состояния кнопок, ui_rocket_btn_{ready,cooldown,empty}, ui_level_card, brand_*.
