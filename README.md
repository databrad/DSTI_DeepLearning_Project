## Overview

------------------------------------------------------------------------

-   **Description**

Based on some social media comments, we want to predict people's mental health state.

Please, refer to the `Introduction` part of the notebook `cleaning_notebooks/clean_raw_data.ipnyb` to have a full understanding of where the data came from and kind of biases that could exist in this analysis.

-   **Structure**

A global view of this project structure is :

```         
DSTI_DEEPLEARNING_PROJECT/
├─ cleaning_notebooks/
│  ├─ __init__.py
│  ├─ clean_raw_data.ipynb
│  ├─ images/
│  │  ├─ image-1.png
│  │  ├─ image-2.png
│  │  ├─ image.png
├─ modeling_notebooks/
│  ├─ __init__.py
│  ├─ how_to_read_clean_data.ipynb
│  ├─ base_model/
│  │  ├─ __init__.py
│  │  ├─ train_a_catboost_model.ipynb
│  ├─ advanced_model/
│  │  ├─ __init__.py
│  │  ├─ train_a_full_deep_learning_model.ipynb
├─ .gitignore
├─ LICENSE
├─ README.md
├─ README.html
├─ poetry.lock
├─ pyproject.toml
```

-   **Packages Management**

`poetry` is used for packages' management of this project.

## Installation

------------------------------------------------------------------------

-   **Clone the repository :**

```         
git clone https://github.com/databrad/DSTI_DeepLearning_Project.git
```

-   **Create a virtual environment, activate it and install all necessary packages :**

```         
conda create -n myenv python=3.11

conda activate myenv

conda install -c conda-forge poetry

poetry install --no-root
```

-   **Inspect and/or execute notebooks :**
    -   You can freely inspect and execute any notebook in the folder `modeling_noteboks/*` .

    -   You can freely inspect in the folder `cleaning_notebooks/clean_raw_data.ipnyb`, but before executing it :

        -   Read well the introduction part of the notebook, and download any needed raw datasets explained in it (in total \~2GB). You can also download the .rar version of them using this [link](https://huggingface.co/datasets/pfacouetey/DSTI_Deep_Learning_Project_2025/tree/main). `kaggle_data.rar` contains the one csv file that need to be put in the folder `kaggle_data/*`, whereas `zenodo_data.rar` contians all the 59 csv files that need to put in the `zenodo_data/*` folder.

        -   Create a folder `data` with this structure :

        ```         
        DSTI_DEEPLEARNING_PROJECT/ 
        ├─ data/ 
        │ ├─ raw_version/ 
        │ │ ├─ kaggle_data/ 
        │ │ ├─ zenodo_data/ 
        │ ├─ clean_version/
        ```

        -   Put all the 59 ZENODO data files downloaded in the `DSTI_DEEPLEARNING_PROJECT/data/raw_version/zenodo_data/` folder, whereas put the one KAGGLE file in the folder `DSTI_DEEPLEARNING_PROJECT/data/raw_version/kaggle_data/` .
        -   Finally, you can execute all the cells of the notebook except the last one since you do not have rights needed to push on the Hugging Face repository specified in the variable `CLEAN_DATA_PATH` even though you can read from it.

## **Licence**

This project is registered under the terms of the MIT license. For any further details, consult the LICENSE file.