# mnist_project

mnist project for mlops

## Project structure

The directory structure of the project looks like this:
```txt
├── .github/                  # Github actions and dependabot
│   ├── dependabot.yaml
│   └── workflows/
│       └── tests.yaml
├── configs/                  # Configuration files
├── data/                     # Data directory
│   ├── processed
│   └── raw
├── dockerfiles/              # Dockerfiles
│   ├── api.Dockerfile
│   └── train.Dockerfile
├── docs/                     # Documentation
│   ├── mkdocs.yml
│   └── source/
│       └── index.md
├── models/                   # Trained models
├── notebooks/                # Jupyter notebooks
├── reports/                  # Reports
│   └── figures/
├── src/                      # Source code
│   ├── project_name/
│   │   ├── __init__.py
│   │   ├── api.py
│   │   ├── data.py
│   │   ├── evaluate.py
│   │   ├── models.py
│   │   ├── train.py
│   │   └── visualize.py
└── tests/                    # Tests
│   ├── __init__.py
│   ├── test_api.py
│   ├── test_data.py
│   └── test_model.py
├── .gitignore
├── .pre-commit-config.yaml
├── LICENSE
├── pyproject.toml            # Python project file
├── README.md                 # Project README
├── requirements.txt          # Project requirements
├── requirements_dev.txt      # Development requirements
└── tasks.py                  # Project tasks
```


Created using [mlops_template](https://github.com/SkafteNicki/mlops_template),
a [cookiecutter template](https://github.com/cookiecutter/cookiecutter) for getting
started with Machine Learning Operations (MLOps).


## Run scripts

Preprocess data from raw to processed folder
Images with mean 0 and sd 1
(venv) mariavendas@MariaLaptop:~/my_project$ invoke preprocess-data

Requirements
(venv) mariavendas@MariaLaptop:~/my_project$ invoke requirements

See what tasks can be run on command line
(venv) mariavendas@MariaLaptop:~/my_project$ invoke --list

See the model architecture and parameters
(venv) mariavendas@MariaLaptop:~/my_project$ python src/my_proje
ct/model.py

Train the model, saved it to the models folder, save statistics to reports/figures folder
(venv) mariavendas@MariaLaptop:~/my_project$ python src/my_project/train.py

Evaluate the model on test set, load the model from the models folder, print out accuracy
(venv) mariavendas@MariaLaptop:~/my_project$ python src/my_project/evaluate.py models/model.pth

Loads a pre-trained network, visualize intermediate representations in 2D space using t-SNE, save visualization in reports/figures
(venv) mariavendas@MariaLaptop:~/my_project$ python src/my_project/visualize.py models/model.pth

