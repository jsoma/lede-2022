# Installing and setting up Jupyter Notebook

## Checking your Python install

You might want to start by running `which python` and `python --version` to make sure it looks like the "right" Python is being used. It is a `pyenv` Python, just like it should be? Does the version look good?

If not, you'll want to check the [Python installation guide](install-python.md).

## Install Jupyter

You can install Jupyter Notebook with the following command:

=== ":fontawesome-brands-apple: OS X"

    ```bash
    pyenv install jupyter
    ```

=== ":fontawesome-brands-windows: Windows"

    ```bash
    pip install jupyter
    pyenv rehash
    ```

It might be quick, it might be slow, but hopefully it eventually finishes without any errors! Don't worry if it yells `WARN` about pip versions or something, it's no big deal unless it actually says `ERR` or `ERROR`.

!!! info "Confirm it worked"

    Run the following command to try to check Jupyer's version number.

    ```bash
    jupyter --version
    ```

    If it says "command not found," it didn't work. If it says anything else, you're okay.

## Setting your Python as the Jupyter Python

When you have multiple versions of Python on your computer, it turns out that sometimes the command line Python and the Jupyter Python don't match up. 

```bash
pip install ipykernel
python -m ipykernel install --user
```

!!! info "Confirm it worked"

    Run the following command to check the list of Pythons attached to Jupyter.

    ```bash
    jupyter kernelspec list --json
    ```

    Skim through the awful, awful bushel of text it presents to you. Do you see `.pyenv` somewhere in it? If so, it worked.
