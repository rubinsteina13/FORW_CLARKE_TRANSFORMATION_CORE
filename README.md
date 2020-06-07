# Synthesizable SystemVerilog IP-Cores of the Forward and Backward Clarke Transformation

Attention! This Clarke Transformation IP-Cores works in case when A + B + C = 0 only !!! (where A,B,C - input vectors).
[More information about Clarke Transformations here](https://en.wikipedia.org/wiki/Alpha%E2%80%93beta_transformation).

* Project structure
	* README.md - current file
	* LICENSE - file with license description
  * forw_clarke_module.sv - Synthesizable Digital IP-Core of the Forward Clarke Transformation
  * inv_clarke_module.sv  - Synthesizable Digital IP-Core of the Backward (Inverse) Clarke Transformation

# forw_clarke_module description

* User constants
  * DATA_WIDTH - input and output signals bus bit resolution
* Inputs
  * clk_i - clock signal (rising edge is active)
  * rst_i - reset signal (high level is active)
  * a_i   - input vector A
  * b_i   - input vector B
* Outputs
  * al_o  - output vector Alpha
  * be_o  - output vector Beta
* Pseudocode
	* al_o = a_i;
	* be_o = (a_i + 2 x b_i)/sqrt(3);

# inv_clarke_module description

* User constants
	* DATA_WIDTH - input and output data bus resolution
* Inputs
	* clk_i - clock signal (rising edge is active)
	* rst_i - reset signal (high level is active)
 	* al_i  - input vector Alpha
 	* be_i  - input vector Beta
* Outputs
 	* a_o   - output vector A
 	* b_o   - output vector B
* Pseudocode
	* a_o = al_i;
  *	b_o = (sqrt(3) x be_i - al_i)/2;
  
# License
  
[MIT](./LICENSE "License Description")
