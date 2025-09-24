
1. Clone the repository locally
```
git clone https://github.com/databrad/DSTI_DeepLearning_Project.git
```

2. Get into develop branch
```
git checkout develop
```
3. Create a new virtual environment, activate it and install necessary packages (poetry is used for packages management)
```
conda create -n myenv python=3.11

conda activate myenv

conda install -c conda-forge poetry

poetry install
```
4. Make sure everything is okay before start working

Go to the example_of_how_to_read_raw_data.ipynb notebook and run all cells to make sure you're able to access all raw data.

4. Before start working, create a new branch (e.g. feature/new-branch) from develop up-to-date
```
git checkout -b feature/new-branch develop
```
5. If you need to add any new package (e.g. new-package), just use :
```
poetry add new-package
```