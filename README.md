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

The **configs** folder contains all the configuration files, such as model hyperparameters.
The data folder (the sub-folder of src) includes the following files:
	• ingestion.py: used to gather the data. If you need to create backups, protect private information, or create a metadata catalog, it’s best to do it here.
	• cleaning.py: used to clean the data by reducing outliers/noise, handling missing values, etc.
	• labeling.py: used to label the data if necessary.
	• splitting.py: used to split the data into test and train sets.
	• validation.py: used to validate the data (to ensure it is ready for training).
	• build_features.py: this file has been moved to this folder because building features means organizing your dataset into a specific structure.
In the models folder (the sub-folder of src), each model’s scripts are organized in the model’s folder and include:
	• model.py: used to define the model architecture.
	• dataloader.py: used to load the data to be fed to the model.
	• preprocessing.py: used to preprocess the data before feeding it to the model.
	• train.py: used to train the model.
	• hyperparameters_tuning.py: used to tune the model and/or the training hyperparameters.
	• predict.py: used to make predictions on random images (not from the dataset).
The visualization folder includes the following:
	• exploration.py: this file includes functions used to visualize the data during the data engineering process.
	• evaluation.py: this file includes functions used to visualize the training results.
	
Some preprocessing functions can be used across all models, so it’s possible to create a single preprocessing file and move it to the data folder to avoid duplicating functions. However, it’s recommended to keep the preprocessing file separate to improve the model’s reusability and prevent potential problems in the future.![image](https://github.com/rajivgupta99/ml-project-structure/assets/54449411/a14c615b-ba2b-45ef-9e3a-43d1960389dd)

