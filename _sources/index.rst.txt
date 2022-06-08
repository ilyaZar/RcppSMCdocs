.. C++ Sphinx Doxygen Breathe documentation master file, created by
   sphinx-quickstart on Wed Jun  8 17:22:47 2022.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

Welcome to the RcppSMC documentation!
======================================================

Sequential Monte Carlo methods are a very general class of Monte Carlo methods for sampling
from sequences of distributions. Simple examples of these algorithms (often termed particle filters)
are used very widely in the tracking and signal processing literature. Recent developments illustrate
that these techniques have much more general applicability, and can be applied very effectively to
statistical inference problems. Unfortunately, these methods are often perceived as being computationally
expensive and difficult to implement. This library seeks to address both of these problems.

A C++ template class library for the efficient and convenient implementation of very general
Sequential Monte Carlo algorithms (or general particle interpretations of Feynman-Kac formulae) is embedded
inside R. Various examples illustrate the flexibility of algorithms that can be implemented this way.

This software is released under  `version 3 of the GNU General Public License <http://www.gnu.org/licenses/gpl-3.0.html>`_ .
Please be aware that this software is still in development, although all known bugs have been eliminated 
it is possible that some persist, see the `project development sources on Github for the most recent version <https://github.com/rcppsmc/rcppsmc>`_. 

If you wish to be added to a mailing list to receive information about
updates to this software, then please send an email to the author, a.m.johansen@warwick.ac.uk. 
Otherwise, please check this page regularly for updates.


.. toctree::
   :maxdepth: 2
   :caption: Contents:


Indices and tables
==================

* :ref:`genindex`
* :ref:`modindex`
* :ref:`search`

Table of Contents
^^^^^^^^^^^^^^^^^

 .. toctree::
    :maxdepth: 2

    self
    api/index
