# Awesome M-VAVE FM-1 [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> A curated list of resources, tools, custom firmware and open source work around the M-VAVE (Cuvave) FM-1 pocket FM synthesizer.

The [FM-1](https://www.m-vave.com/product?id=fm-1) is a battery-powered, six-operator FM synthesizer with 32 algorithms, 27 silicone keys, a colour TFT screen, built-in effects, an arpeggiator and a step sequencer. It speaks Yamaha DX7 SysEx, so decades of DX7 patches load straight into it. It is built around a JieLi AC791N (WL82) SoC and updates its firmware over USB-MIDI SysEx, which is why it has become one of the most hackable synths of 2026: the updater was reverse-engineered within weeks of launch and a family of open source firmwares now runs on it.

**Flashing unofficial firmware is at your own risk.** The flash has a single bank and the board has no debug header, so read the [recovery](#firmware-update-and-recovery) section before you install anything.

## Contents

- [Official](#official)
- [Custom firmware](#custom-firmware)
  - [Open source](#open-source)
  - [Closed source](#closed-source)
  - [Not a synth](#not-a-synth)
- [Reverse engineering and firmware development](#reverse-engineering-and-firmware-development)
- [Firmware update and recovery](#firmware-update-and-recovery)
- [Editors, librarians and companion software](#editors-librarians-and-companion-software)
- [Patches and sound banks](#patches-and-sound-banks)
- [Hardware add-ons](#hardware-add-ons)
- [Documentation and guides](#documentation-and-guides)
- [Articles and reviews](#articles-and-reviews)
- [Videos](#videos)
- [Communities](#communities)
- [Related M-VAVE projects](#related-m-vave-projects)

## Official

- [Product page](https://www.m-vave.com/product?id=fm-1) - Specs and feature overview. Also at [cuvave.com](http://www.cuvave.com/product?id=fm-1).
- [Downloads](https://www.m-vave.com/download) - M-UPGRADE updater for Windows and macOS, the latest `.fwsc` firmware (V15, July 2026), MIDI control reference and release notes.
- [Firmware V15](https://yms-file-store.oss-cn-hongkong.aliyuncs.com/software/firmware/FM-1.fwsc) - Current official firmware image. Custom firmwares expect you to be on V15 first.
- [MIDI control reference (EN)](https://yms-file-store.oss-cn-hongkong.aliyuncs.com/software/releaseNote/firmware/FM-1%20MIDI%20EN.docx) - Official CC map, effects on their own MIDI channel.
- [Release notes](https://yms-file-store.oss-cn-hongkong.aliyuncs.com/software/releaseNote/firmware/FM-1.txt) - Official changelog for every firmware version.
- [User manual (PDF)](https://m.media-amazon.com/images/I/A1WOydif9HL.pdf) - Multi-language printed manual. Also mirrored on [manuals.plus](https://manuals.plus/ae/1005012499001058).

## Custom firmware

All of these install over USB from Chrome or Edge in a couple of minutes, and M-VAVE's own updater takes you back to stock. Most of the open source ones descend from Felucca.

### Open source

- [Felucca](https://github.com/hugelton/Felucca) - Multi-engine synth firmware by Leo Kuroshita (Hügelton Instruments). Thirteen engines (6-op FM, VA, phase distortion, chiptune, sampler, granular, physical modelling, organ, drums), four tracks, 64-step sequencer, song mode, mod matrix, USB audio, [web installer](https://hugelton.github.io/Felucca/) and [web editor](https://hugelton.github.io/Felucca/webapp/editor/). The platform most other firmwares build on. GPL-3.0.
- [SLOOP](https://github.com/isod89/sloop-fm1) - Live four-track groovebox by 3dSam: three synths plus a drum machine, 37 drum kits, punch-in FX, layer system, song mode, web editor. Based on Felucca. GPL-3.0.
- [X0X](https://github.com/charlesvestal/fm1-x0x) - ReBirth-style groovebox by Charles Vestal: TR-909, TR-808, two TB-303s with TB-3PO acid generators and a breakbeat slicer, each with its own sequencer. Has a [browser emulator](https://charlesvestal.github.io/fm1-x0x/emu/) and [manual](https://charlesvestal.github.io/fm1-x0x/manual/). Felucca fork. GPL-3.0.
- [Jangada](https://github.com/zednaked/jangada) - Felucca fork adding superwave analog, a modulation matrix, latched drones, ratchets and synthesized drum kits. GPL-3.0.
- [Melodee](https://github.com/keremimo/melodee) - Felucca derivative that went its own way: ten engines, eight patterns per track, STUDIO workspaces, four-channel USB audio input, TR-808 kit. [Web installer](https://keremimo.github.io/melodee/). GPL-3.0.
- [SLOOP ALG](https://github.com/shaw-core/Sloop_ALG02) - Experimental SLOOP fork (Chinese README) adding DX7, VA, Karplus-Strong, pluck and additive engines, with its own web installer and editor.
- [FM-1 B-Boy Edition](https://github.com/friendsmakenoise-prog/fm1-pocket-sampler) - Early-stage sampler/groovebox firmware that treats the FM-1 as a late-90s chop sampler with three sample tracks and an FM lane.
- [Lunar Modulator](https://github.com/ip2k/lunar-modulator) - Research-stage open firmware built on Mutable Instruments engines (Plaits, Braids, Rings) and a Movy-style sequencer. Nothing flashed yet, but the [virtual FM-1 in the browser](https://ip2k.github.io/lunar-modulator/) is playable and the docs are a good map of the whole reverse-engineering effort. MIT.
- [fm1-polyseq](https://github.com/NOVALENTI/fm1-polyseq) - Polyphonic 16-step sequencer and hardware abstraction layer in strict C99, written from scratch for the pi32v2 CPU.

### Closed source

- [FM-1+VA](https://baudgirl.com/work/FM-1+VA) - The first third-party firmware, by Madeline (Baud Girl). Keeps the stock FM engine, adds a virtual analog engine with supersaw, a 64-step dot-matrix sequencer with ratchets and chance, four assignable knobs on every screen, and a cleaner menu. Free, with a [manual](https://baudgirl.com/work/FM-1+VA/manual) and [web installer](https://baudgirl.com/work/FM-1+VA/install). The author has said the source will be released.
- [Groove OS](https://www.groove-os.com/) - Commercial eight-track groovebox firmware by Peter Gombos ($29). FM and VA engines, up to 20 voices, per-track loop lengths, drum machine, performance mode, [browser emulator](https://www.groove-os.com/emu) and [manual](https://www.groove-os.com/manual). Built on top of the V15 firmware.

### Not a synth

- [fm1-nes](https://github.com/Keitark/fm1-nes) - NES emulator running on the FM-1, published as a worked example of custom firmware development with board-support code and USB serial diagnostics. Apache-2.0.
- [fm1-doom](https://github.com/Keitark/fm1-doom) - Doom engine port for the FM-1, in progress.

## Reverse engineering and firmware development

- [FM-1-RE](https://github.com/AL-255/FM-1-RE) - The deepest public analysis of the stock firmware: architecture, memory map, OTA protocol captures, security audit of recovery entry points, Ghidra scripts and V13/V14 firmware images. WTFPL.
- [fm1-custom-fw](https://github.com/aroum/fm1-custom-fw) - Teardown photos, hardware notes (chip, flash, no debug pads), analysis of the macOS M-UPGRADE app and a Python SysEx flasher and scanner.
- [fm1-nes](https://github.com/Keitark/fm1-nes) - Source-only integration with the JieLi AC79/WL82 SDK, build setup for the pi32v2 toolchain, and guides on application-only updates that preserve the bootloader. Start here if you want to write your own firmware.
- [fm1-emulator](https://github.com/simonjohansson/fm1-emulator) - Rust emulator that runs FM-1 firmware images (`.fwsc`, `.elf`, `.bin`) on your desktop with the screen, buttons and USB serial console, so you can test without flashing. GPL-3.0.
- [fm1-firmware-patcher](https://github.com/czietz/fm1-firmware-patcher) - Binary patches for the stock V15 firmware: Dexed-accurate detune, removes aftertouch vibrato, recolours the oscilloscope. Unlicense.
- [MVAVE-M-UPGRADE-decompiled](https://github.com/entitymar/MVAVE-M-UPGRADE-decompiled) - Decompilation of the official updater application.
- [jielie](https://github.com/kagaimiq/jielie) - Reference site for JieLi SoCs, the family the FM-1's AC791N belongs to.
- [jl-uboot-tool](https://github.com/kagaimiq/jl-uboot-tool) - JieLi flasher and dumper. Source of the `wl82loader.bin` used by FM-1 Transporter.
- [ghidra-jieli](https://github.com/kagaimiq/ghidra-jieli) - Ghidra processor module for JieLi's pi32v2 CPU, needed to disassemble the firmware.
- [jl-misctools](https://github.com/kagaimiq/jl-misctools) - Miscellaneous JieLi utilities.
- [Schwung](https://github.com/charlesvestal/schwung) - Charles Vestal's framework for the Ableton Move. Not an FM-1 project, but X0X and Lunar Modulator borrow its 909, 808, 303 and PSX Verb modules.

## Firmware update and recovery

Stock updates and every custom installer go over USB-MIDI SysEx. If a flash fails the device may not boot, and the only way back in without opening the case is the chip's mask-ROM USB download mode, which needs a small hardware dongle.

- [fm1-linux-update](https://github.com/fuleo/fm1-linux-update) - Update stock V14 to V15 from Linux with verification, since M-VAVE only ships Windows and macOS updaters. MIT.
- [fm1_flasher.py](https://github.com/aroum/fm1-custom-fw) - Standalone CLI flasher and preset uploader from the fm1-custom-fw project.
- [fm1_ota.py](https://github.com/AL-255/FM-1-RE) - Linux USB-MIDI update client from the FM-1-RE project, with offline protocol tests.
- [FM-1 Transporter](https://github.com/kurogedelic/FM-1-transporter) - Read and write the FM-1's flash from a Mac through a Seeed XIAO RP2040 wired to the USB data lines. Dumps the full flash in seconds and is the recovery path for a device that no longer starts. MIT.
- [USB_KEY dongle notes](https://github.com/ip2k/lunar-modulator/blob/main/docs/10-usb-key-dongle.md) - Lunar Modulator's write-up of the RP2040 dongle that forces the AC791N into download mode over USB-C.
- [How to update the firmware](https://medium.com/@shelvindatt02/how-to-update-the-firmware-on-your-m-vave-fm-1-synthesizer-7bc4ea2c3bd5) - Plain walkthrough of the official M-UPGRADE process.
- [fwradar changelog](https://fwradar.com/p/m-vave-fm-1) - Version history with changelogs for V09 through V15.

## Editors, librarians and companion software

- [FM1 Editor & Librarian](https://fm1-editor.com/) - Browser-based DX7 voice editor and patch librarian built for the FM-1 by Benny Sparra: ten local banks, full operator editing, the FM-1 effects chain, SysEx import/export, six languages. Works with stock and FM-1+VA firmware. [Source](https://github.com/benny-sparra/fm1-dx7-patch-importer), MIT.
- [DXcompanion](https://dxcompanion.uk/) - Free browser editor for the whole Yamaha DX family, with beta FM-1 support.
- [Dexed](https://asb2m10.github.io/dexed/) - The open source DX7 emulator and editor. The FM-1 accepts single-parameter SysEx from it, so you can edit live from the plugin.
- [FM-1 Workbench](https://github.com/thegiantsnail/fm1-workbench-public) - Web app, Android app, VST3/CLAP controller plugin and an MCP server for the FM-1, with a DX7 voice library, randomize/mutate, drum sequencer and MIDI file player. [Live](https://fm1-workbench.web.app). GPL-3.0.
- [Virtual FM-1](https://github.com/jbschooley/Virtual-FM-1) - Software FM-1 as a standalone app and VST3/AU plugin for macOS, Windows and Linux, with two-way preset and pattern sync to hardware running FM-1+VA. GPL-3.0.
- [FM-1 Pulses](https://github.com/mene311/fm1-pulses) - Generative browser sequencer that broadcasts MIDI live and can freeze 64-step phrases into the FM-1's patterns on FM-1+VA firmware. [Live](https://mene311.github.io/fm1-pulses/).
- [FM-1 Utility](https://fm1-utility.pages.dev/) - Dependency-light Web MIDI editor for the FM-1.
- [fm1-read-voice](https://github.com/czietz/fm1-read-voice) - Read the current voice back from the FM-1 over USB MIDI, which the stock firmware does not offer through other editors.
- [fm1-bank-sender](https://github.com/leomaimoni/fm1-bank-sender) - Android APK to send `.syx` sound banks to the FM-1 from a phone.
- [fm1_soundbank_app](https://github.com/pfkellogg/fm1-bonus-box/tree/main/fm1_soundbank_app) - Command-line tool to list, reorder and send a 128-preset soundbank over USB MIDI.

## Patches and sound banks

- [fm1-factory-presets](https://github.com/KingParamount/fm1-factory-presets) - The original 128 factory voices recovered as four DX7 bank dumps, since the onboard reset only restores imported data. Includes SysEx protocol notes, a provenance table tracing 126 voices to known DX7 libraries, and an FM synthesis tutorial PDF. CC BY-SA 4.0.
- [fm1-banks](https://github.com/mene311/fm1-banks) - 26 thematic 32-voice DX7 banks (832 patches) with provenance tracking and an [audio gallery](https://mene311.github.io/fm1-banks/).
- [This DX7 Cartridge Does Not Exist](https://www.thisdx7cartdoesnotexist.com/) - Neural-network-generated DX7 cartridges, fresh every reload. Loads straight into the FM-1. [Source](https://github.com/Nintorac/NeuralDX7).
- [Ambient & Dreams](https://natlifesounds.com/product/ambient-dreams-for-m-vave-fm-1-fm-synthesizers/) - Commercial soundbank by NatLife Sounds made for the FM-1.

## Hardware add-ons

- [fm1-sustain-footswitch](https://github.com/pfkellogg/fm1-sustain-footswitch) - Arduino board that turns a 3.5 mm sustain pedal into MIDI CC64 on the FM-1's TRS MIDI in, with schematics.
- [FM-1 Bonus Box](https://github.com/pfkellogg/fm1-bonus-box) - ESP32-S3 companion box: sustain pedal, rotary preset browser with a round TFT, WiFi soundbank manager, USB MIDI keyboard host and a sing-on-key trainer.
- [FM-1 Transporter](https://github.com/kurogedelic/FM-1-transporter) - RP2040 flash dumper and recovery dongle, see above.

## Documentation and guides

- [FM-1 MIDI Guide](https://m-vave-fm1-midi-guide.up.railway.app/) - Baud Girl's readable MIDI implementation: channels, CC map for the six effects, SysEx, clock sync.
- [fm1-guide](https://fuleo.github.io/fm1-guide/) - Practical notes: sequencer tutorial, the V15 reverb fix and updating from Linux.
- [FM-1 on Tao of Mac](https://taoofmac.com/space/com/m-vave/fm-1) - Rui Carmo's running notes and link collection on the device.
- [FM-1 SysEx protocol](https://github.com/KingParamount/fm1-factory-presets) - Handshake, bank transfer and 7-bit payload encoding, documented while recovering the factory banks.
- [OTA protocol and architecture docs](https://github.com/AL-255/FM-1-RE) - USB-MIDI framing, session behaviour and memory layout from the FM-1-RE project.
- [Felucca BUILDING.md](https://github.com/hugelton/Felucca/blob/main/BUILDING.md) - How to build a Felucca-family firmware from source.
- [fm1-nes GETTING_STARTED](https://github.com/Keitark/fm1-nes) - Toolchain and SDK setup for writing firmware from scratch.

## Articles and reviews

- [M-VAVE FM-1 review](https://synthanatomy.com/2026/07/m-vave-fm-1-review-low-budget-pocket-fm-ynthesizer-with-iconic-sounds.html) - Synth Anatomy's full review.
- [FM-1 V15 update](https://synthanatomy.com/2026/07/m-vave-fm-1-a-budget-friendly-dx-7-style-desktop-fm-polysynth.html) - Launch coverage and the V15 feature rundown.
- [Patch librarian](https://synthanatomy.com/2026/07/m-vave-fm-1-patch-librarian.html) - On Benny Sparra's browser librarian.
- [Baud Girl FM-1+VA](https://synthanatomy.com/2026/09/baud-girl-fm-1-va-custom-m-vave-fm-1-firmware.html) - The first custom firmware.
- [Felucca](https://synthanatomy.com/2026/10/hugelton-instruments-felucca-custom-m-vave-fm-1-firmware-turns-it-into-a-multi-engine-synth.html) - Felucca 1.0 coverage.
- [SLOOP](https://synthanatomy.com/2026/10/3dsam-sloop-custom-firmware-turns-m-vave-fm-1-into-a-4-track-groovebox.html) - SLOOP coverage.
- [X0X](https://synthanatomy.com/2026/10/charles-vestal-x0x-custom-firmware-turns-the-m-vave-fm-1-into-a-rebirth-like-groovebox.html) - X0X coverage.
- [Groove OS](https://synthanatomy.com/2026/10/groove-os-turns-the-m-vave-fm-1-into-an-8-track-groovebox.html) - Groove OS coverage.
- [Custom firmware collection](https://pianoandsynth.com/m-vave-fm-1-custom-firmware-collection/) - Piano & Synth Magazine's comparison table of the firmwares.
- [Free custom firmware for Mvave FM-1](https://sonicstate.com/news/2026/09/29/free-custom-firmware-for-mvave-fm-1-/) - Sonicstate on FM-1+VA.
- [MatrixSynth: Felucca](https://www.matrixsynth.com/2026/10/fm-1-custom-firmware-felucca.html), [FM-1+VA](https://www.matrixsynth.com/2026/09/m-vave-fm-1-now-is-va-synthesizer-full.html), [Groove OS](https://www.matrixsynth.com/2026/10/groove-os-new-firmware-third-one-which.html) - Video round-ups.
- [Time To House](https://timetohouse.com/en/articles/m-vave-fm-1-budget-dx7-fm-synth) - Launch article.
- [Noizefield: SLOOP](https://noizefield.com/news/sloop-custom-firmware-turns-m-vave-fm-1-into-4-track-groovebox) - SLOOP coverage.

## Videos

- [M-Vave FM-1 Review - The $70 Pocket DX-7](https://www.youtube.com/watch?v=q3e2zH_-5I8) - Synth Anatomy's video review.
- [Maks Makes: MIDI CC mappings](https://www.youtube.com/watch?v=vWRd1A8I3gc) - Working out the effect CC numbers before M-VAVE published them.
- [Sound import tutorial](https://www.youtube.com/watch?v=zDfeGawNeJU) - Loading DX7 banks over SysEx.
- [Firmware V09 upgrade tutorial](https://www.youtube.com/watch?v=n-TShi-a5OA) - Official-style walkthrough of the updater.
- [Use the FM-1 as a Bluetooth MIDI controller](https://www.youtube.com/watch?v=Eu2BY2PxT5M) - Driving an iOS synth over BLE MIDI.
- [Can the FM-1 make a full song?](https://www.youtube.com/watch?v=a3yb4juRSuE) - No-talking demo track from factory presets.
- [FM-1+VA full tutorial](https://www.youtube.com/watch?v=jfuoEBIUsEE) - NatLife Sounds on the VA engine and new sequencer.
- [Felucca 0.9 full guide](https://www.youtube.com/watch?v=UzgbDjsFEpY) - Walkthrough and sound demo.
- [Felucca first look](https://www.youtube.com/watch?v=EzFknmhtKZk) - Multi-sequencer, engines and scale mode.
- [Felucca jam session](https://www.youtube.com/watch?v=XEK4VhsYwCE) - Live performance on Felucca.

## Communities

- [KVR Audio thread](https://www.kvraudio.com/forum/viewtopic.php?t=632127) - Long-running thread where the factory preset recovery and much of the early tooling were first shared.
- [Elektronauts thread](https://www.elektronauts.com/t/m-vave-fm-1/252170) - Workflow discussion and firmware news.
- [Gearspace thread](https://gearspace.com/threads/m-vave-fm-1.1465371/) - Owners' thread.
- [Plugg Supply](https://plugg-supply.net/forum/gear-plugins/m-vave-fm-1-patch-librarian-free-browser-tool-for-dx-7-sound-transfer) - Russian-language coverage and discussion.
- [GitHub topic: m-vave](https://github.com/topics/m-vave) - Repositories tagged with the brand.

## Related M-VAVE projects

Not about the FM-1, but the same company, often the same chips and the same reverse-engineering crowd.

- [smk37-firmware-custom-mod](https://github.com/amalahama/smk37-firmware-custom-mod) - Custom firmware and flasher for the SMK-37 Pro keyboard, which shares the FM-1's DX7 engine.
- [smk-37-pro-docs](https://github.com/jonathaslacerda/smk-37-pro-docs) - Community documentation for the SMK-37 Pro.
- [mvave-chocolate-sysex](https://github.com/cbix/mvave-chocolate-sysex) and [OpenChocolate](https://github.com/majabojarska/OpenChocolate) - SysEx protocol and open web configurator for the Chocolate footswitches.
- [mvave-blackbox-reverse-engineering](https://github.com/jakino0/mvave-blackbox-reverse-engineering) and [mvave-blackbox-edit](https://github.com/jvsobrinho/mvave-blackbox-edit) - Protocol research and a Web Bluetooth editor for the BlackBox amp modeller.
- [Cuvave Looper Pro protocol](https://gist.github.com/michaelforney/d3a2790bb5f8cbcb1c931eabb50b5f20) - SysEx protocol notes for the Looper Pro.

## Contributing

Contributions welcome. Read the [contribution guidelines](CONTRIBUTING.md) first.
