INSTRUCTIONS
------------

Example on how to interpolate a data cube using GPRPy.

Requirements: Data profiles with either "Easting, Northing, Elevation"
or "X, Y, Z" coordinates given.


In this example, we laid out tape measures in a rectangular area and
collected GPR data along parallel profiles in two directions, first
parallel to the x-axis, then parallel to the y-axis.

Thanks to this simple approach, we can automatize the creation of the
3D-coordinate information for the profiles. Run

python prepareTopo.py

(or python3 prepareTopo.py)

to automatically generate the 3D-coordinate data for this survey.



Next, process and save each profile. The easiest way to do that is to use
the profile GUI to process a single (representative) profile, then
export the GPRPy script, and finally run through the exported
processing steps for all profiles (using a for-loop).

Python script processAll.py shows how that can be done.

Run

python processAll.py

(or python3 processAll.py)


We can now combine and interpolate the processed profiles.

Run

python createDataCube.py

(or python3 createDataCube.py)

Open createDataCube.py with an editor to see the options for the GPRPy
function "makeDataCube", which is used for 3D data interpolation. You
can set the data cube's resolution in x-, y- and z-direction, set
Gaussian smoothing, force absolute values, etc.

You can open the resulting file 'Cube.vts' with for example Paraview:
https://www.paraview.org/
