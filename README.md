# buildstream-reprotest 

`buildstream-reprotest` is a tool that can be used to check the
[reproducibility](https://reproducible-builds.org/) of a project built using
[BuildStream](https://buildstream.apache.org/).

## Install
This is a python package that can be installed using `pip`
```
pip install git+https://gitlab.com/freedesktop-sdk/buildstream-reprotest
```

You can also use `pipx` to install it in a virtual environment to avoid
conflicts with other python packages you may have installed
```
pipx install git+https://gitlab.com/freedesktop-sdk/buildstream-reprotest
```

Please note that it doesn't declare a dependency on buildstream, and expects
to be able to find `bst` in the `PATH`.

## Usage

In your buildstream project, simply run
```
buildstream-reprotest element.bst output-directory/
```
where `element.bst` is the element you want to check, and `output-directory`
is the directory where to output the differences found in non-reproducible
elements.

`buildstream-reprotest` checks the given element and all its dependencies, so you might
want to pass the final output of your project or a `stack` element with multiple such
outputs.
