Getting started
===============

Installing SciencePlots
-----------------------
The easiest way to install SciencePlots is by using ``pip``:

.. code-block:: bash

    # to install the lastest release (from PyPI)
    py -m pip install SciencePlots

    # to install the latest commit (from GitHub)
    py -m pip install git+https://github.com/garrettj403/SciencePlots

    # to clone and install from a local copy
    git clone https://github.com/garrettj403/SciencePlots.git
    cd SciencePlots
    py -m pip install -e .

.. warning:: 
    SciencePlots requires Latex (see :ref:`guides/faq:Installing Latex`). 

.. deprecated::
    CJK fonts were deprecated, in favor of other packages that support and
    maintain them. E.g. :mplfonts:``.

Using the Styles
----------------

``"science"`` is the primary style in this repo. Whenever you want to use it,
simply add the following to the top of your python script:

.. code-block:: python

    import matplotlib.pyplot as plt
    import scienceplots

    plt.style.use('science')

You can also combine multiple styles together by:

.. code-block:: python

    plt.style.use(['science','ieee'])

In this case, the ``ieee`` style will override some of the parameters from the
``science`` style in order to configure the plot for IEEE papers (column width,
fontsizes, etc.).

To use any of the styles temporarily, you can use:

.. code-block:: python

    with plt.style.context('science'):
        plt.figure()
        plt.plot(x, y)
        plt.show()

.. danger::
    It has been reported that `plt.style.context()` has issues with LaTeX
    preambles, so it's better to stick to `plt.style.use()`.
    See :ghmatplotlibissue:`17931`.
