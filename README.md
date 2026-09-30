# RecklissLED

LED strip PCBs designed in [KiCad](https://www.kicad.org/) 10.

> Work in progress: schematic and board layout for the 34x7 strip have just been started.

## Layout

```
34x7/
├── design/RecklissLED 34x7/    KiCad project (open the .kicad_pro)
│   ├── EasyEDA.kicad_sym       project symbol library
│   ├── EasyEDA.pretty/         project footprint library
│   ├── EasyEDA.3dshapes/       3D models (.step / .wrl)
│   └── RecklissLED 34x7.kicad_dru   JLCPCB design rules
├── images/                     renders and photos
└── manufacturing/              Gerbers and BOM for orders
```

## Opening the project

Clone the repo and open `34x7/design/RecklissLED 34x7/RecklissLED 34x7.kicad_pro` in KiCad 10.

The project is self-contained: every part's symbol, footprint and 3D model lives in the project folder and is referenced with `${KIPRJMOD}` paths, so nothing extra needs installing.

## Adding parts

LCSC/JLCPCB parts are imported with the [impartGUI plugin](https://github.com/Steffen-W/Import-LIB-KiCad-Plugin):

- Launch it from the **PCB Editor** (Tools → External Plugins → impartGUI). From the Schematic Editor it can't detect the open project.
- Tick **Save local, in the project folder**; leave **auto settings** unticked. The `EasyEDA` library is already in the project's library tables.

## Design rules

`RecklissLED 34x7.kicad_dru` holds JLCPCB 2-layer, 1 oz copper rules from [Cimos/kicad-druid](https://github.com/Cimos/kicad-druid). Run **Inspect → Design Rules Checker** before exporting Gerbers.

## Working on it from multiple computers

1. `git pull` before opening KiCad.
2. When you're done: save, close KiCad, then `git add -A`, `git commit`, `git push`.
3. Only edit a board on one computer at a time. KiCad files don't merge well.
