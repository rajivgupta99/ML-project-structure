# ML-project-structure

Inspired from (with few changes): [Cookiecutter Data Science](http://drivendata.github.io/cookiecutter-data-science/)

```
ml-project-structure/
├── Dockerfile                   
├── LICENSE     
├── README.md                  
├── Makefile
├── requirements.txt                       
├── setup.py                     
├── startup.sh  
├── .github                      
│   └── workflows                                        
├── configs                      
│   ├── model1.yaml
│   ├── config.ini                  
│   ├── config.py
│   └── .env   
├── data                         
│   ├── external                 
│   ├── interim                  
│   ├── processed               
│   └── raw                      
├── docs                         
├── model_weights                
├── notebooks                    
├── references                   
├── reports                                                 
└── src                          
    ├── __init__.py              
    ├── data_preprocessing       
    │   ├── data_preprocessing.py  
    │   ├── build_features.py   
    │   ├── cleaning.py          
    │   ├── ingestion.py         
    │   ├── labeling.py          
    │   ├── splitting.py         
    │   └── validation.py        
    ├── imagegeneration          # Use Case 1             
    │   ├── __init__.py
    │   ├── hyperparameters_tuning.py 
    │   ├── imagegeneration.py
    │   ├── model.py
    │   ├── predict.py
    │   ├── preprocessing.py
    │   └── train.py
    ├── textgeneration            # Use Case 2        
    │   ├── __init__.py
    │   ├── hyperparameters_tuning.py 
    │   ├── textgeneration.py
    │   ├── model.py
    │   ├── predict.py
    │   ├── preprocessing.py
    │   └── train.py
    ├── utils                  
    │   ├── __init__.py
    │   ├── common.py 
    │   ├── data_manipulation.py
    │   ├── data_operations.py
    │   └── misc.py   
    └── visualization        
        └── visualize.py   
```

The **configs** folder contains all the configuration files, such as model hyperparameters.

The **data** folder contains all data files used during model training and tesing.

The **model_weights** contains pre-trained model weights.

The **notebooks** contains .ipynb version of our code which is readily-executable.

The **reports** contains generated results and outputs in image, graphs and pdf formats.

The **data_preprocessing** folder (the sub-folder of **src**) includes the following files:

- `ingestion.py`: Used to gather the data. If you need to create backups, protect private information, or create a metadata catalog, it’s best to do it here.

- `cleaning.py`: Used to clean the data by reducing outliers/noise, handling missing values, etc.

- `labeling.py`: Used to label the data if necessary.

- `splitting.py`: Used to split the data into test and train sets.

- `validation.py`: Used to validate the data (to ensure it is ready for training).

- `build_features.py` has been moved to this folder because building features means organizing your dataset into a specific structure.

- **`data_preprocessing.py`**: Used as a single source file where class PreProcessing() can be defined with all the methods such as: ingestion, cleaning, labeling, splitting, validation

In the **imagegeneration** folder (the sub-folder of **src**) - **Use Case 1**:

- `model.py`: used to define the model architecture.

- `preprocessing.py`: Used to preprocess the data before feeding it to the model.

- `train.py`: Used to train the model.

- `hyperparameters_tuning.py`: Used to tune the model and/or the training hyperparameters.

- `predict.py`: Used to make predictions on random images (not from the dataset).

- `imagegeneration.py`: Used as a single source file for image generaton use case where a class is defined ImageGeneration() with all it's methods: train, predict, preprocessing, hyperparameters_tuning.

In the **textgeneration** folder (the sub-folder of **src**) - **Use Case 2**:

- `model.py`: used to define the model architecture.

- `preprocessing.py`: Used to preprocess the data before feeding it to the model.

- `train.py`: Used to train the model.

- `hyperparameters_tuning.py`: Used to tune the model and/or the training hyperparameters.

- `predict.py`: Used to make predictions on random images (not from the dataset).

- `textgeneration.py`: Used as a single source file for image generaton use case where a class is defined TextGeneration() with all it's methods: train, predict, preprocessing, hyperparameters_tuning.

The **utils** folder (the sub-folder of **src**) includes the following files:

- `common.py`:

- `data_manipulation.py`: 

- `data_operations.py`: 

- `misc.py`: 

The **visualizations** folder includes the following:
- `visualize.py`: this file includes functions used to visualize the data 
	

**Dockerfile**:

**main.py**:

**requirements.txt**:

**setup.py**:

**startup.sh**:

**LICENSE**:

Some preprocessing functions can be used across all models, so it’s possible to create a single preprocessing file and move it to the data folder to avoid duplicating functions. However, it’s recommended to keep the preprocessing file separate to improve the model’s reusability and prevent potential problems in the future.

