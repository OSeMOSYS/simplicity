# OSeMOSYS Example Model: Simplicity

[![DOI](https://zenodo.org/badge/214192147.svg)](https://zenodo.org/badge/latestdoi/214192147)
[![goodtables.io](https://goodtables.io/badge/github/OSeMOSYS/simplicity.svg)](https://goodtables.io/github/OSeMOSYS/simplicity)

This is an example OSeMOSYS model published as a Frictionless Data [Tabular Data Package](https://frictionlessdata.io/specs/tabular-data-package/).

The Data Package was constructed with the help of the Python **otoole** package available on [PyPI](https://pypi.org/project/otoole/) and [Github](https://github.com/OSeMOSYS/otoole).

Simplicity `v0.2` requires `v0.5.4` or later of **otoole**.
You can use **otoole** to generate a GNU MathProg data file from the dataset with the following commands and then run OSeMOSYS.

Simplicity also requires a specific version of [OSeMOSYS](https://github.com/OSeMOSYS/OSeMOSYS_GNU_MathProg/blob/1567dbe2d341841c97e6fdb9fa130bd22d66fe83/src/osemosys.txt) that you can obtain via:
```
cd OSeMOSYS_GNU_MathProg
git checkout 1567dbe2d
```

```bash
# Install the OSeMOSYS toolkit
pip install otoole>=0.5.4
# Download the dataset and build a GNU MathProg datafile
otoole convert datapackage datafile https://github.com/OSeMOSYS/simplicity ./simplicity.txt
# Solve the model (slow version)
glpsol -m OSeMOSYS.txt -d simplicity.txt
# Solve the model (fast version)
glpsol -m OSeMOSYS_short.txt -d simplicity.txt
```
