# Gmx_Tools

This is a python package to help with data analysis of Molecular Dynamics simulations from GROMACS.

It is recommended to import gmx_tools as gt

## Requirements
- NumPy
- Matplotlib

### xvg module

The xvg module allow to parse .xvg file generated from GROMACS and create an XVG object.
You can then extract 3D coordinates using mdt.XVG.get3Dcoord() (if the .xvg file was generated using gmx traj -ox for example) or simply generate a plot using mdt.XVG.plot().

### mixsolvmd module

The mixsovlmd module can generate hotspot from Mixed Solvent MD simulations.\
It requires:
  - 3D trajectories from simulations of all the probes for each timestep in complexe with another molecule (protein, DNA, RNA, lipid bilayer, etc...) and in bulk (water only).
  - The size of the box and the metric (only support rectangular box and nm or Ang as metrics)
  - The temperature used during the simulations

### binding_events function

The binding_events function allows to determine the number of binding events (and their retention time) that happened during a simulation.
It requires:
  - XVG file of the trajectory of the center of mass of the ligand(s) (accept multiple ligands).
  - XVG file of the trajectory of the center of mass of the site of interest.
