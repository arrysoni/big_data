# CMPSC 410: Big Data Programming and Analytics

This repository contains my lab assignments and mini projects for **CMPSC 410: Big Data Programming and Analytics** at Penn State.

The coursework focuses on big data processing, distributed computing, PySpark programming, machine learning pipelines, recommendation systems, clustering, dimensionality reduction, and large language model fine-tuning. The repository includes a mix of Jupyter Notebooks and exported HTML reports that document completed lab work, code outputs, results, and written analysis.

## Repository Overview

| File         | Type         | Topic                                                     |
| ------------ | ------------ | --------------------------------------------------------- |
| `lab2.html`  | Lab Report   | MapReduce in Spark and Spark error handling               |
| `lab3.html`  | Lab Report   | Hashtag and user counting with Spark RDDs                 |
| `lab4.ipynb` | Notebook     | Data integration and change detection                     |
| `lab5.ipynb` | Notebook     | Spark DataFrames, joins, aggregation, and movie reviews   |
| `lab6.html`  | Lab Report   | ALS movie recommendation and hyperparameter tuning        |
| `lab8.html`  | Lab Report   | Decision Tree learning using Spark ML pipelines           |
| `lab9.ipynb` | Notebook     | Fine-tuning T5 for text summarization                     |
| `MP1.html`   | Mini Project | Frequent port-set mining on Darknet scanner data          |
| `MP2.html`   | Mini Project | K-Means clustering using One-Hot Encoded port features    |
| `MP3.html`   | Mini Project | PCA-based dimensionality reduction and K-Means clustering |

## Course Themes

This repository demonstrates work across several major areas of big data analytics:

* Distributed data processing with Apache Spark
* RDD transformations and actions
* MapReduce-style programming
* Spark DataFrame operations
* Data cleaning and preprocessing
* Joins, aggregations, filtering, sorting, and feature engineering
* Spark ML pipelines
* Decision Tree classification
* ALS-based recommendation systems
* K-Means clustering
* One-Hot Encoding for categorical and set-based features
* Principal Component Analysis for dimensionality reduction
* Hyperparameter tuning and model evaluation
* Hugging Face transformer fine-tuning
* Text summarization using T5
* Local mode testing and cluster mode execution

## Labs

### Lab 2: MapReduce in Spark and Understanding Error Messages

**File:** `lab2.html`

Lab 2 introduces the basics of Spark programming using RDDs. The lab focuses on reading text files, parsing input lines into tokens, transforming data into key-value pairs, and using MapReduce-style logic to count word frequencies.

Key concepts covered:

* Creating and using a `SparkContext`
* Reading files into RDDs
* Using `map`, `flatMap`, and `reduceByKey`
* Creating key-value RDDs
* Counting token frequencies
* Using `.take()` to inspect RDD contents
* Understanding Spark lazy evaluation
* Debugging common Spark error messages

This lab establishes the foundation for later assignments that use RDD transformations for larger text and tweet-based datasets.

### Lab 3: Hashtag and User Counting with Spark Submit in Cluster Mode

**File:** `lab3.html`

Lab 3 applies Spark RDD transformations to tweet data related to the Boston Marathon Bombing. The goal is to count hashtags and mentioned users from tweet datasets and then move from local mode development to cluster mode execution.

Key concepts covered:

* Filtering tokens using `filter`
* Sorting results with `sortBy`
* Counting hashtags in tweet data
* Counting mentioned Twitter users
* Using sampled data for local testing
* Preparing code for Spark cluster execution
* Exporting notebook logic into `.py` files
* Saving output files from RDD computations

This lab builds on Lab 2 by applying MapReduce-style counting to a more realistic social media dataset.

### Lab 4: Data Integration and Change Detection

**File:** `lab4.ipynb`

Lab 4 focuses on integrating data from multiple sources and detecting temporal changes. The dataset involves Boston Marathon Bombing tweets from different dates, specifically comparing hashtag counts across April 17 and April 19.

Key concepts covered:

* Loading multiple tweet datasets
* Computing hashtag counts for two different days
* Joining RDDs using outer joins
* Handling missing values created by joins
* Replacing `None` values with zero
* Computing count differences across time
* Sorting hashtags by change in frequency
* Saving results for local and cluster mode output

