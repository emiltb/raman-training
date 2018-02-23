# Raman analysis tutorial using Wire 4.3

**Whatever you do, always have a backup of the original datafile before you do any processing!**

## Open ”NiG spectra.wdf”

This is just a single recorded spectra. All information about the experiment is stored in the file, so see if you can find out how it was done.

* Which laser was used?
* What was the exposure time, how many accumulations?
* Which objective was used for recording the spectrum?

Export the original spectrum to a .txt file.

Use the tools within Wire to do the following:

* Subtract the baseline
* Truncate the spectrum to remove the uninteresting regions at either end
* Normalize the spectrum to a maximum intensity of 1
* Export the modified data to a .txt file


## Open “IntercalatedGraphite.wdf”

Go to View > View map data, to examine the region where the spectra were recorded.

The spectra contain 2 interesting peaks for graphene – the D-peak at ~1340 cm-1 and the G-peak at ~1580 cm-1. We will mainly work with these.

The following steps can be done in order to process a map. They might not all be strictly necessary, that depends a lot on your data. Unfortunately no data processing can be done while the map view is open, so start by closing that.

Use the tools within Wire to do the following:
* The map contains a couple of cosmic rays, which will disturb a curve fitting. Use the cosmic ray removal tool to find and remove these. This might need several iterations.
* Do a baseline subtraction for all of the spectra. Try to look at the properties (right click) – which parameters do you think would be best to use?
* Use the Mapping review tool to plot a Signal to baseline plot of the G peak. Note that this requires no curve fitting. 
* Use the curve fit tool to set up a curve fit. It should fit the three main peaks with proper labelling, lorentzian peak shape and no baseline (since we already corrected that). Once the fit looks good for one of the spectra, right click and go Curve parameters > Save. This file will be used as the ‘guess’ for fitting the rest of the data. Then right click on the spectrum and exit curve fitting by Accepting or Rejecting (it does not really matter). 
* Now go to the Mapping review tool again and plot the following: G1 intensity, G2 intensity and D intensity. The first time you will need to use the curve parameters file you just made to fit all the data. 
* Make sure that your Wire datafile is saved, as the programme might crash now.
* Use the mapping review tool to make ratio maps with G2 intensity / G1. View these two maps and adjust the color scale using the LUT control. Save these as images. 
* Export the ratio maps you just made to a .txt file.

### Functions that were not covered in this walk-through

A couple of things are possible, which we did not go through. Play around with these or look in the manual.
 
* Exporting individual peaks in a curve fit
* Exporting full datasets

* Data arithmetic
* Differentiate
* Noise filter

* Smooth
* Integrate
* Peak pick
