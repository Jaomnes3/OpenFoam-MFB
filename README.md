# OpenFoam-MFB
Modification of the OpenFoam tutorial: lagrangian/DPMFoam/Goldschmidt.

12/22/19
Alterations
(1)blockMeshDict was altered into a cylinder(r=1.5mm, h=15mm).
(2)U.air, p were altered to reference the surfaces of the altered blockMeshDict.
(top→atmosphere, bottom→walls,　walls→sides)
(3)U.water was created from a copy of U.air, in response to error report.
(4)constant/transportProperties: "rho.water = 1000" was added in response to error report.

The final error indicated that the "parcelInjectionCell" coordinates were those of
 particles outside of the newly created cylindrical object.
Therefore, the next step is the generation of a random assortment of particles positioned within the cylinder,
 dictated by "constant/kinematicCloudPositions". 

References 
https://bugs.openfoam.org/view.php?id=1119
