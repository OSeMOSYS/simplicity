# OSeMOSYS Example Model: Simplicity

[![DOI](https://zenodo.org/badge/214192147.svg)](https://zenodo.org/badge/latestdoi/214192147)
[![goodtables.io](https://goodtables.io/badge/github/OSeMOSYS/simplicity.svg)](https://goodtables.io/github/OSeMOSYS/simplicity)

This is an example OSeMOSYS model published as a Frictionless Data [Tabular Data Package](https://frictionlessdata.io/specs/tabular-data-package/).

The Data Package was constructed with the help of the Python **otoole** package available on [PyPI](https://pypi.org/project/otoole/) and [Github](https://github.com/OSeMOSYS/otoole).

You can use `v0.2` onwards of **otoole** to generate a GNU MathProg data file from the dataset with the following commands and then run OSeMOSYS

```bash
# Install the OSeMOSYS toolkit
pip install otoole
# Download the dataset and build a GNU MathProg datafile
otoole prep datafile https://zenodo.org/record/3479823/files/OSeMOSYS/simplicity-v0.1a0.zip ./simplicity.txt
# Solve the model
glpsol -m OSeMOSYS.txt -d simplicity.txt
```