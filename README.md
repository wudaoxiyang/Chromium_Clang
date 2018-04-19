# Chromium_Clang

The Chromium web browser for Windows built with the open source Clang compiler and LLD linker using the Polly "high-level loop and data-locality optimizer" for LLVM.

About polyhedral optimization in general:

http://polyhedral.info/

About the Polly optimizer:

http://polly.llvm.org/

The latest build release includes the following Polly configuration options:

"-mllvm", "-polly",
"-mllvm", "-polly-detect-profitability-min-per-loop-insts=40",
"-mllvm", "-polly-invariant-load-hoisting",
"-mllvm", "-polly-optree-normalize-phi",
"-mllvm", "-polly-precise-fold-accesses",
"-mllvm", "-polly-precise-inbounds",
"-mllvm", "-polly-run-dce",
"-mllvm", "-polly-vectorizer=stripmine",
"-Xclang", "-Rpass-analysis=polly",

The V8 JavaScript engine includes the added configuration option:

"-mllvm", "-polly-delicm-max-ops=0",

Additional features of the build include modified compiler optimizations including whole-program analysis and cross-module optimization using "full" link time optimization (LTO) via build configuration modifications.

Implementation of various options are subject to change depending upon performance, stability, and similar paramaters.

Link to latest build release:

