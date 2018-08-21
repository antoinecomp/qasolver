<h1 align="center">qasolver</h1> 
<div align="center">
  <strong>QA system for text understanding</strong>
</div>

<div align="center">
  <!-- Stability -->
  <a href="https://img.shields.io/badge/python-3.5.2-yellow.svg">
    <img src="https://img.shields.io/badge/python-3.5.2-yellow.svg"
      alt="Python 3.5.2" />
  </a>  <a href="https://img.shields.io/badge/contributions-welcome-orange.svg">
    <img src="https://img.shields.io/badge/contributions-welcome-orange.svg"
      alt="Contributions welcome" />
  </a>
  <a href="https://github.com/antoinecomp/qasolver/issues">
    <img src="https://img.shields.io/github/issues/antoinecomp/drqa.svg"
      alt="Issues" />
  </a>
</div>
<div align="center">
  <h3>
	Come discuss with us 
    <a href="https://www.reddit.com/r/Moodbot/">
      @Reddit
    </a>
  </h3>
</div>


Updating the QA system for [Stanford Question Answering Datatset 2.0](https://rajpurkar.github.io/SQuAD-explorer/) initially made by Alvina Swalin for the first version of SQUAD. You can find [her attempt on GitHub](https://github.com/aswalin/SQuAD). She details her thoughts [in her article on towardsdatascience](https://towardsdatascience.com/building-a-question-answering-system-part-1-9388aadff507).

 - The first file create_emb.ipynb takes care of creating a dictionary of sentence embedding for all the sentences and questions in the wikipedia articles of training dataset

 - The second file unsupervised.ipynb calculates the distance between sentence & questions basis Euclidean & Cosine similarity using sentence embeddings. It finally extracts the setence from each paragraph that has the minimum distance from the question. Currently, they are giving an accuracy of 32.0% & 42.5% respectively.

 - The last file treats this problem as a supervised learning problem where I am fitting multinomial logistic regression, random forest and xgboost and create twenty features - (two features represents the cosine distance & euclidean for one sentence. I am limiting each paragraphs to ten sentences). The target variable is the sentence ID having the correct answer. So I have ten labels. This is currently giving an accuracy of 29.0%, 45.0% & 45.0% respectively.

## To-Do
Future Work: Use RNNs to get the exact answer

## Installation

You need to download the SQUAD datasets that contains the train and dev data. You can find them on [Stanford Question Answering Datatset 2.0](https://rajpurkar.github.io/SQuAD-explorer/). Make sure to place them in the data folder!

You also need to clone [InferSent repository from FaceBook reasearch lab](https://github.com/facebookresearch/InferSent) and know [how to use their sentence encoder](https://github.com/facebookresearch/InferSent#use-our-sentence-encoder)

Finally you need to import the `requirements.txt` file with `pip install -r requirements.txt` you can use a virtual environment, it is my personal recommendation.

Then, you're all set and can launch `jupyter notebook` from the repository. Before hurrying to the unsupervised and supervised methods make sure that you have created your embeddings first!

## Documentation 

If you're a bookworm that needs to read how all of this is done :

 1. Start with [Stanford Question Answering Datatset 2.0 paper](https://arxiv.org/pdf/1806.03822.pdf) about the dataset and the contest they set up.
 2. Follow with [Alvina Swalin's article on towardsdatascience](https://towardsdatascience.com/building-a-question-answering-system-part-1-9388aadff507), where she explains her attempt and her features.
 3. Read my [ongoing Master dissertation on this project](https://www.overleaf.com/read/xgkqdjfswtgz). I tried to formalize the project and the features with solid mathematical definitions of her attempts and their limits in front of this new dataset.

You are welcome to discuss them [on Reddit](https://www.reddit.com/r/Moodbot/), especially the last one ;)
## Support

Feel free to launch an issue above if you're stuck. I will try to help as much as I can.
