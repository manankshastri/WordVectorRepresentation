# Operations on word vectors

<div>
  <p> Objectives: </p>
  <p> - Load pre-trained word vectors, and measure similarity using cosine similarity. </p>
  <p> - Use word embeddings to solve word analogy problems such as Man is to Woman as King is to ______. </p>
  <p> - Modify word embeddings to reduce their gender bias </p>
</div>
<hr>
<div>
  <p>We will use <a href="https://nlp.stanford.edu/projects/glove/">50-dimensional GloVe vectors</a> to represent words.</p>
</div>
<hr>
<div>
  <h2>1 - Cosine similarity</h2>

To measure how similar two words are, we need a way to measure the degree of similarity between two embedding vectors for the two words.

This similarity depends on the angle between <b>u</b> and <b>v</b>. If <b>u</b> and <b>v</b> are very similar, their cosine similarity will be close to 1; if they are dissimilar, the cosine similarity will take a smaller value. 

<img src="images/cosine_sim.png" style="width:800px;height:250px;">
<caption><center> **Figure 1**: The cosine of the angle between two vectors is a measure of how similar they are</center></caption>
</div>
