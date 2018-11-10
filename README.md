component-contribution
======================

Standard reaction Gibbs energy estimation for biochemical reactions.
For more information on the method behind component-contribution, please view our open access paper:

Noor E, Haraldsdóttir HS, Milo R, Fleming RMT (2013)
[Consistent Estimation of Gibbs Energy Using Component Contributions](http://journals.plos.org/ploscompbiol/article?id=10.1371/journal.pcbi.1003098),
PLoS Comput Biol 9:e1003098, DOI: 10.1371/journal.pcbi.1003098

Please, quote this paper if you publish work that uses component-contribution.

## Requirements (for the python version):
* python 3.5+
* (optional) ChemAxon's Marvin >= 5.11
* from PyPI:
  - numpy>=1.14.0
  - scipy>=1.0.0
  - pandas>=0.23.0
  - openbabel>=2.4.0
  - requests>=2.18.0

## Requirements (for the MATLAB version):
* Matlab >= 7
* python == 2.7
* numpy >= 1.14.0
* scipy >= 1.0.0
* pandas >= 0.23.0
* Open-Babel >= 2.3.1 ('babel' must be in PATH, including python bindings)
* ChemAxon's Marvin >= 5.11 ('cxcalc' must be in PATH)

## Installing on Windows
* install Anaconda 5.1 for Windows (recommended python 3.6 version)
* install the openbabel package
  - [conda package](https://anaconda.org/openbabel/openbabel)
* optional: install "Marvin Suite" by ChemAxon
  - Marvin is only required for adding structures of new compounds that are not in the KEGG database
  - [instructions](https://chemaxon.com/products/marvin/download)
  - add `cxcalc.bat` to PATH
  - you will need to get a license to use ChemAxon (it is free for academic use)

## Installing on Ubuntu
* as root: `apt install libopenbabel-dev`
* as root: `pip install -r requirements.txt`
* optional: install "Marvin Suite" by ChemAxon
  - only required for adding structures of new compounds that are not in the KEGG database
  - [instructions](https://chemaxon.com/products/marvin/download)
  - add `cxcalc` to PATH, e.g. using a symbolic link from `/usr/bin/cxcalc`
  - you will need to get a license to use ChemAxon (it is free for academic use)

## Description of files in /data
* compounds.tsv - table of all KEGG compounds, their name and InChI (used only in Matlab code)
* fixed_mapping.tsv - table mapping some KEGG compound IDs to BiGG IDs (overriding the InChI-based mapping)
* formation_energies_transformed.tsv - table of biochemical formation energies (used for training CC)
* kegg_additions.tsv - table of compounds that are missing from KEGG together with their InChI
* kegg_compounds.json.gz - JSON of all KEGG compounds including their InChI and names
* redox.tsv - table of reduction potentials (used for training CC)
* TECRDB.tsv - table of K'eq values from the NIST database (http://xpdb.nist.gov/enzyme_thermodynamics/)
