# ML-project-structure

Inspired from (with few changes):
1. [Cookiecutter Data Science](http://drivendata.github.io/cookiecutter-data-science/)

```
ml-project-structure/
├── LICENSE     
├── README.md                  
├── Makefile                     # Makefile with commands like `make data` or `make train`
|
├── configs                      # Config files (models and training hyperparameters)
│   └── model1.yaml
│   └── config.ini                  
├── configs                      # Config files (models and training hyperparameters)
│   └── model1.yaml
│   └── config.ini
│   └── config.py
│   └── .env   
│
├── data                         
│   ├── external                 # Data from third party sources.
│   ├── interim                  # Intermediate data that has been transformed.
│   ├── processed                # The final, canonical data sets for modeling.
│   └── raw                      # The original, immutable data dump.
│
├── docs                         # Project documentation.
│
├── model_weights                # Pre-Trained and serialized models.
│
├── notebooks                    # Jupyter notebooks.
│
├── references                   # Data dictionaries, manuals, and all other explanatory materials.
│
├── reports                      # Generated analysis as HTML, PDF, LaTeX, etc.
│   └── figures                  # Generated graphics and figures to be used in reporting.
│
├── requirements.txt             # The requirements file for reproducing the analysis environment.
└── src                          # Source code for use in this project.
    ├── __init__.py              # Makes src a Python module.
    │
    ├── data_preprocessing       # Data engineering scripts.
    │   ├── build_features.py    
    │   ├── cleaning.py          
    │   ├── ingestion.py         
    │   ├── labeling.py          
    │   ├── splitting.py         
    │   └── validation.py        
    │
    ├── imagegeneration          # Use Case 1             
    │   └── __init__.py
    │   └── hyperparameters_tuning.py 
    │   └── imagegeneration.py
    │   └── predict.py
    │   └── preprocessing.py
    │   └── train.py
    │ 
    ├── textgeneration            # Use Case 2        
    │   └── __init__.py
    │   └── hyperparameters_tuning.py 
    │   └── textgeneration.py
    │   └── predict.py
    │   └── preprocessing.py
    │   └── train.py
    |
    ├── utils                  
    │   └── __init__.py
    │   └── common.py 
    │   └── data_manipulation.py
    │   └── data_operations.py
    │   └── misc.py   
    │
    └── visualization        # Scripts to create exploratory and results oriented visualizations.
        ├── visualize.py       
            
```
