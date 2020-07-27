FAQ
=======================

Installation
-------------

Error: ``ModuleNotFoundError: No module named 'numpy'``
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Some versions of several packages that WORC uses, such as PyWavelets and
PyRadiomics, require numpy during their installation. To solve this issue,
simply first install numpy before installing WORC or any of the dependencies
, i.e. ``pip install numpy`` or ``conda install numpy`` when using Anaconda.

Execution
-------------

My experiment crashed, where to begin looking for errors?
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
The ``fastr`` toolbox has a method to trace back errors. For more details,
see the `fastr documentation <https://fastr.readthedocs.io/en/stable/static/user_manual.html#debugging-a-network-run-with-errors/>`_.


Error: ``WORC.addexceptions.WORCValueError: First column in the file`` ``given to SimpleWORC().labels_from_this_file(**) needs to be named Patient.``
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
This means that your label file, i.e. in which the label to be predicted for
each patient is given, is not formatted correctly. Please see the
:ref:`Configuration chapter <config-chapter>`, or the WORC Tutorial Github
for an `example <https://github.com/MStarmans91/WORCTutorial/blob/master/Data/Examplefiles/pinfo_HN.csv/>`_.

Error: ``WORC.addexceptions.WORCKeyError: 'No entry found in labeling`` ``for feature file .../feat_out_0.hdf5.'``
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
This means for this specific file (../feat_out_0.hdf5), WORC could not
find a label in your label file. Please make sure that one of the Patient IDs
from your label file occurs in the filename of your inputs. For example,
when using the example label file from the `WORC tutorial <https://github.com/MStarmans91/WORCTutorial/blob/master/Data/Examplefiles/pinfo_HN.csv/>`_,
if your Patient ID is not listed in column 1, this error will occur.