# MIRRORS (MultIspectRal imaging RadiOmetRy Software)
### v1.6

Xtools is a suite of programmes I am developing that are designed to be of use at the synchrotron during X-ray diffraction experiments performed at high pressure and high temperature conditions. Currently two tools are available:

1. A PV converter. This converts pressure to volume and vice versa for a variety of important high-pressure mineral phases.

2. A RFS/Raman converter. This converts pressure determined from ruby fluorescence spectroscopy to pressure determined by Raman spectroscopy of the diamnod anvil and vice versa

The tools are written in Python and are implemented within a Jupyter Notebook, which allows users to operate the tools themselves as well as view the underlying code. It also allows the programmer to add interactive widgets and provide explanatory notes. See jupyter.org to find out more about this incredibly useful open source project.

## Getting Started

These instructions will get you a copy of the project up and running on your local machine.

### Installing

[![Binder](http://mybinder.org/badge.svg)](http://mybinder.org:/repo/otlord/xtools)

Xtools requires nothing more that a web browser to run using the MyBinder service (see badge above). his service essentially allows you to build an executable version of any Jupyter Notebook within a specific GitHub repository that can then be accessed via any web browser (though check its status - the service is sometimes unavailable). The result is that your code is immediately available to anyone even if they don't have Python installed on their local machine. Just click the button above and then click on Xtools.ipynb in the resulting browser tab followed by:

```
Cell | Run All
```

Alternatively, 

Installation is simple. Simply navigate to https://github.com/olivertlord/MIRRORS and download the .ZIP file and extract it into your chosen directory. Alternatively, if you have git installed, then at the command line type:

```
cd targetdirectory
git clone https://github.com/olivertlord/MIRRORS.git
```
This will craete a clone of the GitHub repository called ```MIRRORS``` inside ```targetdirectory```

To run MIRRORS, simply open Matlab, navigate to the MIRRORS directory and then type

```
MIRRORS
```

To add the MIRRORS directory to the Matlab PATH, at the Matlab command prompt type:
End with an example of getting some data out of the system or using it for a little demo

```
location = userpath
location = location(1:end-1)
cd(location)
edit startup.m
```

At this point, if you are prompted to create ```startup.m```, then do so. In the new .m file that opens in the Editor, add the following line and resave:

```
addpath(genpath('~/MIRRORS'));
```

Where ```~/MIRRORS``` is the full path to your MIRRORS directory. Now, next time you start Matlab, MIRRORS will be on the Matlab PATH and you can type MIRRORS at the command prompt from any directory and the GUI should run.

### Testing

To check that MIRRORS is working correctly, a set of example data files are provided, along with screnshots of the MIRRORS GUI after processing and output files containing the epected results. Below are instructions on how to process these files and check that the output matches expectations.

To test your insatallation:

1. Run MIRRORS by typing ```MIRRORS``` at the Matlab command prompt.

2. Once the GUI has opened, click the 'Post process' button. 

3. Navigate to the folder ```/MIRRORS/example/data``` and click 'Open'. 

4. Click 'Select ROI' and then double click inside the white rectangle that appears in the summary plot window at the bottom right of the GUI. The 'Select ROI' button should go green.

5. Type '1' in the 'Start' box and '11' in the 'End' box. Both should go green.

6. Check that the tickboxes and radiobuttons match those in ```/MIRRORS/example/data/test_1/test_1.png```.

7. Click 'Process'. Once processing is complete, the GUI window should look like ```/MIRRORS/example/data/test_1/test_1.png```.

8. A new folder should appear in ```/MIRRORS/example/data``` of the form ```MIRRORS_output_xx_xxx_xxx_xx_xx_xx``` where the x's denote the date and time. Inside that folder should be 13 files, 11 of the form ```example_xxx_map.txt``` where xxx is 001 to 011, 1 called ```data_SUMMARY.txt``` and 1 called ```data_VIDEO.avi```.

9. To check the output of your installation against the benchmark data provided in the software, type the following commands in the Matlab command line (this assumes you are in the folder ```MIRRORS```:

```
new = textread('example/data/MIRRORS_output_22_Feb_2018_15_20_40/data_SUMMARY.txt');
benchmark = textread('example/data/test_1/data_SUMMARY.txt');
difference = new-benchmark
```
The resulting output should look like this:

```
difference =

     0     0     0     0     0   NaN
     0     0     0     0     0     0
     0     0     0     0     0     0
     0     0     0     0     0     0
     0     0     0     0     0     0
     0     0     0     0     0     0
     0     0     0     0     0     0
     0     0     0     0     0     0
     0     0     0     0     0     0
     0     0     0     0     0     0
     0     0     0     0     0     0
```

10. Repeat steps 6-9 for each of the 8 tests. If the resulting output looks like that in step 9 for every test, then the software is working correctly.

### Hardware specific code edits

Before using MIRRORS, you will need to edit the code to match your hardware. Find the following lines in ```mapper.m```:

```
%//////////////////////////////////////////////////////////////////////////
% HARDWARE SPECIFIC - REQUIRES EDITING
% Wavelengths in nm
wa = 670.08; %top left
wb = 752.97; %top right
wc = 851.32; %bottom left
wd = 578.61; %bottom right

% Values of Spectral Radiance of calibration source at each wavelength in 
sr_wa = 7.26917; 
sr_wb = 9.86540; 
sr_wc = 12.0780; 
sr_wd = 4.19100;
%//////////////////////////////////////////////////////////////////////////
```

You will need to change the values `wa`,`wb`,`wc`,`wd`, to match the wavelngths of the filters used in your system, being careful to correctly match the wavelgnth of the image to its quadrant in the image. You will also need to change the values of `sr_wa`,`sr_wb`,`sr_wc`,`sr_wd` to the spectral radiance of your calibration source at the relevant wavelength.

### Troubleshooting

Should the testing procedure fail, or if you detect any bugs during use, then please contact me (Oliver Lord) at <oliver.lord@bristol.ac.uk>. Suggestions for new features are also welcome.

## Authors

* **Oliver Lord, School of Earth Science, Univeristy of Bristol** - (https://github.com/olivertlord, https://seis.bristol.ac.uk/~glotl/index.html)

* **Weiwei Wang, Innovative Technology and Science Ltd** - (http://www.innotecuk.com/)

## License

This project is licensed under the GNU General Public Licence Version 3 - see the [LICENSE.md](LICENSE.md) file for details

## Acknowledgments

* Mike Walter, Director, Gephysical Laboratory, Carnegie Institution of Washington for help and advice on all things radiometic
* The students and post-doctoral researchers at the DAC lab, School of Earth Sciences, University of Bristol, who tested the software, detected numerous bugs and suggested improvements.
* I (Oliver Lord) would like to acknowledge support from the Royal Society in the form of a University Research Fellowship (UF150057) and the Natural Environment Research Council (NERC) in the form of an Post-doctoral Research Fellowship (NE/J018945/1).

## References

* Briggs, R., Daisenberger, D., Lord, O. T., Salamat, A., Bailey, E., Walter, M. J., & McMillan, P. F. (2017). High-pressure melting behavior of tin up to 105 GPa. Physical Review B, 95(5), 054102. http://doi.org/10.1103/PhysRevB.95.054102

* Campbell, A. J. (2008). Measurement of temperature distributions across laser heated samples by multispectral imaging radiometry. Review of Scientific Instruments, 79(1), 015108. http://doi.org/10.1063/1.2827513

* Fischer, R. A., & Campbell, A. J. (2010). High-pressure melting of wustite. American Mineralogist, 95(10), 1473–1477. http://doi.org/10.2138/am.2010.3463

* Walter, M. J., & Koga, K. T. (2004). The effects of chromatic dispersion on temperature measurement in the laser-heated diamond anvil cell. Physics of the Earth and Planetary Interiors, 143-144, 541–558. http://doi.org/10.1016/j.pepi.2003.09.019