This lab demonstrates how Spark can be used not only for counting, but also for comparing time-based changes in large datasets.

### Lab 5: DataFrames, Aggregation, and Top Movie Reviews

**File:** `lab5.ipynb`

Lab 5 transitions from RDD-based programming to Spark DataFrames. It uses movie and rating datasets to demonstrate tabular data processing, filtering, joining, grouping, and aggregation.

Key concepts covered:

* Creating a `SparkSession`
* Defining schemas with `StructType` and `StructField`
* Reading CSV data into Spark DataFrames
* Selecting columns
* Filtering rows with DataFrame operations
* Creating new columns using `withColumn`
* Splitting genre strings into arrays
* Using `array_contains`
* Grouping data with `groupBy`
* Computing counts, sums, and averages
* Joining movie metadata with rating data
* Identifying highly rated movies within specific genres
* Saving DataFrame output as CSV

This lab shows how Spark DataFrames provide a higher-level and more structured way to work with big data compared to raw RDDs.

### Lab 6: Movie Recommendations Using ALS and Hyperparameter Tuning

**File:** `lab6.html`

Lab 6 introduces recommendation systems using Alternating Least Squares, or ALS. The lab uses user-movie rating data to train and evaluate a collaborative filtering model.

Key concepts covered:

* Building a recommendation model with ALS
* Splitting data into training, validation, and testing sets
* Training recommendation models with Spark MLlib
* Computing training, validation, and testing error
* Tuning ALS hyperparameters
* Comparing model performance
* Using Pandas DataFrames to store evaluation results
* Selecting the best hyperparameter combination
* Using checkpointing to improve iterative Spark processing

This lab demonstrates how Spark can be used for scalable recommendation systems and model selection.

### Lab 8: Decision Tree Learning Using Spark ML Pipeline

**File:** `lab8.html`

Lab 8 focuses on supervised machine learning using Decision Trees and Spark ML pipelines. The dataset used in this lab is a Breast Cancer diagnosis dataset.

Key concepts covered:

* Creating a Spark ML pipeline
* Preparing features for machine learning
* Using `VectorAssembler`
* Training a `DecisionTreeClassifier`
* Evaluating classification performance
* Computing metrics such as F1 score
* Visualizing decision trees
* Performing automated hyperparameter tuning
* Selecting the best Decision Tree model
* Saving model evaluation and hyperparameter outputs

This lab demonstrates the full machine learning workflow in Spark, from preprocessing to model training, evaluation, visualization, and tuning.

### Lab 9: Fine-Tuning T5 for Text Summarization

**File:** `lab9.ipynb`

Lab 9 introduces transformer-based natural language processing by fine-tuning a pretrained T5 model for text summarization. The lab uses the CNN/Daily Mail news summarization dataset and evaluates the model using ROUGE scores.

Key concepts covered:

* Accessing pretrained models from Hugging Face
* Using Google Colab with GPU acceleration
* Loading CNN/Daily Mail summarization data
* Cleaning and deduplicating training, validation, and test data
* Tokenizing articles and summaries
* Applying truncation and padding
* Fine-tuning an encoder-decoder transformer model
* Using `Seq2SeqTrainer`
* Evaluating summarization quality with ROUGE
* Saving the fine-tuned model and tokenizer
* Testing the model on unseen articles
* Generating summaries for recent news articles

Security note: Hugging Face tokens should never be hardcoded or printed in notebook outputs. Tokens should be stored using Google Colab Secrets or environment variables.

## Mini Projects

### Mini Project 1: Frequent Port-Set Mining on Darknet Data

**File:** `MP1.html`

Mini Project 1 focuses on mining frequent port sets from Darknet scanner data. The goal is to identify commonly scanned ports and port combinations using an adapted Apriori-style approach.

Key concepts covered:

* Working with Darknet scanner profile data
* Identifying frequent 1-port sets
* Identifying frequent 2-port sets
* Identifying frequent 3-port sets
* Applying support thresholds
* Using pruning strategies inspired by the Apriori algorithm
* Reusing RDDs efficiently with `persist` and `unpersist`
* Running analysis on small sampled data locally
* Scaling the solution to a larger Darknet dataset in cluster mode
* Saving frequent port-set outputs

