# OSeMOSYS Example Model: Simplicity

[![DOI](https://zenodo.org/badge/214192147.svg)](https://zenodo.org/badge/latestdoi/214192147)

This is an example OSeMOSYS model used to demonstrate the functionality of the Python
package [otoole](https://github.com/OSeMOSYS/otoole). You can use **otoole** to generate
a GNU MathProg data file from the dataset with the following commands. Full
**otoole** documentation (including installation and examples) can be found on
its [ReadTheDocs site](https://otoole.readthedocs.io/en/latest/).

**NOTE**: To be able to solve the model in this example, you will need to install
the free and open-source solver [GLPK](https://www.gnu.org/software/glpk/)

```bash
# Install the OSeMOSYS toolkit
pip install otoole>=1.0.0

# Download the dataset. On Linux or OSX use wget, otherwise download and unzip
wget https://zenodo.org/record/7736670/files/OSeMOSYS/simplicity-v1.0.zip?download=1

unzip simplicity-v1.0 -d simplicity

# Create the GNUMathProg data file with otoole
mv simplicity/OSeMOSYS-simplicity-f0d3e83/* simplicity
otoole convert csv datafile simplicity/data ./simplicity.txt simplicity/config.yaml

# Solve the model
glpsol -m OSeMOSYS.txt -d simplicity.txt
```
