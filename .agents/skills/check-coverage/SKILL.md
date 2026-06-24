---
name: check-coverage

description: Check the code coverage of this Python project against the interface specified in the QuantLib SWIG wrappers.
---

Read the [README.md](../../../README.md) file for more information on the QuantLibXlOil project.

Identify the QuantLib-SWIG version from the user prompt and store it in a variable `swig_version`. If the user does not provide a version, use the default value `v1.41`.

Read the QuantLib-SWIG interface specifications from the `QuantLib-SWIG` repository for the specified version. You can find the interface specifications in the `QuantLib-SWIG` repository on GitHub: https://github.com/lballabio/QuantLib-SWIG/tree/`swig_version`/SWIG/

The interface specification is defined in the `*.i` files in the `SWIG` directory. The main interface file is `quantlib.i`, which includes other interface files via the `%include` directive.

Consider only interface specifications for Python or for all platforms. The interface specifications for Python are marked with the `#if defined(SWIGPYTHON)` directive in the SWIG interface files.

Iterate through the interface specifications and extract the module name, class names and function names and their corresponding QuantLib-SWIG interface specifications. Store the module name, class names, function names and their corresponding interface specifications in a list.

Read the QuantLibXlOil source code in the folder `quantlib_xloil`. Identify the functions that are exposed to Excel via the `@xlo.func` decorator.

Compare the functions from the QuantLib-SWIG interface specifications with the functions exposed to Excel in QuantLibXlOil. For each function in the QuantLib-SWIG interface specifications, check if it is present in the list of functions exposed to Excel in QuantLibXlOil. If a function is not present in the list of functions exposed to Excel, add it to a list of missing functions.

Write a coverage report to the file `docs/source/06_coverage_report.md`. If the file already exists, overwrite it. If the file does not exist, create a new file and write the coverage report to it.

The coverage report should include the following information:
- The QuantLib-SWIG version used for the comparison.
- The date of the comparison.
- A table listing the classes and functions in the QuantLib-SWIG interface specifications along with their corresponding functions exposed to Excel in QuantLibXlOil. The table should have the following columns: Module name,  Class Name, Function Name, QuantLibXlOil Function Name, and Status (Present or Missing).
