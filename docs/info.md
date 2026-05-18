<!---

This file is used to generate your project datasheet. Please fill in the information below and delete any unused
sections.

You can also include images in this folder and reference them in the markdown. Each image must be less than
512 kb in size, and the combined size of all images must be less than 1 MB.
-->

## How it works

This is a SKY130 mixed-signal frequency synthesizer / PLL test vehicle. It includes a custom ring VCO, DAC-controlled VCont tuning path, divided clock output path, TDC/RS-latch debug interface, and a small digital debug/control macro.


## How to test

1. Power the design with 1.8 V on `VDPWR` and ground on `VGND`.
2. Apply a reference clock to `clk`.
3. Set `ui[5] = 1`, drive an 8-bit DAC code on `uio[7:0]`, then toggle/wait for the reference clock to latch the DAC code.
4. Set `ui[5] = 0` to enable debug outputs on `uio[7:0]`.
5. Use `ui[3:1]` to select debug mux pages.
6. Observe divided VCO/debug outputs on `uo[7:0]` and `uio[7:0]`.
7. Sweep the DAC code and measure VCO tuning behavior through the divided output.

## External hardware

1. Power supply
2. Oscilloscope
