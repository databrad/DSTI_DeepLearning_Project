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
├─ production/
│  ├─ __init__.py
│  ├─ inference_on_new_data.ipynb
├─ modeling_notebooks/
│  ├─ __init__.py
│  ├─ advanced_model/
│  │  ├─ __init__.py
│  │  ├─ train_deep_learning_models.ipynb
│  ├─ base_model/
│  │  ├─ __init__.py
│  │  ├─ train_a_catboost_model.ipynb
├─ .gitattributes
├─ .gitignore
├─ LICENSE
├─ README.md
├─ poetry.lock
├─ pyproject.toml
```

Main parts of the project are :
- Data cleaning process done in the folder `DSTI_DEEPLEARNING_PROJECT/cleaning_notebooks/*`. 
- Models' training and evaluation done in the folder `DSTI_DEEPLEARNING_PROJECT/modeling_notebooks/*`. 
- Real-world usage of the trained models explained in the folder `DSTI_DEEPLEARNING_PROJECT/production/*`.

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

conda install -c conda-forge platformdirs

conda install -c conda-forge poetry

poetry install --no-root
```

-   **Inspect and/or execute notebooks (using any GPU is recommended for their execution):**

    -   You can freely inspect in the folder `cleaning_notebooks/clean_raw_data.ipnyb`, but before executing it :

        -   Read well the introduction part of the notebook, and download any needed raw datasets explained in it (in total \~2GB). You can also download the .rar version of them using this [link](https://huggingface.co/datasets/pfacouetey/DSTI_Deep_Learning_Project_2025/tree/main). `kaggle_data.rar` contains the one csv file that need to be put in the folder `kaggle_data/*`, whereas `zenodo_data.rar` contains all the 59 csv files that need to put in the `zenodo_data/*` folder.

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

        -   Finally, you can execute all the cells of the notebook except the last one since you do not have rights needed to push on the Hugging Face repository specified in the variable `CLEAN_DATA_PATH` even though you can read from it. Without any GPU, it could quite time but still you will have results.

    -   You can freely inspect and execute any notebook in the folder `modeling_noteboks/*`.

        -   For any notebook in the folder `modeling_notebooks/base_model/*`, no additional setup is needed. You can execute them locally, but first time it could take some time. Inspect all cells to understand any process done.

        -   For the folder `modeling_notebooks/advanced_model/` (Powerful GPU especially needed in this part):

            -   Go to this [website](https://docs.wandb.ai/), create an account (the first 30 days are free), then set your local `WANDB_API_KEY` values in a .env file.

            -   The notebook `modeling_notebooks/advanced_model/train_deep_learning_models.ipynb` displays the whole training-evaluation and inference of trained models :

                -   Follow well the `Collab Setup` part of the notebook.
                -   We make sure to comment any saving part of the trained models since there's restricted access on pushing them, even if you can load from it.

    -   You can freely inspect and execute any notebook in the folder `production/*` (can be executed locally using your local your CPU) :

        -   The notebook `production/inference_on_new_data.ipynb` displays the process of how to infer on new data with the trained models. At the end of the notebook, you have this link <https://huggingface.co/spaces/paragonadey/mental-health-text-classifier> to access the best of the trained models to predict mental health state of a person based on the text he provides online.

-    ## Test the model with a frontend:
  
  Steps to launch and test the app !

Install Docker Desktop from : https://docs.docker.com/desktop/setup/install/windows-install/

The application is composed of two docker images: backend and frontend.

    1 - Pull the images from docker hub (backend and frontent)
    
        docker pull bradesteve/mental-health-frontend:latest
        docker pull bradesteve/mental-health-backend:latest
    
    2 - Run the containers :
    
        docker run -p 8000:8000 bradesteve/mental-health-backend:latest # backend runs on port 8000
        docker run -p 80:80 bradesteve/mental-health-frontend:latest # frontend runs on port 80
    
    3 - Launch the app in localhost :
    
        http://localhost:80


## **Licence**

This project is registered under the terms of the MIT license. For any further details, consult the LICENSE file.
