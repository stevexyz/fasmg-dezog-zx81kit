
This kit can be used to cross compile and debug assembler programs for ZX81. The toolchain is based on very powerful tools such as FasmG, ZEsarUX and Visual Studio Code, and has been put together with the kind support of @Maziac” (DeZog debugger author) and @Jacobly0 (Z80 compiler infrastructure for FasmG author).

The scope of the kit is not to explain how to program in assembler (for this there are many other sources), but to explain how to combine those very powerful tools, and the following steps provide basic instructions on how to start:

1. Install ZEsarUX (https://github.com/chernandezba/zesarux/releases), VSCode (https://code.visualstudio.com/docs/setup/setup-overview), and install DeZog extension inside VSCode. FasmG and Z80 scripts have been included for convenience but are available here https://flatassembler.net/download.php and here https://github.com/jacobly0/fasmg-z80. For the same convenience some other useful files with character set, rom addresses, etc. have also been provided

2. In order to compile the example program use the “./fasmg simple-zx81-example.asm”; the output will be the “.p” executable and the “.sld” listing file for DeZog

3. In the example directory launch ZesarUX with the command line “zesarux --enable-remoteprotocol --remoteprotocol-port 10000 --machine ZX81 --tape simple-zx81-example.p”

4. Run VSCode and open the directory of the example program ("code ."); load the “simple-example.asm” and set a breakpoint for example before writing the screen (after label “displaychar:”), and then “Run with Debug” inside VSCode and after program start press the "Run" in order to allow execution until breakpoint

5. Now if you go to ZEsarUX and press a key you’ll notice that the program will stop inside VSCode on the set breakpoint (note: do not click inside the zesarux window since it will stop execution, probably in the ROM display routines, but select window with title bar or “alt-tab”)

6. Other than standard VSCode facilities, DeZog offers additional ones as for example the memory inspector with "-mv 0x4000 1024" in the debug console. Please refer to the documentation for full features description https://github.com/maziac/DeZog
    
These instructions and the kit itself have been tested on Linux, even if they should for the most part be the same or very similar with other compatible platform available for the tools used

