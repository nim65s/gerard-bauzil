3D model of the Gerard Bauzil experimental room
===============================================

People involved in the design process:

Kilian Lirola: Roof + koroibot staircases
Alexandre Girard: Estrade + HRP-2 box
Perrinne Collet: Desktop and drawers
Christophe Bonnefond: Furniture
Olivier Stasse: overall integration + Blender beautification

### Generate DAE from AprilTag png files

Run the command `scripts/april-tag-to-dae.py -h`
to get some help on how to do this.

The following bash script was used to generate some images.
```bash
ids="50 51 52 53"

for id in ${ids}; do
  scripts/april-tag-to-dae.py --cubesize 1. --family 36h11 --number ${id}
done
```
