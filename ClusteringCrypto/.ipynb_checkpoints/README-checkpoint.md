#  Clustering Crypto

![Cryptocurrencies coins](Images/cryptocurrencies-coins.jpg)
_[Cryptocurrencies coins by Worldspectrum](https://www.pexels.com/@worldspectrum?utm_content=attributionCopyText&utm_medium=referral&utm_source=pexels) | [Free License](https://www.pexels.com/photo-license/)_



In this homework assignment, we have the opportunity to put in action  new unsupervised learning and skills to cluster cryptocurrencies and create some plots to present the results.

We are asked to accomplish the following main tasks:

* **[Data Preprocessing](#Data-Preprocessing):** Prepare data for dimension reduction with PCA and clustering using K-Means.

* **[Reducing Data Dimensions Using PCA](#Reducing-Data-Dimensions-Using-PCA):** Reduce data dimension using the `PCA` algorithm from `sklearn`.

* **[Clustering Cryptocurrencies Using K-Means](#Clustering-Cryptocurrencies-Using-K-Means):** Predict clusters using the cryptocurrencies data using the `KMeans` algorithm from `sklearn`.

* **[Visualizing Results](#Visualizing-Results):** Create some plots and data tables to present your results.


---

### Files

* [crypto_clustering.ipynb](crypto_clustering.ipynb)

---

### Instructions

#### Data Preprocessing

In this section, we have to load the information about cryptocurrencies from the provided `CSV` file and perform some data preprocessing tasks. The data was retrieved from  _CryptoCompare_ using this endpoint: `https://min-api.cryptocompare.com/data/all/coinlist`.

We start by loading the data in a Pandas DataFrame named `crypto_df`, and continue with the following data preprocessing tasks by:

3. Removing all cryptocurrencies that are not on trading.

4. Removing all cryptocurrencies that have not an algorithm defined.

5. Removing the `IsTrading` column.

6. Removing all cryptocurrencies with at least one null value.

7. Removeing all cryptocurrencies without coins mined.

9. Then we store the names of all cryptocurrencies on a DataFramed named `coins_name`, we use the `crypto_df.index` as the index for this new DataFrame.

10. Removing the `CoinName` column.

11. We create dummies variables for all the text features, store the resulting data on a DataFrame named `X`.

12. We use the [`StandardScaler` from `sklearn`](https://scikit-learn.org/stable/modules/generated/sklearn.preprocessing.StandardScaler.html) to standardize all the data of the `X` DataFrame. Remember, this is important prior to using PCA and K-Means algorithms.

#### Reducing Data Dimensions Using PCA

Use the [`PCA` algorithm from `sklearn`](https://scikit-learn.org/stable/modules/generated/sklearn.decomposition.PCA.html) to reduce the dimensions of the `X` DataFrame down to three principal components.

Once we have reduced the data dimensions, we create a DataFrame named `pcs_df` using as columns names `"PC 1", "PC 2"` and `"PC 3"`; we  use the `crypto_df.index` as the index for this new DataFrame.


![pcs_df](Images/pcs_df.png)

#### Clustering Cryptocurrencies Using K-Means

In this section, we will use the [`KMeans` algorithm from `sklearn`](https://scikit-learn.org/stable/modules/generated/sklearn.cluster.KMeans.html) to cluster the cryptocurrencies using the PCA data.

We will perform the following tasks:

1. Create an Elbow Curve to find the best value for `k`, 

2. We define the best value for `k` and run the `Kmeans` algorithm to predict the `k` clusters for the cryptocurrencies data. 

3. Create a new DataFrame named 

    ![clustered_df](Images/clustered_df.png)

#### Visualizing Results
