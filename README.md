# Capstone-Project-1
Capstone Project 1 for SpringBoard Data Science Career Track
## Classification of tumors into 2 categories (benign or malignant) based on features of tumor cell nuclei
### The problem
A tumor can be malignant (cancerous) or benign (non-cancerous). This classification is made by a pathologist who examines the tumor cells obtained from a biopsy under a microscope. One method employed by pathologists is to examine the shape of a cell nuclei and make a judgement based on it. 
The problem that is encountered in this regard, is that the shape is defined by many parameters such as the area of a nuclei, it’s perimeter and numerous other parameters. Making a judgement on which of these parameters are more important relative to other parameters requires a quantitative analysis of the differences in these parameters between the malignant and benign cases.  
### The clients and their need for this analysis
The client for this project are cancer pathologists and oncologists. Their decision on tumor classification determines the type of treatment that an oncologist will undertake. The proposed analysis will aid a pathologist in deciding the type of tumor. Also, it will increase the confidence of an oncologist who relies on the report of a pathologist.    
### Data: What it is and how will it be acquired 
The data for this analysis will be a csv file containing 30 features of a cell nuclei of a tumor cell. This will be acquired from the following data base link:
https://www.kaggle.com/uciml/breast-cancer-wisconsin-data/data
### Approach outline

1-	Read data and store it in a data frame.

2-	Perform data wrangling:

  •	Check data for duplicate values.
   
  •	Check data for NaN values.
   
  •	Check metadata to determine which of the columns are required for the analysis.
   
  •	Check if reshaping (melting or pivoting) the data frame helps in visualization and analysis.
   
3-	Perform visual exploratory data analysis:

  • Plot box plots to inspect changes in different parameters.
   
4-	Perform statistical exploratory data analysis to inspect changes in different parameter.

5-	Discover which of the parameters show the greatest changes between the two types of tumors.

### Deliverables

1-	The final code used for analysis.

2-	The full code (exploratory data analysis code) which can be read to see why the data frame is sliced in a certain manner and why a function for visualization is written.

3-	A final report describing the methodology used in the analysis and the results obtained from the analysis.
