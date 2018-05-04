MSMExplorer: data visualizations for biomolecular dynamics
==========================================================

[![Build Status](https://travis-ci.org/msmbuilder/msmexplorer.svg?branch=master)](https://travis-ci.org/msmbuilder/msmexplorer)
[![Build status](https://ci.appveyor.com/api/projects/status/038hirce0vlx2847?svg=true)](https://ci.appveyor.com/project/cxhernandez/msmexplorer)
[![Coverage Status](https://coveralls.io/repos/github/msmbuilder/msmexplorer/badge.svg?branch=master)](https://coveralls.io/github/msmbuilder/msmexplorer?branch=master)
[![PyPI version](https://badge.fury.io/py/msmexplorer.svg)](http://badge.fury.io/py/msmexplorer)
[![License](https://img.shields.io/badge/license-MIT-red.svg?style=flat)](https://opensource.org/licenses/MIT)
[![DOI](http://joss.theoj.org/papers/f9485c45a7bfc5cfce6edd8919a07739/status.svg)](http://joss.theoj.org/papers/f9485c45a7bfc5cfce6edd8919a07739)
[![Documentation](https://img.shields.io/badge/docs-latest-blue.svg?style=flat)](http://msmbuilder.org/msmexplorer/)


<div class="row">
  <a href="http://msmbuilder.org/msmexplorer/development/examples/plot_chord.html">
      <img src="http://msmbuilder.org/msmexplorer/development/_static/plot_chord_thumb.png" height="135" width="135">
  </a>
  <a href="http://msmbuilder.org/msmexplorer/development/examples/plot_free_energy_2d.html">
      <img src="http://msmbuilder.org/msmexplorer/development/_static/plot_free_energy_2d_thumb.png" height="135" width="135">
  </a>
  <a href="http://msmbuilder.org/msmexplorer/development/examples/plot_histogram.html">
      <img src="http://msmbuilder.org/msmexplorer/development/_static/plot_histogram_thumb.png" height="135" width="135">
  </a>
  <a href="http://msmbuilder.org/msmexplorer/development/examples/plot_stackdist.html">
      <img src="http://msmbuilder.org/msmexplorer/development/_static/plot_stackdist_thumb.png" height="135" width="135">
  </a>
  <a href="http://msmbuilder.org/msmexplorer/development/examples/plot_trace.html">
      <img src="http://msmbuilder.org/msmexplorer/development/_static/plot_trace_thumb.png" height="135" width="135">
  </a>
  <a href="http://msmbuilder.org/msmexplorer/development/examples/plot_voronoi.html">
      <img src="http://msmbuilder.org/msmexplorer/development/_static/plot_voronoi_thumb.png" height="135" width="135">
  </a>
</div>

MSMExplorer is a Python visualization library for statistical models of
biomolecular dynamics. It provides a high-level interface for drawing
attractive statistical graphics with [MSMBuilder](http://msmbuilder.org).


Documentation
-------------

Online documentation is available [here](http://msmbuilder.org/msmexplorer/). It includes IPython notebooks, detailed API documentation, and other useful info.

There are docs for the development version [here](http://msmbuilder.org/msmexplorer/development). These should correspond with the github master branch.

Examples
--------

```python
from msmbuilder.example_datasets import FsPeptide
from msmbuilder.featurizer import RMSDFeaturizer

import msmexplorer as msme

# Load Fs Peptide Data
traj = FsPeptide().get().trajectories[0]

# Calculate RMSD
featurizer = RMSDFeaturizer(reference_traj=traj[0])
rmsd = featurizer.partial_transform(traj).flatten()

# Plot Trace
msme.plot_trace(rmsd, label='traj0', xlabel='Timestep', ylabel='RMSD (nm)')
```

![](http://msmbuilder.org/msmexplorer/development/_images/plot_trace.png)

The documentation has an [example gallery](http://msmbuilder.org/msmexplorer/development/examples/) with short scripts showing how to use different parts of the package.


Dependencies
------------

- Python 3.4+

### Mandatory

The latest versions of the following packages are required:

-  [numpy](http://www.numpy.org/)

-  [scipy](http://www.scipy.org/)

-  [matplotlib](matplotlib.sourceforge.net)

-  [networkx](https://networkx.github.io/)

-  [pandas](http://pandas.pydata.org/)

-  [seaborn](https://stanford.edu/~mwaskom/software/seaborn/)

-  [statsmodels](http://statsmodels.sourceforge.net/devel/)

-  [corner](http://corner.readthedocs.io/en/latest/)

-  [mdtraj](https://mdtraj.org/)

-  [msmbuilder](https://msmbuilder.org)


Installation
------------

The preferred installation mechanism for `msmexplorer` is with `conda`:

```bash
$ conda install -c omnia msmexplorer
```

If you don't have conda, or are new to scientific python, we recommend that
you download the [Anaconda scientific python distribution](https://store.continuum.io/cshop/anaconda/).

To install from PyPI, just do:

    pip install msmexplorer

You may instead want to use the development version from Github, by running

    pip install git+git://github.com/msmexplorer/msmexplorer.git#egg=msmexplorer


Development
-----------

All development happens here, on
[Github](https://github.com/msmexplorer/msmexplorer).

If you're interested in contributing to MSMExplorer, please refer to our
[Contributing](http://msmbuilder.org/msmexplorer/development/contributing.html)
guide.

Support
-------

Please [submit](https://github.com/msmexplorer/msmexplorer/issues/new) any bugs
or questions to the Github issue tracker.

License
-------

Released under a MIT license


Citing
------

```bibtex
@article{msmexplorer,
  doi = {10.21105/joss.00188},
  url = {https://doi.org/10.21105%2Fjoss.00188},
  year  = {2017},
  month = {apr},
  publisher = {The Open Journal},
  volume = {2},
  number = {12},
  author = {Carlos X. Hern{\'{a}}ndez and Matthew P. Harrigan and Mohammad M. Sultan and Vijay S. Pande},
  title = {{MSMExplorer}: Data Visualizations for Biomolecular Dynamics},
  journal = {The Journal of Open Source Software}
}
```
