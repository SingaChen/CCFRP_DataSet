# CCFRP_DataSet
## Update on 2021/12/03
Here we provide another format for CCF waypoints, named __Generator_XXX_raw.tx__, you may find it in folders.

The explanation is shwon below:
1. "S" Start of a toolpath
2. "E" End of a toolpath
3. "X-42.1257 Y9.50999 Z0.25" The waypoints for CCF.

*Note that only toolpath of CCF is recorded in this file*
****
This is the dataset of our continuous carbon fibre printing project

There are 4 models in the dataset, namely Bar, Shell, Loop and Wrench.

Please refer to the .obj files for 3D view, which are the input of TetGen(.tet) files.

Three printing strategies are generated for all models, namely FDM, Zigzag_Contour, and Ours.

The FDM strategy is similar with traditional FDM printing, only PLA layers are printed along one direction and the angle difference is 45 degrees between neighboring layer.

For the Zigzag_Contour strategy, continuous carbon fibres (CCF) layers interspersed within PLA layers. The pattern of CCF layer is similar with PLA layer, that is zigzag-contour toolpath.

Ours’ approach is designed to print CCF along with the direction of principal stress over the PLA layer, for more details, please refer to our paper.

For your better understanding of the G-code, some explanation is shown below:

1. “G92 E0” reset the extruder and change the extrusion to 0;

2. “T0/T1” change the printing head, “T0” means the printing head of PLA material while “T1” stands for CCF.

3. “G0 F120 X59.973 Y7.527 Z4.250 E0.000” The travel command, to move the printing head without extrusion.

4. “G1 F120 X59.973 Y7.527 Z0.250 E1.000” The printing command, to move the printing head and printing at the same time.

5. “W” Wait command, to wait for 1 second, only used in CCF printing.

6. “C” Shearing command, to shear the continuous carbon fibres, always used at the end of printing.
