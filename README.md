# CB_Recommednder_Project

It is a univeristy project from Recommenders system class. In this project I worked with real life hotel data. The aim was to create Content-based recommender so that it would recommend apropriate hotel for a user based on given features. Recommender was evaluated on a test set, I wanted to achieve the highest HR@10 possible and perforem better than Amazon Recommender. Firstly I performed basic data manipulation, later I created separate dataframes for users and items instances, so that it would fit to the Content-based recommender. Finally recommender was initialized using different ML model such as LinearRegressionCBUIRecommender, SVRCBUIRecommender, RandomForestCBUIRecommender, XGBoostCBUIRecommender. Optimal parameters for every model were found using hyperopt package. At the end, score of every model was compared with Amazon Recommender on the same data.

HR@10 results achieved using different ML models:
- LinearRegression - 0.231500
- SVR - 0.043109
- RandomForest - 0.124576	
- XGBoost - 0.124576

The best result was achieved with LinearRegression. The worst one was with SVR it might be because I did not tune hyperparamters for that model because it would have taken to long. Here is a table with all results, LinearRegression managed to beat Amazon Recommender.

![image](https://user-images.githubusercontent.com/91895188/236181310-15b95f67-ff9e-48e5-8cb0-cfd89008db7b.png)


# Preparing your computer
1. Install https://www.anaconda.com/download with Python 3.8
2. Install https://git-scm.com/downloads
3. Fork this repository to your GitHub account
4. Go to the chosen folder on your machine where you want to have a local copy of the repository. Right-click in the folder and from the context menu choose "Git Bash Here". Run the following command to clone the forked repository on your GitHub account to your local machine

          git clone <your_repository_address_which_you'll_find_in_your_github>

5. Prepare your conda environment
- Open Anaconda Prompt as administrator
- Make sure you're in the repository main folder. Run the following command

          conda env create --name rs-class-env -f environment.yml
6. In Git Bash open the repository folder and activate just created environment with the following command

        conda activate rs-class-env
        
7. In Git Bash type

         jupyter notebook
         
A new tab with Jupyter Notebook should open in your browser. There will be folder 'data' with hotel data, 'data_preprocessing' with functions to manipulate data, 'evaluation_and_testying' with functions to evaluate data, 'recommenders' with Amazon recommender to compare results. There will be notebooks 'project_1_data_preparation' and 'project_1_recommender_and_evaluation'. To run code in that notebooks go in there and alt + enter every cell or click Cell -> Run All. Warning: running 'project_1_recommender_and_evaluation' will take very long time, if you want to stop that process click Kernal -> Restart. 

In case of any errors with packages, type

        conda install <name of missing package>
  
Used packages:
- numpy
- pandas
- matplotlib
- seaborn
- sklearn
- hyperopt
- datetime
