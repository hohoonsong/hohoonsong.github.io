# hohoonsong.github.io

```
# generate docs
sphinx-quickstart docs

# edit docs theme (conf.py)
extensions = ['sphinx.ext.autodoc']
html_theme = 'sphinx_rtd_theme'

# add package root (conf.py)
import os
import sys
sys.path.insert(0, os.path.abspath('../../src/packages'))

# generate rst file
sphinx-apidoc -f -o docs/source/ src/packages

# add modules (docs/source/index.rst)
==========================
    ...
.. toctree::
   :maxdepth: 2
   :caption: Contents:

   modules
   ...
==========================

# generate docs
cd docs
make html

# copy builds to docs
cp -R docs/build/html docs/
```
