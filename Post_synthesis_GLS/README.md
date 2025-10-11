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
read_verilog /home/thomas_ubuntu/VSDBabySoC_1/VSDBabySoC/src/module/vsdbabysoc.v
read_verilog -I /home/thomas_ubuntu/VSDBabySoC_1/VSDBabySoC/src/include /home/thomas_ubuntu/VSDBabySoC_1/src/module/rvmyth.v
read_verilog -I /home/thomas_ubuntu/VSDBabySoC_1/VSDBabySoC/src/include /home/thomas_ubuntu/VSDBabySoC_1/src/module/clk_gate.v
```

<div align="center"><img src="images/soc_read.png" alt="Alt Text" width="500"/> </div>
