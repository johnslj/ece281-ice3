# ECE 281 ICE 3: Ripple-Carry Adder with Top Level Design

This is a **template** repository.

[ICE 3 instructions](https://usafa-ece.github.io/ece281-book/ICE/ICE3.html)

Targeted toward Digilent Basys3. Make sure to install the [board files](https://github.com/Xilinx/XilinxBoardStore/tree/2018.2/boards/Digilent/basys3).

Tested on Vivado 2024.2

---

## GitHub Actions Testbench

The workflow uses the [setup-ghdl-ci](https://github.com/ghdl/setup-ghdl-ci) GitHub action
to run a *nightly* build of [GHDL](https://ghdl.github.io/ghdl/).

First, the workflow uses GHDL to **analyze** all `.vhd` files in `src/`.

Then it **elaborates** the entity defined by `$TB_ENTITY`

Finally, the workflow **runs** the simulation. If successful then it will quietly exit with a `0` code.
If any of the `assert` statements fail then GHDL will cease the simulation and exit with non-zero code; this will also cause the workflow to fail.
Assert statements of other severity levels will be reported, but not fail the workflow.

## Screenshots

![I chose to use 7 test cases. This included the original all zeros and all ones test cases, along with the suggested all zero with the carry-in, along with a standard no carry-in or -out case (67 case), a case which would strattle the line of needing the carry-out (69 no carry-in and 69 carry-in case), and finally a case which would use the carry out (the cd case).](waveform.png)

![This is my entity diagram:](entity_diagram.png)

## Documentation
My ChatGPT transcript is: https://chatgpt.com/share/698c1743-736c-8001-ba32-2dc1bd00a0a5
note that the first few prompts are lab 1 prompts, I continued with the same chat
