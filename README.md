# MayaToLiggghts
My scripts for converting a (fairly specific) maya scene to input files for LIGGGHTS


These Mel scripts can be called from the Maya Command line, or better yet from a custom button on the shelf that calls 
  "plfExport_Liggghts;"
  
In Maya, your scene should:
 - Have z=up (for gravity)
 - Be scaled to correctly (and maya scene left in cm scale)
 - Motion will be calculated as though 240 frames = 1 second, regardless of maya frame rate setting.
 - Have a tray called SIMINS1 (particles will be inserted into this tray)
   - Generally produced via creating a cube and deleting the face on top.
   - Keep this as small as possible to reduce particle numbers, but large enough to avoid edge effects
 - Have a box around the entire simulation domain called "SIMBOX1" - this must include full extents of any moving object.
 - Moving object(s)
  
Select all moving objects, then run "plfExport_Liggghts;" or "plfExport_Liggghts_deformable;"

You will see moving objects jittering through the full animation sequence.


TO-DO:

- For some reason coefficient of restitution ($cr) is not longer recognised by liggghts - need to hardcode for now.  <-- I think this is because I already have a variable 'c' and it's using that?
- double check if I want sjkr or sjkr2 for material properties (I had issues with sjkr in previous versions of liggghts and moved to sjkr2 which is 'stickier'

IF YOU USE THESE SCRIPTS, PLEASE CITE THE FOLLOWING PAPERS (which were instrumental in the development of these scripts):
Falkingham, P.L. and Gatesy, S.M., 2014. The birth of a dinosaur footprint: subsurface 3D motion reconstruction and discrete element simulation reveal track ontogeny. Proceedings of the National Academy of Sciences, 111(51), pp.18279-18284.

Falkingham, P.L., Turner, M.L. and Gatesy, S.M., 2020. Constructing and testing hypotheses of dinosaur foot motions from fossil tracks using digitization and simulation. Palaeontology, 63(6), pp.865-880.

Hatala, K.G., Gatesy, S.M. and Falkingham, P.L., 2021. Integration of biplanar X-ray, three-dimensional animation and particle simulation reveals details of human ‘track ontogeny’. Interface focus, 11(5), p.20200075.
