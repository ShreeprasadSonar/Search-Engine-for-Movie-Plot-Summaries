# Search-Engine-for-Movie-Plot-Summaries
Movie Plot Summary Search Engine using TF-IDF and Cosine Similarity
# Movie Plot Summary Search Engine using TF-IDF and Cosine Similarity

This project focuses on building a search engine for movie plot summaries using the tf-idf technique implemented in Scala/PySpark on a Databricks cluster. The dataset utilized is available from the [Carnegie Movie Summary Corpus](http://www.cs.cmu.edu/~ark/personas/data/MovieSummaries.tar.gz) site.

## Project Overview

The objective is to create a search engine that performs the following tasks:

1. **Data Preparation:**
   - Extract and upload the file `plot summaries.txt` from the provided link to Databricks.
   - Upload a file containing user-generated search terms, one term per line.

2. **Data Processing:**
   - Removal of stopwords using a chosen method.
   - Creation of tf-idf values for each term and document (represented by Wikipedia movie ID) using MapReduce.

3. **Search Functionality:**
   - For single term queries, display the top 10 documents with the highest tf-idf values.
   - For multi-term queries, compute cosine similarity between the query and all documents and return the top 10 documents with the highest cosine similarity values.

4. **Output:**
   - Return a list of movie names sorted by their relevance values (in descending order) based on the search terms entered by the user.
   - Utilize the `movie.metadata.tsv` file to lookup and return movie names (not movie IDs).

5. **Display Output:**
   - Display the output of the program on the screen.

## Resources and References

For more details about tf-idf, MapReduce implementation, cosine similarity, and relevant techniques used in this project, refer to the following resources:

- Good introduction from Coursera Distributed Programming course
- Chapter 4 of the reference book Data-Intensive Text Processing using MapReduce
- [Text2Vec - Cosine Similarity](http://text2vec.org/similarity.html)
- [TF-IDF and Cosine Similarity Explanation](https://janav.wordpress.com/2013/10/27/tf-idf-and-cosine-similarity/)
- [Lecture on Information Retrieval - Cosine Similarity](https://courses.cs.washington.edu/courses/cse573/12sp/lectures/17-ir.pdf)

## Repository Contents

- `notebook.ipynb`: Jupyter notebook containing the Scala/PySpark code for the search engine implementation.
- `plot_summaries.txt`: Dataset file containing movie plot summaries.
- `user_search_terms.txt`: File containing user-generated search terms.

## Usage

1. Upload `plot_summaries.txt` and `user_search_terms.txt` to a Databricks cluster.
2. Execute the code provided in `notebook.ipynb` on the Databricks environment.
3. Input single or multiple search terms as per the specified functionality to retrieve relevant movie names.