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
  
Select all moving objects, then run "plfExport_Liggghts;"

You will see moving objects jittering through the full animation sequence.


TO-DO:

- For some reason coefficient of restitution ($cr) is not longer recognised by liggghts - need to hardcode for now.
- double check if I want sjkr or sjkr2 for material properties (I had issues with sjkr in previous versions of liggghts and mvoed to sjkr2 which is 'stickier'
