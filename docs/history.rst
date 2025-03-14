===============
Version History
===============

*Note:* SNCosmo uses `Semantic Versioning <http://semver.org>`_ for
its version numbers. Specifically, this means that code written for
sncosmo v1.0 will continue to work with any v1.x version. However,
exact results may differ between versions in the 1.x series. (For
example, due to changes in integration method.)

v2.12.0 (2025-01-21)
====================

Major Changes & Additions:

- Add support for Numpy 2.0 (#398)

- Add non-radially varability to bandpasses (#400)

- Adds hdf5 dependancy (#400)

Minor Changes:

- Improve testing (#402)

v2.11.2 (2024-11-01)
====================

- Add SkyMapper filters

v2.11.1 (2024-07-11)
====================

- Add Nugent Type Ia Super-Chandra model from Fitz Axen and Nugent, (2023) ApJ, v. 953, p. 13

v2.11.0 (2024-07-11)
====================

- Drop support for Python 3.8
- New `add_effect` for G10 and C11 SNIa intrinsic scatter models (#378)
- Salt2 ColorLaw function correction (#389)


v2.10.4 (2024-02-20)
====================

- Fix issue with Python 3.12. Added dependency, `looseversion`, to replace removed `distutil` module (#387).

v2.10.3 (unreleased)
====================

v2.10.2 (2023-09-29)
====================

- Add ultrasat_ bandpasses (#381).

.._ultrasat: https://www.weizmann.ac.il/ultrasat/

v2.10.1 (2023-06-28)
====================

- Add GOTO_ (#374) and `DES u`_ (#371) filters.

.. _GOTO: https://goto-observatory.org/
.. _DES u: https://noirlab.edu/science/programs/ctio/filters/Dark-Energy-Camera

v2.10.0 (2023-04-27)
====================

Major Changes:

- Dropped support for Python <3.7 (#361)

- Add phase dependence option to PropagationEffect (#359)

Additions & Improvements:

- Add retrained SALT2 models from the DES and Pantheon+ teams (#355)
  
- Add TESS filter (#357)

v2.9.0 (2022-09-27)
===================

- Add P22 SALT3-NIR model (#350)

- Updated SALT3 input calibration (#339)

- Add Gaia filters (#351)

- Improvements to code management

v2.8.0 (2022-03-16)
===================

- Add 2MASS filters (#338)

- Add ATLAS filters (#336)

v2.7.0 (2021-10-29)
===================

- New zeropoint alias for improved SNANA compatibility (#318)

- Add Roman filters (#218, #322)

- Add the ability to a use SNANA co-add simlibs (#247)

- Fix file paths for Windows users (#324)

- Fix the builtins with poor spline options (#203, #328, #329)

- Various improvements to code and repo management

v2.6.0 (2021-09-09)
===================

This release mostly involves modernizing the SNCosmo build system.

- Add Pan-STARRS1 bandpasses (#212)

- Added support for wheels which should now be automatically uploaded to PyPI
  for any new release (#304).

- Fixed the Zenodo integration. New SNCosmo releases should now automatically
  be archived to Zenodo.

- Moved citations to the new CITATION.cff format. GitHub and Zenodo will now
  provide BibTeX entries that can be used to cite SNCosmo (#302).

- Update to the emcee version 3 API. Now only compatible with emcee>=3.

- Migrate from Travis CI to GitHub Actions for continuous integration/tests
  (#293).

- Bugfixes:

  - Fixed the implementation of the SALT3 error model (#300).

  - Fixed numpy type deprecations.

  - Fixed the documentation for models (#299).


v2.5.0 (2021-04-20)
===================

- Add SALT3 model from Kenworthy et al. (2021)

- Various documentation fixes

v2.4.0 (2021-03-05)
===================

- Add SUGAR model from Leget et al. (2020)

- Add support for the iminuit 2.0 API (#291).

- Update tox to work with any version of Python 3.

- Bugfixes:

  - Fix flatten_result bug due to API change (#285).

v2.3.0 (2020-11-16)
===================

- Add Swift UVOT bandpasses.

- Bugfixes:

  - Fix segfaults in bicubic interpolation.

v2.2.0 (2020-10-23)
===================

- Add core-collapse models from Vincenzi et al. (2019)

- New Spectrum class to handle processing and fitting spectral observations.

- Removed appveyor builds.

- Bugfixes:

  - Prevent segfaults in light curve fitting when the minuit fit fails.

v2.1.0 (2020-02-25)
===================

- Add ZTF transmission functions

- Bugfixes

  - Corrected pyproject.toml; should help cases where the wrong numpy
    version was being installed.

  - Remove all references to the six package

  - Fix accidental mutation of ``bounds`` inputs in ``fit_lc`` and
    ``mcmc_lc``.

v2.0.0 (2019-06-08)
===================

This version is the same as v1.8, with the exception that Python 2 support
has been removed, and deprecated functions and attributes have been removed.
These were deprecated in v1.5.0 (released April 2017) or before.

On Python 2, pip should automatically install sncosmo v1.8 still. If not,
specify ``sncosmo<2.0.0``.

Minor changes:

- The ``salt2-h17`` source model has been renamed to ``salt2-extended-h17``
  to make clearer its relation to ``salt2-extended``. It is still available
  under the old name for backwards compatibility.

v1.8.2 (2019-06-08)
===================

- Fix bug in download location of ``snana-*`` models latest versions,
  introduced in v1.8.0.

v1.8.1 (2019-06-08)
===================

- Fix bug in download location of ``salt2-extended`` model latest version,
  introduced in v1.8.0.

v1.8.0 (2019-05-25)
===================

- Add version 2.0 of many ``snana-...`` built-in core-collapse models,
  based on Pierel et al. 2018 (pull request 229).

- Bugfixes:

  - Fix compatibility with scipy 1.3+ by removing outdated import statements
    (pull request 238).

  - Fix issue affecting optimization of models with free propagation effects
    (pull request 236).

v1.7.0 (2019-02-02)
===================

- Add SNEMO2, SNEMO7, SNEMO15 source models from Saunders et al. (2018)
  to built-ins.


v1.6.0 (2018-04-27)
===================

- Add Hounsell et al. (2017) SALT2 model to built-ins.

- Add ``remote_timeout`` configuration option.
  
- Build system: remove build-time dependency on astropy helpers.

- Bugfixes:

  - Correctly delete empty files created when a download fails.

  - Use pseudo-inverse when inverting covariance matrix for increased stability.

  - Fix an issue with pickling on Cython 0.26+.

  - Fixed problem where ``data['fluxcov']`` was unintentionally being modified
    in-place when passed to ``fit_lc``.

  - Fixed problem where ``'fluxcov'`` not recognized as a valid name for
    covariance column in data in ``fit_lc``.


v1.5.0 (2017-04-20)
===================

This is a major new release. The highlight is really close compatibility of
the SALT2 model and fitting procedure with ``snfit``, the "official" SALT2
fitter.

- ``SALT2Source``: Internal interpolation scheme of ``SALT2Source``
  updated to match ``snfit`` implementation exactly. Test suite now tests
  against ``snfit`` implementation.

- ``fit_lc()``:

  - Handling of model covariance updated to match that of ``snfit``: model
    covariance is fixed for each fit and fit is repeated until convergence.
    
  - New arguments ``phase_range`` and ``wave_range``. If given,
    data outside this range will be discarded after an initial fit and
    additional fits will be performed until convergence.
    With ``phase_range=(-15., 45.)`` and ``wave_range=(3000., 7000.)``,
    behavior approximates that of snfit with default arguments.

  - Added support for covariance in photometric data measurements, and
    this covariance is used in ``fit_lc()`` if present. Covariance
    is stored as a ``'fluxcov'`` column in the table of measurements.

  - Result includes two new attributes: ``data_mask``, a boolean array
    indicating which rows in the input data were used in the final fit
    (since multiple fits might be performed), and ``nfit``, the number
    of fits performed.

  - New argument ``warn`` can be set to False to turn off warnings about
    dropping bands outside model wavelength range.

- ``read_lc()``:

  - Added support for reading snfit-format "covmat" files into
    a table of photometry::

      >>> data = read_lc('filename', format='salt2', read_covmat=True)
      >>> data['Fluxcov'].shape == (len(data), len(data))
      True

  - New keyword argument ``expand_bands``. When True, the returned band
    column will contain ``Bandpass`` objects instead of strings. (Strings
    converted to bandpass objects using ``sncosmo.get_bandpass()``.) This
    is particularly useful for position-dependent bandpasses in the salt2
    file format, such as ``megacampsf``: ``read_lc()`` reads the position from
    the header and feeds the position to ``get_bandpass()`` to get a Bandpass
    object for the correct position.

- Built-in bandpasses and magnitude systems: Many new built-in bandpasses
  and magnitude systems.

- Configuration: The environment variable ``SNCOSMO_DATA_DIR`` can be
  used to set the path to the data directory. If set, it takes
  precedence over the ``data_dir`` variable in the configuration file
  (``$HOME/.astropy/config/sncosmo.cfg``).


v1.4.0 (2016-11-16)
===================

- ``SFD98Map`` and ``get_ebv_from_map`` deprecated in favor of separate package
  `sfdmap <http://github.com/kbarbary/sfdmap>`_ which has vastly improved
  performance (200x faster) for the typical case of scalar coordinates in
  ICRS frame.

- ``animate_source()`` deprecated. This is a "fun extra" that is difficult
  to test and no longer seems to work.

- Cython implementation of extinction functions has been factored out into
  a separate Python module called ``extinction``, which is now a dependency.

- ``Model.bandflux()`` and ``Source.bandflux()`` now integrate on a
  fixed wavelength grid of 5 angstroms regardless of the wavelength
  grid of the bandpass. This will result in small differences in
  results from previous sncosmo versions.

- The internal (publicly undocumented) ``Spectrum`` class now acts
  more like ``Model``; in particular, its ``bandflux()`` method now
  behaves the same way.  As ``Spectrum`` backs ``SpectralMagSystem``,
  this makes the integration of models and zeropoint spectra more
  consistent.

- Experimental (non-public) support for aliases for bandpasses,
  such as ``'SDSS::g'`` for ``'sdssg'``.

- Sources now use cubic rather than quadratic spline interpolation internally.
  
- ``Model.source_peakmag()`` and ``Model.set_source_peakmag()`` added
  as convenience functions for ``Model.source.peakmag()`` and
  ``Model.source.set_peakmag()`` respectively.

- **[Bugfix]** Fixed missing import of ``math`` module in ``mcmc_lc()``
  when using the ``priors`` keyword. [Backported to v1.3.1]
  [`#143 <https://github.com/sncosmo/sncosmo/issues/143>`_]


v1.3.0 (2016-06-30)
===================

This is mostly a bugfix release, but it also **drops support for Python 2.6.**
Python 2.7 is now the minimum supported Python version.

- Updates for compatibility with AstroPy 1.2.

- The registry now handles subclasses more robustly. For example,
  if ``magsys`` is an instance of ``SpectralMagSystem``, the following
  used to fail::

      sncosmo.register(magsys, 'name')
      sncosmo.get_magsystem('name')

  Now this works.  [`#132 <https://github.com/sncosmo/sncosmo/issues/132>`_]

- **[Bugfix]** ``SALT2Source`` had a bug under Python 3 (only)
  yielding drastically wrong fluxes. Python 2 was not affected. [`#138
  <https://github.com/sncosmo/sncosmo/issues/138>`_]

v1.2.0 (2015-12-01)
===================

- **[API change]** Registry functions moved to the top-level namespace, as
  follows:

  - ``sncosmo.registry.register()`` -> ``sncosmo.register()``
  - ``sncosmo.registry.register_loader()`` -> ``sncosmo.register_loader()``
  - ``sncosmo.registry.retrieve()`` -> deprecated, use class-specific
    functions such as ``sncosmo.get_bandpass()``.

  The old import paths will still work for backwards compatibility.

- ``nest_lc()`` now uses the ``nestle`` module under the hood. A new
  keyword ``method`` is available which selects different sampling
  methods implemented by ``nestle``. The new methods provide potential
  efficiency gains.

- The MLCS2k2 model is now available as a built-in Source, with the
  name ``'mlcs2k2'``.

- Bandpasses from the Carnegie Supernova Project added to built-ins.

- In ``realize_lcs()``, a new ``scatter`` keyword makes adding noise
  optional.

- **[Bugfix]** Fix built-in Bessell bandpass definitions, which were
  wrong by a term proportional to inverse wavelength. This was due to
  misinterpretation of the trasmission units. [backported to v1.1.1]
  [`#111 <https://github.com/sncosmo/sncosmo/issues/111>`_]


v1.1.0 (2015-08-12)
===================

This is a mostly bugfix release with more solid support for Python 3.

- Added ``Model.color()`` method.
  
- Remove ``loglmax`` from result of ``nest_lc()``, which was not
  officially documented or supported. Use ``np.max(res.logl)`` instead.

- Fixed bug that caused non-reproducible behavior in
  ``nest_lc()`` even when ``numpy.random.seed()`` was called
  directly beforehand.
  [`#102 <https://github.com/sncosmo/sncosmo/issues/102>`_]

- Fixed file I/O problems on Python 3 related to string encoding.
  [`#83 <https://github.com/sncosmo/sncosmo/issues/83>`_,
  `#85 <https://github.com/sncosmo/sncosmo/issues/85>`_]

- Fixed problem with SDSS bandpasses being stored as integers internally,
  preventing them from being used with models with dust.
  [`#100 <https://github.com/sncosmo/sncosmo/issues/100>`_,
  `#101 <https://github.com/sncosmo/sncosmo/issues/101>`_]

- Fixed problem where built-in source name and version strings were being
  dropped. [`#82 <https://github.com/sncosmo/sncosmo/issues/82>`_]

- Minor doc fixes.



v1.0.0 (2015-02-23)
===================

- **[API change]** The API of ``mcmc_lc`` has changed significantly
    (the function was marked experimental in previous release).

- **[Deprecation]** In result of ``fit_lc``, ``res.cov_names`` changed to
  ``res.vparam_names``.

- **[Deprecation]** In result of ``nest_lc``, ``res.param_names``
  changed to ``res.vparam_names``. This is for compatibility between
  the results of ``fit_lc`` and ``nest_lc``.
  [`#30 <https://github.com/sncosmo/sncosmo/issues/30>`_]

- **[Deprecation]** Deprecate ``flatten`` keyword argument in
  ``fit_lc()`` in favor of explicit use of ``flatten_result()``
  function.

- Many new built-in models.

- Many new built-in bandpasses.

- New remote data fetching system.

- SALT2 model covariance available via ``Model.bandfluxcov()`` method and
  ``modelcov=True`` keyword argument passed to ``fit_lc``.

- New simulation function, ``zdist``, generates a distribution of redshifts
  given a volumetric rate function and cosmology.

- New simulation function, ``realize_lcs``, simulates light curve data given a
  model, parameters, and observations.

- Add color-related keyword arguments to ``plot_lc()``.

- Add ``tighten_ylim`` keyword argument to ``plot_lc()``.

- Add ``chisq()`` function and use internally in ``fit_lc()``.

- Add ``SFD98Map`` class for dealing with SFD (1998) dust maps persistently so
  that the underlying FITS files are opened only once. 

- Update ``get_ebv_from_map()`` to work with new SkyCoord class in
  ``astropy.coordinates`` available in astropy v0.3 onward. Previously, this
  function did not work with astropy v0.4.x (where older coordinates classes
  had been removed).

- Update to new configuration system available in astropy v0.4 onward.
  This makes this release incompatible with astropy versions less than
  0.4.

- Now compatible with Python 3.

- Increased test coverage.

- Numerous minor bugfixes.


v0.4.0 (2014-03-26)
===================

This is non-backwards-compatible release, due to changes in the way
models are defined. These changes were made after feedback on the initial
design.

The most major change is a new central class ``Model`` used throughout
the pacakge. A ``Model`` instance encompasses a ``Source`` and zero or
more ``PropagationEffect`` instances. This is so that different
source models (e.g., SALT2 or spectral time series models) can be
combined with arbitrary dust models. The best way to think about this
is ``Source`` and ``PropagationEffect`` define the rest-frame behavior
of a SN and dust, and a ``Model`` puts these together to determine the
observer-frame behavior.

- New classes:

  - ``sncosmo.Model``: new main container class
  - ``sncosmo.Source``: replaces existing ``Model``
  - ``sncosmo.TimeSeriesSource``: replaces existing ``TimeSeriesModel``
  - ``sncosmo.StretchSource``: replaces existing ``StretchModel``
  - ``sncosmo.SALT2Source``: replaces existing ``SALT2Model``
  - ``sncosmo.PropagationEffect``
  - ``sncosmo.CCM89Dust``
  - ``sncosmo.OD94Dust``
  - ``sncosmo.F99Dust``

- New public functions:

  - ``sncosmo.read_griddata_ascii``: Read file with ``phase wave flux`` rows
  - ``sncosmo.read_griddata_fits``
  - ``sncosmo.write_griddata_fits``
  - ``sncosmo.nest_lc``: Nested sampling parameter estimation of SN model
  - ``sncosmo.simulate_vol`` (EXPERIMENTAL): simulation convenience function.

- Built-ins:

  - updated SALT2 model URLs
  - added SALT2 version 2.4 (Betoule et al 2014)

- Improvements to ``sncosmo.plot_lc``: flexibility and layout

- Many bugfixes


v0.3.0 (2013-11-07)
===================

This is a release with mostly bugfixes but a few new features,
designed to be backwards compatible with v0.2.0 ahead of API changes
coming in the next version.

- New Functions:

  - ``sncosmo.get_ebv_from_map``: E(B-V) at given coordinates from SFD map. 
  - ``sncosmo.read_snana_ascii``: Read SNANA ascii format files.
  - ``sncosmo.read_snana_fits``: Read SNANA FITS format files.
  - ``sncosmo.read_snana_simlib``: Read SNANA ascii "SIMLIB" files.

- registry is now case-independent. All of the following now work::

      sncosmo.get_magsystem('AB')
      sncosmo.get_magsystem('Ab')
      sncsomo.get_magsystem('ab')

- Photometric data can be unordered in time. Internally, the data are
  sorted before being used in fitting and typing.

- Numerous bugfixes.


v0.2.0 (2013-08-20)
===================

- Added SN 2011fe Nearby Supernova Factory data to built-in models as
  ``'2011fe'``

- Previously "experimental" functions now included:

  - ``sncosmo.fit_lc`` (previously ``sncosmo.fit_model``)
  - ``sncosmo.read_lc`` (previously ``sncosmo.readlc``)
  - ``sncosmo.write_lc`` (previously ``sncosmo.writelc``)
  - ``sncosmo.plot_lc`` (previously ``sncosmo.plotlc``)

- New functions:

  - ``sncosmo.load_example_data``: Example photometric data.
  - ``sncosmo.mcmc_lc``: Markov Chain Monte Carlo parameter estimation.
  - ``sncosmo.animate_model``: Model animation using matplotlib.animation.

- Fitting: ``sncosmo.fit_lc`` now uses the iminuit package for
  minimization by default. This requires the iminuit package to be
  installed, but the old minimizer (from scipy) can still be used by
  setting the keyword ``method='l-bfgs-b'``.

- Plotting: Ability to plot model synthetic photometry
  without observed data, using the syntax::

      >>> sncosmo.plot_lc(model=model, bands=['band1', 'band2'])

- Photometric data format: Photometric data format is now more
  flexible, allowing various names for table columns.

v0.1.0 (2013-07-15)
===================

Initial release.
