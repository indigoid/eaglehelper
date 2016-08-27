# eaglehelper

## what?

Makefile to simplify generation of Gerber zip files for assorted
PCB fab shops, to match their provided CAM files for Cadsoft Eagle.

Currently-supported board houses are:

* Hackvana
* Seeed Studio
* OSH Park

Others could be trivially added. These are the three shops I use.

## why?

I made it to save typing and reduce errors. Errors in Gerber
packaging could trivially lead to your PCBs not being manufactured
as you intended, and thus wasting money.

## how?

1. Clone this repository somewhere on your workstation.

2. In each project directory, create a Makefile that looks like the below:

    # this should be the name of your Eagle .brd file, without
    # the .brd suffix
    basename=project_name_here

    # change this path to wherever you cloned eaglehelper
    include $(HOME)/Documents/eagle/eaglehelper/Makefile.include

3. Use Eagle's CAM processor to generate the Gerber files for your
preferred PCB fab shop

4. In your terminal, type one of the below, as appropriate:

    make oshpark

    # or

    make seeed

    # or 
    make hackvana

5. Inspect the resulting `.zip` file with a Gerber viewer

