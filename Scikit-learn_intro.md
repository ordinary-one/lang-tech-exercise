### 1. Loading and Saving Data with Pandas
    >Pandas for data analysis:
     Convert a Python’s list, dictionary or Numpy array to a Pandas data frame
     Open a local file using Pandas, usually a CSV file, but could also be a delimited text file (like TSV)
     Open a remote file or database like a CSV or a JSONon a website through a URL or read from a SQL table/database*

#### 1) Read a (csv) file into DataFrame: 
    df = pd.read_csv()
#### 2) Show the DataFrame:
    df.head() #show the first 5 lines by default
    df.head(num)
#### 3) Column selection, addition, deletion of DataFrame (dict-like)
      Select column by label: df[label] / df[label].values
      Select row by label:  df.loc[label]	
      Select row by integer location: df.iloc[loc]	
      Slice rows: df[5:10]	
      Select rows by boolean vector: df[bool_vec]
      
      i.e. df['three'], df.loc['b'], df.iloc[3]
           df.iloc[:, 1:3], df.iloc[[0,2], [1, 3]]

### 2. Feature Selection
    Given columns should be divided into two types of target variable and feature variables.
    x = df.iloc[:, 1:len(df.columns)-1] #features
    y = df.iloc[:, [len(df.columns)-1]] #target

### 3. Splitting Data
    To understand model performance, dividing the dataset into a training set and a test set.
    #Split dataset into training set and test set
    x_train, x_test, y_train, y_test = train_test_split(x, y, test_size=0.3)
    #Check the sizes
    print(x_train.shape, x_test.shape, y_train.shape, y_text.shape)

### 4. Building Decision Tree Model
    Create a Decision Tree Model using Scikit-learn.
    
    #Create Decision Tree classifer object
    clf = DecisionTreeClassifier()

    #Train Decision Tree Classifer
    clf = clf.fit(x_train,y_train)

    #Predict the response for test dataset
    y_pred = clf.predict(x_test)

### 5. Evaluating Model
    Estimate how accurately the classifier or model can predict the type of cultivars.
    Accuracy can be computed by comparing actual test set values and predicted values.

    print("Accuracy:",metrics.accuracy_score(y_test, y_pred))
