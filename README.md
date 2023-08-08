# Pycurl

## Usage

```
pybasecurl https://nextjsvietnam.com --output nextjsvietnam.com.html
```

## Install env


```sh
pip3 install --user pipenv
pipenv --python 3.9
```

- Activate virtualenv : pipenv shell
- Install dependencies: pipenv install

## References

- [argparse](https://docs.python.org/3/library/argparse.html)
- [packaging project](https://packaging.python.org/en/latest/tutorials/packaging-projects/)
- [Sample package](https://github.com/pypa/sampleproject/blob/main/src/sample/__init__.py)

## Test package

```sh
pip install -e .
```

## Build package


```sh
python -m build
```

## Upload package

```sh
# test
twine upload --repository testpypi dist/*
# production
twine upload --skip-existing --repository pypi dist/* --verbose
```

## Test with docker

```sh
winpty docker run --name python -it python bash
pip install pybasecurl
pybasecurl https://nextjsvietnam.com --output nextjsvietnam.com.html
cat nextjsvietnam.com.html
```

## Authenticate with pypi

nano $HOME/.pypirc

```
[distutils]
index-servers =
    pypi

[pypi]
#repository = https://upload.pypi.org/legacy/
username = __token__
password = your-pipy-api-token
```