# DFFT_Basketball
Reduced Synergy NBA tracking data for SSAC

mat_{o,d}_R{0,3} represent the overall offense (o) and deffense (d) density with the corresponding result of the play (0) or (3). The court was partitioned into 100 blocks. The shape is [37594 play positions, block location along x, block location along y]

data500_R{0,3} shows 500 the positions of the offense and defensive that result in a (0) or (3) otucome. 

mats500_{o,d} show the individual player densities generated from the data500 positions. The shape is [500 play positions, 5 players, block location along x, block location along y]

single_positions_{o,d}_SSAC represents the offense (o) and deffense (d) positions for the play shown in the abstract to SSAC. The data is the same as mats500 but for a single play position.
single_positions_locs_SSAC represents [index in external data set (ignore), Ox1, ..., Ox5, Oy1, ..., Oy5, Dx1, ..., Dx5, Dy1, ..., Dy5, Result of shot]
