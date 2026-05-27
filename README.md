# VASP 6.5.0 - Localized Orbital Locator + Electron Localizability Indicator
This repository contains a patch for VASP v6.5.0 that:
1. Enabling calculation of the Localized Orbital Locator (LOL)
2. Enabling calculation of the Electron Localizability Indicators (ELI) parallel-spin electron pair density (D)

It is essentially a copy of the patch from @Chengcheng-Xiao for VASP v6.3.0 but updated for v6.5.0. The original can be found [here](https://github.com/Chengcheng-Xiao/VASP_LOL) and all credit should be pointed his way.


## Applying patch
1. Copy `VASP6.5_ELI_D.patch` into your VASP source folder and run the following:
```
patch -p0 < VASP6.5_ELI_D.patch
```

2. Compile/recompile VASP.

## Running calculations
Setting `LLOL=.TRUE.` in `INCAR` file will enable the calculation of LOL at the end of the single point cycle.
A file named `LOLCAR` is generated after the calculation.

Setting `LELID=.TRUE.` in `INCAR` file will enable the calculation of ELID at the end of the single point cycle.
A file named `ELIDCAR` is generated after the calculation.

## Disclaimer

*1. VASP is a commercial package, be sure you have a proper license to use it.

*2. This repo is based on the patch located [here](https://github.com/Chengcheng-Xiao/VASP_LOL)

*3. The correctness of this patch has been checked with few simple cases.
However, this is not guaranteed to work for your specific system. Make sure you KNOW WHAT YOU ARE DOING!
