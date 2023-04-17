doxygen-lisp-filter

A Doxygen input filter for Lisp code.

Overview

doxygen-lisp-filter is a library that provides a Doxygen input filter for Lisp code. Doxygen is a popular documentation tool for C++ and other languages, but it doesn't support Lisp out of the box. This library solves that problem by allowing you to document your Lisp code using Doxygen syntax.

The doxygen-filter function in doxygen-lisp-filter takes a stream containing Lisp code and generates Doxygen documentation for it. It supports all standard Doxygen commands, including @brief, @param, @return, and @example. It also handles multi-line and single-line comments, which can be documented using the /** ... */ and /// ... syntax, respectively.

Installation

doxygen-lisp-filter can be installed using Quicklisp. First, make sure you have Quicklisp installed. Then, clone the doxygen-lisp-filter repository into your Quicklisp local projects directory:

ruby
Copy code
$ git clone https://github.com/yourusername/doxygen-lisp-filter.git ~/quicklisp/local-projects/doxygen-lisp-filter
You can then load doxygen-lisp-filter using Quicklisp:

lisp
Copy code
(ql:quickload :doxygen-lisp-filter)
Usage

To use doxygen-lisp-filter with Doxygen, you need to add it to your Doxygen configuration file. Here's an example configuration file that uses doxygen-lisp-filter:

makefile
Copy code
# Doxyfile for MyProject

# Specify the input files
INPUT = src/

# Specify the output directory
OUTPUT_DIRECTORY = doc/

# Use doxygen-lisp-filter to document Lisp code
FILTER_PATTERNS = *.lisp=doxygen-lisp-filter %s
This configuration file tells Doxygen to look for Lisp files in the src/ directory, and to generate documentation in the doc/ directory. It also tells Doxygen to use the doxygen-lisp-filter input filter for files with a .lisp extension.

Example

Here's an example Lisp file that uses doxygen-lisp-filter:

lisp
Copy code
(defun square (x)
  "Return the square of X."
  (* x x))
When processed with doxygen-filter, this file generates the following Doxygen documentation:

c
Copy code
/**
 * @brief square
 * 
 * @param x 
 * 
 * @return 
 */
License

doxygen-lisp-filter is released under the MIT License. See the LICENSE file for details.


