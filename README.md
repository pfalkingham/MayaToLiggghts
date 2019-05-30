# MayaToLiggghts
My scripts for converting a (fairly specific) maya scene to input files for LIGGGHTS


These Mel scripts can be called from the Maya Command line, or better yet from a custom button on the shelf that calls 
  "plfExport_Liggghts;"
  
In Maya, your scene should:
 - Have z=up (for gravity)
 - Be scaled to correctly (and maya scene left in cm scale)
 - Have a tray that will contain particles called "simtray"
 - Have an identical tray called SIMINS1 (particles will be inserted into this tray)
   - Both of the above are generally produced via creating a cube and deleting the face on top.
 - Have a box around the entire simulation domain called "SIMBOX1" - this must include full extents of any moving object.
 - Moving object(s)
  
Select all moving objects + simtray, then run "plfExport_Liggghts;"

You will see moving objects jittering through the full animation sequence.
