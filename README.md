# question5
Text classification on consumer complaint data.
The dataset has been accessed from here: https://catalog.data.gov/dataset/consumer-complaint-database

Data Exploration:

The dataset has 18 columns and 9408224 entries in total. out of that only 1 column is integer datatype. Summary statistics were taken against the numerical variables, and the unique values in records were also observed. 
<img width="205" alt="statistics" src="https://github.com/user-attachments/assets/141a343d-d8eb-4c77-bb11-1dabc75824fd" />

Data Cleaning:

The dataset was analysed for missing values, errors and outliers. it was observed that, 11 columns had missing(NaN) values. the columns which had values more than 50% of the size of dataframe were removed. the rest columns had their NaN values replaced with the most repeating value in that respective column.
<img width="319" alt="NaN" src="https://github.com/user-attachments/assets/b83b915c-76c0-4f84-b65d-317df07ca1ab" /><img width="319" alt="dropcols" src="https://github.com/user-attachments/assets/ea266d4c-084f-4a30-8068-f6c37526c03e" />

this reduced the dataset size to:
Number of rows: 9408224
Number of columns: 15

Feature Creation:	

The product column was mapped to the newly created category column. there are 4 categories.i.e, 0-Credit reporting, repair, or other,1-Debt collection,2-Consumer Loan,3-Mortgage. these are multi class columns and will be used as target variable for model training and testing. Issue and Sub-Issue columns were also concatenated.


Feature Transformation: 

further, the texts in the columns were preprocessed. The data was cleaned by converting into lower case, removing special characters, extra spaces, numbers, and punctuation. Stop words are also removed from the texts. clean texts were vectorised i.e, converted into numerical features for modeling.


Feature Selection: 

features where the NaN values more than 50% of the dataframe size were removed.

this changed the dataset size to:
rows: 1241493
columns: 18 

Model Training:

The dataset was split into train and test sets. Three models were used for training the data.
1.Logistic Regression  
2.Multinomial NaiveBayes
3.LinearSVC

These models were tuned using parameters to reduce overfitting, high tolerance for early stopping.

Evaluation:
The models were evaluated against validation sets and also tested against new unseen data. on validation sets, Logistic regression achieved 94% accuracy, Multimodal NaiveBayes achieved 97% accuracy and LinearSVC achieved 97% accuracy. classification reports were generated for further analysis.

<img width="463" alt="LR" src="https://github.com/user-attachments/assets/ce103291-6564-4db2-b52c-f5c58e33d759" />
<img width="463" alt="MNB" src="https://github.com/user-attachments/assets/4c1bcaec-b5be-46e2-b12b-8cb203bee596" />
<img width="463" alt="Ls" src="https://github.com/user-attachments/assets/fb388981-be8d-4142-bbb2-2fd61173a1e6" />

