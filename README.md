## Classification of tumors into 2 categories (benign or malignant) based on features of tumor cell nuclei     
      
### Summary     
      
#### Links    
    
[Project proposal](https://github.com/rali88/Capstone-Project-1/blob/master/Project%20proposal.pdf)      
[jupyter notebook](https://github.com/rali88/Capstone-Project-1/blob/master/Tumor%20classification.ipynb)     
[Analysis report](https://github.com/rali88/Capstone-Project-1/blob/master/Analysis%20report.pdf)        
[Slide deck](https://github.com/rali88/Capstone-Project-1/blob/master/Slide%20Deck.pptx)       
        
**Problem:** classification of tumor nuclie in to 2 classes: malignant and benign.   
   
**Client:** Cancer pathologists and oncologists.     
   
**Data source:** UCI machine learning repository, created by Dr. William H. Wolberg of University of Wisconsin Hospitals. [Link](https://www.kaggle.com/uciml/breast-cancer-wisconsin-data/data)

**Data type:** Comma separated file with rows labeled with patient identification number. 
     
**Target variable:** first column, labeled diagnosis, contains a series of ‘M’ (malignant) or ‘B’(benign) strings.   
       
**Features:** Rest of the columns containing values for 30 different parameters describing the shape of the cell nucleus.   
      
**Methodology and results**
      
1- **Data wrangling:** Check for sample repittion, check for NaN values, normalize data if needed and remove unnecessary columns.     
       
2- **Exploratory and statistical analysis:** Correlation between different features:        

![Correlation matrix](https://github.com/rali88/Capstone-Project-1/blob/master/CorrelationPlot.png)   

There is a high correlation between radius, area and perimeter. Moreover, a high correlation between compactness, concavity and number of concave points can also be seen. Performing Principal Component Analysis (PCA) before building our predictive models might be beneficial.      
        
Differences between the features for the two classes:      
       
![Difference](https://github.com/rali88/Capstone-Project-1/blob/master/BoxAndStripPlot.png)        
	
Almost all the features differ between the two classes.     
       
Calcualating percentage changes:     
      
![Percentage change](https://github.com/rali88/Capstone-Project-1/blob/master/PercentageChangePlot.png)      
       
The largest changes are observed in the concavity and the number of concave points. Area of malignant nuclei also increases compared to benign nuclei.      
      
Statistical test to check for significant differences:     
       
Normalcy test shows that data is not normally distributed. Mann-whitney u test shows that all features are statistically different between the 2 classes.

3- **Visual model:**    
      
![Visual model](https://github.com/rali88/Capstone-Project-1/blob/master/VisualModel.png) 

4- **Shallow machine learning models:**     
       
Princiapal component analysis (PCA) for feature selection. 
       
![PCA](https://github.com/rali88/Capstone-Project-1/blob/master/PCA.png)     

Variance of the data can be completely explained by 15 components. 10 components explain most of the variance in the data (~97%). We have reduced the dimensionality of our data by a factor of 2!      
        
Using PCA- transformed data, split into test and train data set:      
      
k nearest neighbors model:      
       
The f-1 score for test data is 0.96. If the test data is large, the model is slow to predict. One cannot know the weight different features in the data have on predicting the class of tumors.       
        
Logistic regression model:     
        
The f-1 score for test data is 0.97. This model will be faster in predicting on a large data set, and it also has a better f-1 score compared to k-NN. Still, cannot know the weight different features in the data have on predicting the class of tumors.      
           
Using non-transformed data, split into test and train data set:        
       
Logistic regression model:       
       
The coefficients for different features, which quantify the effect of different features on predicting the tumor class, are known. The f-1 score on test data is reduced to 0.95.      