This project applies distributed data mining concepts to cybersecurity-related network scanning data.

### Mini Project 2: K-Means Clustering with One-Hot Encoded Port Features

**File:** `MP2.html`

Mini Project 2 clusters Darknet scanners based on the ports they scanned. The project uses One-Hot Encoding to represent scanned ports as binary features, then applies K-Means clustering.

Key concepts covered:

* Representing scanned ports as binary One-Hot Encoded features
* Identifying top ports for feature construction
* Building feature vectors for scanner behavior
* Applying K-Means clustering
* Interpreting cluster centers
* Evaluating clusters using Silhouette score
* Comparing clusters with Mirai labels
* Running clustering in local mode and cluster mode
* Using `persist` and `unpersist` for performance
* Exporting cluster summaries and scanner count outputs

This project demonstrates unsupervised learning on high-dimensional cybersecurity data.

### Mini Project 3: PCA and K-Means Clustering

**File:** `MP3.html`

Mini Project 3 extends the clustering work from Mini Project 2 by adding dimensionality reduction with Principal Component Analysis. The project compares K-Means clustering with and without PCA.

Key concepts covered:

* Working with 130 top scanned port features
* Reducing high-dimensional One-Hot Encoded features using PCA
* Reducing features to 35 principal components
* Running K-Means clustering without PCA
* Running K-Means clustering with PCA
* Comparing clustering results using Silhouette score
* Comparing clusters using Mirai external labels
* Interpreting cluster centers in the original feature space
* Running experiments in local mode and cluster mode
* Comparing scalability and performance with and without dimensionality reduction

This project demonstrates how dimensionality reduction can make machine learning more efficient and interpretable for large high-dimensional datasets.

## Technologies Used

* Python
* Apache Spark
* PySpark
* Spark RDDs
* Spark DataFrames
* Spark SQL functions
* Spark MLlib
* Spark ML pipelines
* Pandas
* NumPy
* Jupyter Notebook
* Google Colab
* Hugging Face Transformers
* Hugging Face Datasets
* ROUGE evaluation
* K-Means clustering
* ALS recommendation models
* Decision Tree classification
* Principal Component Analysis

## How to View the Files

### HTML Reports

The `.html` files can be opened directly in a browser.

Example on macOS:

```bash
open lab2.html
open MP1.html
```

### Jupyter Notebooks

The `.ipynb` files can be opened using Jupyter Notebook, JupyterLab, VS Code, or Google Colab.

Example:

```bash
jupyter notebook lab4.ipynb
```

or:

```bash
jupyter lab lab5.ipynb
```

## How to Run the Repository Locally

Clone the repository:

```bash
git clone https://github.com/arrysoni/big_data.git
cd big_data
```

Install common Python dependencies:

```bash
pip install pandas numpy matplotlib jupyter
```

For Spark-based notebooks, PySpark is also required:

```bash
pip install pyspark
```

Then start Jupyter:

```bash
jupyter notebook
```

Some labs were designed to run in Penn State ICDS or Roar computing environments, so file paths may need to be updated before running locally.

## Notes on Data and Execution

Some notebooks and reports depend on datasets that were provided through the course environment or Canvas. These datasets may not be included in this repository.

If rerunning the notebooks:

1. Update file paths to match your local machine or cluster environment.
2. Make sure required datasets are available.
3. Run cells in order.
4. For Spark notebooks, ensure only one active `SparkContext` or `SparkSession` is running when required.
5. For cluster mode assignments, local-mode notebook code may need small changes before submission as a `.py` file.

## Security Notes

This repository should not contain API keys, access tokens, passwords, or private credentials.

Before committing Jupyter notebooks, clear notebook outputs:

```bash
jupyter nbconvert --clear-output --inplace lab9.ipynb
```

If using Hugging Face, store tokens securely using:

* Google Colab Secrets
* Environment variables
* A local `.env` file that is excluded from Git

Never hardcode tokens directly in notebooks or print them as cell output.

## Academic Integrity

This repository is intended to document my own coursework, learning progress, and technical work for CMPSC 410. It is shared for portfolio and reference purposes only.

Please do not copy or submit this work as your own academic assignment.

## Author

**Aarya Soni**
CMPSC 410: Big Data Programming and Analytics
Penn State University
