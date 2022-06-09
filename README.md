# RcppSMCdocs

Documentation for RcppSMC.

## Types of documentation

Two types of documentation are available:

1. Good old doxygen:
    - create `./build` and `cmake ..` followed by `make docs`
    - produces html files in the directory `./build/docs_doxygen/html`
    - view the documentation via `./build/docs_doxygen/html/index.html`

2. Using Sphinx (modern look, facilitates readability, but less detailed API documentation)
    - use `make html` inside `./docs_sphinx`
    - output is stored in `./docs_sphinx/html`
    - view the documentation via `./docs_sphinx/html/index.html`

## Workflow to update, alter or re-generate documentation

### Making additions if underlying code changes

1. Copy new code into `./include` or `./src`
2. `git add .`, `git commit` and `git push`, which triggers automatic deployment
3. Github actions automatically deploys the page

### Switching between doxygen and Sphinx-read-the-docs-styles

The directory `./.github/workflows/docs.yml` contains the config for this. The
following part is relevant to change from Sphinx-style to doxygen-style web 
documentation:

```
...
- name: Build docs
      run: cd docs_sphinx  # cd build
        && make html       # && cmake ..
        && cd _build/html  # && make docs
        && touch .nojekyll # delete this statement if doxygen is used
...
FOLDER: docs_sphinx/_build/html # build/docs_doxygen/html- name: Deploy
      uses: JamesIves/github-pages-deploy-action@v4.3.3
      with:
        GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
        BRANCH: gh-pages # The branch the action should deploy to.
        FOLDER: docs_sphinx/_build/html # FOLDER: build/docs_doxygen/html
```

1. In the above snippet, the Sphinx style is run. To change to doxygen, switch
statements to:
    - `run: cd build` (`run: cd docs_sphinx` before)
    - `&& cmake ..` (`&& make html` before)
    - `&& make docs` (`&& cd _build/html` before)
    - delete `&& touch .nojekyll`
    - `FOLDER: build/docs_doxygen/html` (`FOLDER: docs_sphinx/_build/html` before)

2. `git add .`, `git commit` and `git push` which triggers automatic deployment

## Sources

Links for resources on the doxygen-sphinx-breathe + webpage setup I followed to
set up this workflow:

1. Medium 3part blog:
  - https://medium.com/practical-coding/c-documentation-with-doxygen-cmake-sphinx-breathe-for-those-of-use-who-are-totally-lost-7d555386fe13
  - https://medium.com/practical-coding/c-documentation-with-doxygen-cmake-sphinx-breathe-for-those-of-use-who-are-totally-lost-part-2-21f4fb1abd9f
  - https://medium.com/practical-coding/c-documentation-with-doxygen-cmake-sphinx-breathe-for-those-of-use-who-are-totally-lost-part-3-d20549d3b01f

2. Sources (more elaborated) upon which this blog-series is based on:
  - https://devblogs.microsoft.com/cppblog/clear-functional-c-documentation-with-sphinx-breathe-doxygen-cmake/
  - https://vicrucann.github.io/tutorials/quick-cmake-doxygen/
