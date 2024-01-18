# {{ cookiecutter.project_name }}

## Summary
* What the project is intended to do 
* how to set it up 
* Run Tests to check everything works
* How to make changes 


## Setup
* Make sure your Project is installable in Dev mode as a [Python Package](https://towardsdatascience.com/setuptools-python-571e7d5500f2)
* It should have a setup.py
* Add Dev and Test Packages to setup.py. 
* Only add Prod packages to requirements.txt
* Setup virtualenv in current dir and add it to gitignore (already added)
```bash
python3 -m venv {{ cookiecutter.virtual_env }}
source {{ cookiecutter.virtual_env }}/bin/activate
python3 -m pip install --upgrade pip setuptools wheel
python3 -m pip install  -e .[dev]
```

## Pre-commit Hooks
* Use pre-commit hooks to make mandatory checks before committing
* Use Black for Auto-formatting
* Use isort for grouping imports
* Use pylint for Linting
```bash
pre-commit install
pre-commit autoupdate
```
* Use custom Hooks for anything that has to be forced everytime, like License checks
```bash
chmod +x /path/to/file.sh
```

## Set Envirnoment Variables
* set PYTHONPATH to project root


# Setup Git
```bash 
git init
git add .
git commit -am 'init'
git push -u origin
```

## Testing
* Use [Pytest](https://towardsdatascience.com/pytest-with-marking-mocking-and-fixtures-in-10-minutes-678d7ccd2f70) for Testing. 
* Run tests in the test_project directory.
* Set pytest.ini if Required and set Pythonpath

Run a Specific Test:
```bash
pytest {{ cookiecutter.repo_name }}_tests/test_sample.py::test_function_one -n <number of workers> 
```
Run Tests matching name:
```bash
pytest -k "keyword" 
```

## Documentation with mkdocs
Use mkdocs to create documentation from Docstrings.
```bash
python3 -m mkdocs new .
```

## Continuous Experimentation
* Use Git Branches for Experiments
* Merge only successfull Experiments to Main Branch
* Keep track of failed Experiments
* Keep Code, Dataset, Artifacts & Model verions in Git to reproduce experiments
