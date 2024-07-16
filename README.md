In order to run the script that is available there are some pre requisite tasks they are as follows:
1.	Load the IPYNB file properly in jupyter or Google Colab. 
2.	Upload all the required documents/research papers into a single folder in Google drive. 
3.	Mount the Google drive to jupyter notebook.
4.	Replace the path of folder mentioned in the third block of code which is used to extract the abstract from research papers.
5.	Also replace the path for creating folders in the last block of cell.
6. 	Should have installed Numpy, Pandas, Matplotlib before running the script.
7.	All other libraries that were used in the script will be installed automatically while running the code.
   
Working Process of the code:
1.	 This code takes the path of the research paper (path means the place where the file is stored in google drive) and reads all the text present in the research paper using PDFminer and stores it in a temporary variable.
2.	This temporary variable is then subjected to various filters to result only the abstract part to stay and remove all other parts of the research paper.
3.	The processed abstract is then processed to vectorization by the use of TF-IDF vectorizer and all the stop words are removed in this process.
4.	The resulting Dataset is then used to train our model.
5.	The Models that were used in this process are KMeans classifier, DBscan.
6.	These models are then subjected to Evaluation through Elbow Method and silhouette analysis and graphs are produced and through which Optimal No. of Clusters is determined to be 7.
7.	By Visualizing the graphs that were created using PCA we can conclude that the classification is up to the mark.
8.	The Files that were given at the start are then classified based on the model that was created and the files area sent to appropriate folders.
   
Why this Process:
1.	Pdfminer was used in the script instead of pypdf2 since pypdf2 extracts text line by line which leads to incorrect text extraction when the pdf is in double column format. Pdfminer extracts text block by block from which we can take the abstract block using some filters.
2.	Both the word Embedding and TF-IDF vectorization method were used and From the graph that was obtained by using PCA, it was decided that the TF-IDF vectorization technique has yielded better results.
The graphs that were obtained are as follows:
   
Based on these graphs we can say that in TF-IDF dataset the clusters are well spread and can easily be separated.
3.	In Text data the features(words) are mostly independent on each other and we want only their variance over the data so Choosing PCA over t-SNE for dimensionality reduction is better.
4.	Also in PCA, the no. of components is set to be 2 to visualize the spread of the clusters in a 2D plane. We can also try going for 3 components or more.
5.	The Kmeans classifier is tested over 1-10 no. of clusters, max limit is set to 10 because the dataset consists of 50 datapoints and clustering them into more than 10 clusters isn’t that appropriate.
6.	So the tests were conducted by Elbow Method and Silhouette Analysis and the results are as follows:
    

There are so curves at 3 and 7 in the line but haven’t seen a sharp curve 
   
We can clearly see that there is a peak ponit at 7, i.e, optimal no. of clusters will be 7.
 
7.	Finally we can say that the Optimal no. of clusters is 7 and the best classifier for our research paper classification is KMeans classifier.

