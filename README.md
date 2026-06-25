# **StarGal**

## Presentation

Wrap up of star-galaxy separation algorithms. Source-type classification is crucial for cosmology: misclassified sources can act as noise and severely disrupt statistics. In the context of large photometric surveys, we want to maximise the efficiency of the classifiers to obtain the purest sample of stars or galaxies possible. Several methods have emerged in the context of photometric classification, each being more relevant than another in particular use cases: computation speed, completeness, low SNR... etc. It is therefore important to identify which classifier is the most efficient for a given application and to provide easy access to it within a common framework.

This repository is a wrap-up of photometric classifiers in the LSST era. It contains different methods to perform star-galaxy separation, each of them working separately, with code and/or data related to these methods stored in separate folders. The folders named respectively after the methods do not contains the core code of it, but rather the tools to work with the outputs. The methods used are as follows:
 - **locus**: Tools using the *color* property of stars and galaxies to position them on particular loci in color-magnitude and color-color diagrams.
 - **morpho**: Classification using *morphological* parameters such as extendedness or elliptic moments, which are available in the object tables.
 - **margnet**: *Neural network* algorithm that takes any parameters in the photometry catalog, as well as cutouts, to compute source-type probabilities.
 - **split**: Uses results from *template fitting* algorithms to attribute source types by comparing models. It can either run the fitting algorithm or take a table with fitting parameters as input. It uses either direct best-model comparison or reduced Bayesian posterior probability distribution metrics to compute the type.

This repository also contains:
 - **catsorter**: Tools to classify sources from photometry, using magnitudes, errors, and flags, in order to improve computational efficiency of classifiers.
 - **data**: Where to store the datasets for the tests or results.
 - **metrics**: Tools to compute efficiency metrics of classifiers.
 - **utils**: Utilities for data manipulation, computation, and plotting.
 - **work**: Main running scripts and notebooks.

## Input / Output

Each method takes photometric catalogs as input and outputs source-type probabilities or labels. Depending on the method used, it needs additional inputs in the catalogs.

## Installation

```
mamba env create -f environment.yml
conda activate stargal
```

or
```
python3.13 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
```

## Quick start

Example scripts can be found in the `work/` directory.

## Repository structure

StarGal/
├── data/
├── locus/
├── margnet/
├── morpho/
├── split/
├── metrics/
├── photosorter/
├── utils/
└── work/

## License

GPL-3.0 License