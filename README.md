# Xtools
### v1.0

[![DOI](https://zenodo.org/badge/83300016.svg)](https://zenodo.org/badge/latestdoi/83300016)

Xtools is a suite of programmes I am developing that are designed to be of use at the synchrotron during X-ray diffraction experiments performed at high pressure and high temperature conditions. Currently two tools are available:

1. A PV converter. This converts pressure to volume and vice versa for a variety of important high-pressure mineral phases.

2. A RFS/Raman converter. This converts pressure determined from ruby fluorescence spectroscopy to pressure determined by Raman spectroscopy of the diamnod anvil and vice versa

The tools are written in Python and are implemented within a Jupyter Notebook, which allows users to operate the tools themselves as well as view the underlying code. It also allows the programmer to add interactive widgets and provide explanatory notes. See jupyter.org to find out more about this incredibly useful open source project.

## Getting Started

These instructions will get you a copy of the project up and running on your local machine.

### Installing

[![Binder](http://mybinder.org/badge.svg)](http://mybinder.org:/repo/otlord/xtools)

Xtools requires nothing more that a web browser to run using the MyBinder service (see badge above). This service essentially allows you to build an executable version of any Jupyter Notebook within a specific GitHub repository that can then be accessed via any web browser (though check its status - the service is sometimes unavailable). The result is that your code is immediately available to anyone even if they don't have Python installed on their local machine. Just click the button above and then click on Xtools.ipynb in the resulting browser tab followed by:

```
Cell | Run All
```

Alternatively to install Xtools directly on your local machine, navigate to https://github.com/olivertlord/Xtools and download the .ZIP file and extract it into your chosen directory. Alternatively, if you have git installed, then at the command line type:

```
cd targetdirectory
git clone https://github.com/olivertlord/Xtools.git
```
This will craete a clone of the GitHub repository called ```Xtools``` inside ```targetdirectory```

To run Xtools, simply type the following at the terminal:

```
jupyter notebook Xtools.ipynb
```

This will open a new tab in your browser. To run Xtools, from the menu bar select:

```
Cell | Run All
```

This method assumes that you already have Pyhton 3.0 and the Jupyter notebook package installed. Detailed instructions on how to do both can be found here: http://jupyter.org/install

### Troubleshooting

If you detect any bugs during use, then please contact me (Oliver Lord) at <oliver.lord@bristol.ac.uk>. Suggestions for new features are also welcome.

## Authors

* **Oliver Lord, School of Earth Science, Univeristy of Bristol** - (https://github.com/olivertlord, https://seis.bristol.ac.uk/~glotl/index.html)

## License

This project is licensed under the GNU General Public Licence Version 3 - see the [LICENSE.md](LICENSE.md) file for details

## Acknowledgments

* I (Oliver Lord) would like to acknowledge support from the Royal Society in the form of a University Research Fellowship (UF150057) and the Natural Environment Research Council (NERC) in the form of an Post-doctoral Research Fellowship (NE/J018945/1).
