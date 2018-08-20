# qasolver

Updating the QA system for [Stanford Question Answering Datatset 2.0](https://rajpurkar.github.io/SQuAD-explorer/) initially made by Alvina Swalin for the first version of SQUAD on GitHub. She details her thoughts [in her article on towardsdatascience](https://towardsdatascience.com/building-a-question-answering-system-part-1-9388aadff507)

 - The first file create_emb.ipynb takes care of creating a dictionary of sentence embedding for all the sentences and questions in the wikipedia articles of training dataset

 - The second file unsupervised.ipynb calculates the distance between sentence & questions basis Euclidean & Cosine similarity using sentence embeddings. It finally extracts the setence from each paragraph that has the minimum distance from the question. Currently, they are giving an accuracy of 32.0% & 42.5% respectively.

 - The last file treats this problem as a supervised learning problem where I am fitting multinomial logistic regression, random forest and xgboost and create twenty features - (two features represents the cosine distance & euclidean for one sentence. I am limiting each paragraphs to ten sentences). The target variable is the sentence ID having the correct answer. So I have ten labels. This is currently giving an accuracy of 29.0%, 45.0% & 45.0% respectively.

Future Work: Use RNNs to get the exact answer
