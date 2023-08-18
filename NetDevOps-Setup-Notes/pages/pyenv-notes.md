# pyenv Notes

<https://github.com/pyenv/pyenv>

- Using pyenv is a good habit for all projects/repos. It will help you avoid conflicts with python / package versions. It is recommended to read up and adopt this practice.

## Installing pyenv

See [Preparing the Environment](env-prep.md).

## Manage versions of Python on your workstation

- Versions stored in `${PYENV_ROOT}/versions` directory.

### Verify what's installed

```bash
pyenv versions
```

### See what's available for download

```bash
pyenv install --list
```

### Install an available version

```bash
pyenv install <VERSION>
```

### Uninstall an unneeded version

```bash
pyenv uninstall <VERSION>
```

### Set global version

```bash
pyenv global <VERSION>
```

## pyenv local

pyenv can be set locally, which applies to current directories and all sub-directories

```bash
pyenv local <VERSION>
```

### Verify local packages

```bash
pip3 list
```
