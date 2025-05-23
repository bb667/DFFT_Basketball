# DFFT_Basketball
DFFT NBA tracking data. Both for abstract using for MIT SSAC 2024 and subsequent paper.

The following is regarding files used in the abstract SSAC:

mat_{o,d}_R{0,3} represent the overall offense (o) and deffense (d) density with the corresponding result of the play (0) or (3). The court was partitioned into 100 blocks. The shape is [play positions, block location along x, block location along y]

data500_R{0,3} shows 500 positions of the offense and defensive that result in a (0) or (3) otucome. 

mats500_{o,d} show the individual player densities generated from the data500 positions. The shape is [500 play positions, 5 players, block location along x, block location along y]

single_positions_{o,d}_SSAC represents the offense (o) and deffense (d) positions for the play shown in the abstract to SSAC. The data is the same as mats500 but for a single play position.
single_positions_locs_SSAC represents a column indicating [Ox1, ..., Ox5, Oy1, ..., Oy5, Dx1, ..., Dx5, Dy1, ..., Dy5, Result of shot = 3]

Note that when going from individual positions to the overall density of the offense or defense to the integer forms found in mat_{o,d}_R{0,3}), the procedure in the SSAC abstract was to sum over all players of that type, set the upper limit of the density to 0.5, and applying the floor division '//' by 0.02. This was simply to discritize the densities to possible 25 values, which was used in the abstract.

Regarding files for the paper submission. They are too large to be placed on github, but link here: https://drive.google.com/drive/folders/1xB4Lg1JrhVjAZBkr2o-yw_m-E0NDX3-v?usp=drive_link

data_R{Shot Result}_reduced represents data with the corresponding shot result (0, 2, 3). It contains the following ['O1x', 'O1y', 'O2x', 'O2y', 'O3x', 'O3y', 'O4x', 'O4y', 'O5x', 'O5y', 'O1p', 'O2p', 'O3p', 'O4p', 'O5p', 'D1x', 'D1y', 'D2x',
'D2y', 'D3x', 'D3y', 'D4x', 'D4y', 'D5x', 'D5y', 'D1p', 'D2p', 'D3p','D4p', 'D5p', 'Bx', 'By', 'Tshot']. Note that the x values go from -25 to 25 and the y values goes from 0 to 50, for the half-court to be taken to be 50 feet by 50 feet.

Which corresponds to the offense player x and y positions and 'p' indicating an identification for the player. Similar for offense. Then the ball position and the time until the shot is taken (Tshot).

The densities generated by the positions are in the respective mats_o for offense and mats_d for defense. These densities were created by creating a Gaussian for each player with a standard deviation of 5 feet and discretizing the half-court into 5 by 5 feet squares (so 100 bins overall). These npy files show the density generated by each player. In the paper, after summing over all players of the same type (offense or defense) the densities are discretized to 20 levels (14 in the SSAC version of the paper).

