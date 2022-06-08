# RcppSMCdocs

Documentation for RcppSMC.

## Generate documentation

Two possibilities to generate documentation:

1. Good old doxygen:
    - create `./build` and `cmake ..` followed by `make docs`
    - produces html files in the directory `./build/docs_doxygen/html`
    - view the documentation via `./build/docs_doxygen/html/index.html`

2. Using Sphinx (modern look, facilitates readability, but less detailed API documentation)
    - use `make html` inside `./docs_sphinx`
    - output is stored in `./docs_sphinx/html`
    - view the documentation via `./docs_sphinx/html/index.html`

## Sources

Links for resources on the doxygen-sphinx-breathe + webpage setup:

1. Medium 3part blog:
  - https://medium.com/practical-coding/c-documentation-with-doxygen-cmake-sphinx-breathe-for-those-of-use-who-are-totally-lost-7d555386fe13
  - https://medium.com/practical-coding/c-documentation-with-doxygen-cmake-sphinx-breathe-for-those-of-use-who-are-totally-lost-part-2-21f4fb1abd9f
  - https://medium.com/practical-coding/c-documentation-with-doxygen-cmake-sphinx-breathe-for-those-of-use-who-are-totally-lost-part-3-d20549d3b01f

2. Sources (more complicated) for above blog-series:
  - https://devblogs.microsoft.com/cppblog/clear-functional-c-documentation-with-sphinx-breathe-doxygen-cmake/
  - https://vicrucann.github.io/tutorials/quick-cmake-doxygen/
