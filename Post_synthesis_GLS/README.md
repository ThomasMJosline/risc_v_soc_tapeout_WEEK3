# Post Synthesis GLS of BabySoC
---

During GLS of BabySoC, the following are verified:
 
 - Whether the design meets timing requirements.
 - Whether the logical behaviour remains same after realizing the design with standard cells.
 - To see whether the submodules in BabySoC interact with each other properly.

---
### Procedure for post synthesis GLS:
---

#### 1. Load the modules into Yosys:

Invoke Yosys and load the modules
```
$yosys
```

```
$read_verilog /home/thomas_ubuntu/VSDBabySoC_1/VSDBabySoC/src/module/vsdbabysoc.v
$read_verilog -I /home/thomas_ubuntu/VSDBabySoC_1/VSDBabySoC/src/include /home/thomas_ubuntu/VSDBabySoC_1/src/module/rvmyth.v
$read_verilog -I /home/thomas_ubuntu/VSDBabySoC_1/VSDBabySoC/src/include /home/thomas_ubuntu/VSDBabySoC_1/src/module/clk_gate.v
```

<div align="center"><img src="images/soc_read1.png" alt="Alt Text" width="700"/> </div>
<div align="center"><img src="images/soc_read2.png" alt="Alt Text" width="700"/> </div>
<div align="center"><img src="images/soc_read3.png" alt="Alt Text" width="700"/> </div>

#### 2. Load the Liberty files:

```
$read_liberty -lib /home/thomas_ubuntu/VSDBabySoC_1/VSDBabySoC/src/lib/avsdpll.lib
$read_liberty -lib /home/thomas_ubuntu/VSDBabySoC_1/VSDBabySoC/src/lib/avsddac.lib
$read_liberty -lib /home/thomas_ubuntu/VSDBabySoC_1/VSDBabySoC/src/lib/sky130_fd_sc_hd__tt_025C_1v80.lib
```

<div align="center"><img src="images/soc_lib.png" alt="Alt Text" width="700"/> </div>

#### 3. Run synthesis:

```
$synth -top vsdbabysoc
```
- The list of standard cells used can be seen as:
<div align="center"><img src="images/soc_clk.png" alt="Alt Text" width="500"/> </div>
<div align="center"><img src="images/soc_rvmyth.png" alt="Alt Text" width="500"/> </div>
<div align="center"><img src="images/soc_vsd.png" alt="Alt Text" width="500"/> </div>

- The heirarchy of modules:
  <div align="center"><img src="images/soc_heir.png" alt="Alt Text" width="500"/> </div>


