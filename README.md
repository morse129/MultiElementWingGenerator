# Multi-Element Wing Generator

![gui_image](/MultiElementWingGenerator_resources/screenshot.png)


## What is it?

A MATLAB Graphical User Interface (GUI) app to parameterize two- and three-element wings. I wrote this as an undergrad on the [Gopher Motorsports](https://gophermotorsports.com/) Formula SAE (Formula Student) team at the University of Minnesota.

In the Formula SAE rules (at least at the time), the wings are required to fit in a rules box, so often you end up designing the largest wing to fit within a certain area. That was the motivation for this app: the GUI takes the airfoil profile, length, and angle of the main element (and optionally a second flap) and adjusts the first flap (given the desired slot gaps) to ensure the entire wing fits within the defined box. The wing profile can then be saved in SolidWorks or ANSYS file formats for input into your favorite CFD software.


## How do I install it?

Simply download **MultiElementWingGenerator.mlappinstall**, navigate to the **Apps** tab in MATLAB, and click **Install App**. Select the file **MultiElementWingGenerator.mlappinstall** to complete the installation. Then the app can be opened from the MATLAB Apps Toolbar.


## How do I use it?

To get started using the app, at a minimum you need to specify the parameters of the main element and the box size. If you would like a second flap, toggle this option on and enter its parameters. Different airfoil profiles can be selected with the drop-down menu for each element!

To visualize the wing profile, click **Preview**.

If everything looks good, enter a save name in the **Group Save Name** field and toggle to whichever file format you'd like. Then you can click **Save** to save the curve file(s) and a text file containing the wing parameters.


## What are all these input options?

Play around to make your own multi-element wing!

* **Box dimensions**: Height and width of the box for wing to fit within.
* **Main element**: Airfoil profile, chord length, angle of attack (degrees).
* **Flap 1**: Airfoil profile.
* **Flap 2**: Airfoil profile, chord length, angle of attack (degrees).
* **Slot gaps**: The horizontal and vertical dimensions of slot gaps 1 and 2 can also be specified (if you leave these boxes blank, default values are 2 percent of box diagonal).
* **Group save name**: Save name to prepend on output files.
* **File type**: Toggle to change between ANSYS and SolidWorks curve file formats.


## Which files does it create?

Wing geometry files are saved in either SolidWorks format (3 curve files) or ANSYS format (1 curve file). An accompanying wing parameter text file detailing the parameters of the generated wing is also saved. All files are saved in the current folder.


## Why are the airfoil curves not saved as closed loops?

This behavior was chosen due to peculiarities in the way that SolidWorks/ANSYS handles imported curves. After you import the wing, connect the open ends of the profile using a line. Then you should be able to extrude the profile to create a three-dimensional wing.


## Which airfoils are included?

I've included the airfoils in the [UIUC Airfoil Database](https://m-selig.ae.illinois.edu/ads/coord_database.html) and Enrico Benzing's airfoils from [Ali/Wings](http://www.benzing.it/enrico.profili.htm).


## How do I add additional airfoils?

Airfoils can be added by adding their name and coordinates (airfoil.name and airfoil.coord, respectively) to the structure defined in the airfoildatabase.mat file. The airfoil coordinates must be given as (x,y) coordinates. The coordinate points must start from the trailing edge, move forward to the leading edge, and continue back to the trailing edge.


## Credit

If you gained any value out of this app, give it a star on GitHub!

This app was created (a long time ago) by Nick Morse. I'm not actively maintaining this repo, but if you encounter problems, please raise them as an [issue](https://github.com/morse129/MultiElementWingGenerator/issues).