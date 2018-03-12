# Making plots from DQMIO root files

As an example: If you want to make the EtaBToJpsiJpsi plots, using the HLT_Dimuon20_Jpsi_Barrel_Seagulls_v path you can do the following:

```bash
phys_utils/python/PlotUtils/createDQMCompPlots.py --startdir 'DQMData/Run 1/HLT/Run summary/BPH/reHLT' \
--regex HLT_Dimuon20_Jpsi_Barrel_Seagulls --outdir EtaBJpsJpsi_plots \
--keys 9_2_8,9_2_7 9_2_8_files/EtaBToJpsiJpsi_DQM.root 9_2_7_files/EtaBToJpsiJpsi_DQM.root
```

- The `startdir` is the toplevel TDirectory in the file that will be considered. In this case it starts at the BPH folders, and the DQMIO file has been produced locally with the `processName` and `hltProcess` changed to `reHLT`.
- The `regex` option can be used to select a given path or a subset of plots to be plotted (The regex is matched against the full name of the plot in the root file including the TDirectory path to it).
- The `outdir` specifies into which directory the plots will be stored (each path gets its own subdirectory)
- The `keys` can be used to label the different input files (sam order as the inputfiles)

The above command will thus create a `EtaBToJpsiJpsi_plots/HLT_Dimuon20_Jpsi_Barrel_Seagulls_v/` directory containing all the plots available for this path.
