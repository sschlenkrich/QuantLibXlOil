---
name: check-coverage

description: Check the code coverage of this Python project against the interface specified in the QuantLib SWIG wrappers.
---

Read the [README.md](../../../README.md) file for more information on the QuantLibXlOil project.

Identify the QuantLib-SWIG version from the user prompt and store it in a variable `swig_version`. If the user does not provide a version, use the default value `v1.41`.

Read the QuantLib-SWIG interface specifications from the `QuantLib-SWIG` repository for the specified version. You can find the interface specifications in the `QuantLib-SWIG` repository on GitHub: https://github.com/lballabio/QuantLib-SWIG/tree/`swig_version`/SWIG/

Follow the files which are included via the `%include` directive in the `quantlib.i` file. These files contain the interface specifications for QuantLib.

Consider only interface specifications for Python or for all platforms. The interface specifications for Python are marked with the `#if defined(SWIGPYTHON)` directive in the SWIG interface files.

Read the QuantLibXlOil source code and identify the functions that are exposed to Excel via the `@xlo.func` decorator. These functions are defined in the Python files in the `quantlib_xloil` package.

Compare the functions exposed to Excel in QuantLibXlOil with the interface specifications from QuantLib-SWIG. Identify any functions that are present in the QuantLib-SWIG interface specifications but are not exposed to Excel in QuantLibXlOil.

List the missing functions and their corresponding QuantLib-SWIG interface specifications.

Write a report to the file `docs/source/06_coverage_report.md`. If the file already exists, overwrite it. If the file does not exist, create a new file and write the report to it.
