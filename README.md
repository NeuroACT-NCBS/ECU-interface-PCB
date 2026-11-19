# ECU Interface PCB

KiCad PCB design for a reward-well/environmental setup controller for behavioral neuroscience experiments.

## Function
needs a rewrite. 
Built around an **RP2040-Zero** microcontroller. Takes 6 SMA coaxial sensor inputs from the spikegadgets ECU, through a schmitt-trigger buffer, and drives 4 TMC2209 stepper motors for reward dispensing. 8× AO3400A MOSFETs switch light and sounds. Two stacked USB-A ports allow to connect with the reward wells.

## Requirements

- [KiCad](https://www.kicad.org/) 10.0+
- [NeuroACT-KiCad-libraries](https://github.com/NeuroACT-NCBS/NeuroACT-KiCad-libraries), installed as global libraries (see below)

## Setup

Clone this repository and the library repository:

```bash
git clone https://github.com/NeuroACT-NCBS/ECU-Interface-PCB.git
git clone https://github.com/NeuroACT-NCBS/NeuroACT-KiCad-libraries.git
```

Then add the library to KiCad as a global library:

1. In KiCad, open **Preferences → Manage Symbol Libraries**, choose the **Global Libraries** tab, and add `NeuroACT.kicad_sym` from the library clone with the nickname `NeuroACT`.
2. Open **Preferences → Manage Footprint Libraries**, choose the **Global Libraries** tab, and add the `NeuroACT.pretty` folder from the library clone with the nickname `NeuroACT`.
3. Open **Preferences → Configure Paths** and add a variable named `NEUROACT_LIBS` set to the library clone folder (the one containing `3D models/`). It is used to load the 3D models.
4. Restart KiCad and open `ECU-Interface-PCB.kicad_pro`.

See the [library README](https://github.com/NeuroACT-NCBS/NeuroACT-KiCad-libraries#installation-as-a-global-library) for details and for editing the global library tables directly.

## KiCad Plugins

- **Fabrication Toolkit** — for generating production Gerber files
- **Round Tracks** — configured via `.round-tracks-config`

## License

CERN Open Hardware Licence Version 2 — see [LICENSE](LICENSE)
