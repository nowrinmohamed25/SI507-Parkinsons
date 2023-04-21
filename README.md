#  Parkinson's Disease Progression Prediction

I propose to predict the progression of Parkinson's Disease (PD) using protein and peptide data measurements. Parkinson's Disease is a chronic and progressive neurological disorder that affects movement, causing symptoms such as tremors, stiffness, and impaired balance and coordination. It is the second most common neurodegenerative disorder, affecting approximately 1% of people over the age of 60. Early and accurate prediction of disease progression can help healthcare providers plan and adjust treatment regimens accordingly, including medications, physical therapy, and surgical interventions. It can also help patients and their caregivers better understand what to expect in terms of symptoms and disease trajectory.

The progression in patients with PD is measured by MDS-UPDRS (Movement Disorder Society-Sponsored Revision of the Unified Parkinson's Disease Rating Scale), which is a comprehensive assessment of both motor and non-motor symptoms associated with Parkinson's. We plan to develop a model trained on data on protein and peptide levels over time in subjects with Parkinson’s disease.

I believe this work could help provide important breakthrough information about which molecules change as Parkinson’s disease progresses.

Contributors
* Nowrin Mohamed (nowrin)

# Steps to run the code:

1. eda.ipynb - Exploratory data analysis of all 4 datasets present in the project with basic manipulation and also visualization.
    
    Data visualization and Interaction:

    There are multiple plots used in this file especially using Plotly for the user to hover and interact with the graph to see the data in detail.
    In addition to this a command line user interface set up is done which asks several questions to the user and depending on the input, the data is retrieved and displayed. For example,

    1. A question which asks the user what kind of plot is required to plot UPDRS scores across the visit_month? Please choose either bar or hist. 

    2. A question for the user to choose a patient id to see that patient's disease progression. Name any patient_id from the clinical_data table available under data\clinical_data. For example, 65043


2. graphConstruct.ipynb - Arrangement of Proteins and Peptides into a bipartite graph and store it in a json named graphJson.json

    Data visualization and Interaction:

    The graph is plotted using networkx library for the number of nodes the user wants to display. Please note that the database is huge so giving a higher value might not give a proper visualization. Try giving any number between 5 and 10 to visualize the graph properly. 

     A command line user interface set up is done which asks several questions to the user and depending on the input, the data is retrieved and displayed. For example,

    1. A question which asks the user if they want to visualise the graph and also how many nodes should be present in the graph? Please give any value between 5 and 10 as mentioned above.

3. graphAnalysis.ipynb - construct the graph by reading the json file where the graph is constructed and stored from file in 2 point.   Data analysis is done and found interesting relationships.
    
    Data visualization and Interaction:

    The graph is constructed from the json with all the nodes for detailed analysis.

    A command line user interface set up is done which asks several questions to the user and depending on the input, the data is retrieved and displayed. For example,

    1. A question for the user to choose a protien source node and peptide target node to find the path between those. Please choose any  protein or peptide from the train_proteins.csv and train_peptides.csv respectively. For example, the protein can be IEIPSSVQQVPTIIK and peptide can be VIAVNEVGR.

    2. A question for the user if they want to print and see all paths in the graph. Answer yes if you want to see all paths.

2. main.ipynb - Preprocessing, data transformation, and all the ML models are present in this file.

3. data\ - contains the original train_clinical_data.csv, supplemental_clinical_data.csv, train_proteins.csv and train_peptides.csv data. In addition to this, it contains the processed data as peptides_features.csv and proteins_features.csv

Please note that all libraries which are mentioned in the first block of all the above files need to be installed using pip3 install <Libraryname>

There are files apart from the above which are categorized as rough work but not used.

# Data Structure description

In graph.ipynb, the proteins and peptides data are arranged in the form of a bipartite graph. Each peptide is represented as a node in one set, and each protein is represented as a node in the other set. Each peptide node is connected to the protein nodes that it binds to or interacts with, based on the data provided in the dataset and Peptide Abundance is the weight of the edges.

## What is a Bipartite graph?

A bipartite graph is a type of graph that consists of two distinct sets of nodes, and all edges connect nodes from one set to nodes from the other set. This property makes the data organization part of this project and identifying the relationship between proteins and peptides easier.

