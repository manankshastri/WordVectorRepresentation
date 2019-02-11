# Operations on word vectors

<div>
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
<p align='center'>Figure 1 : The cosine of the angle between two vectors is a measure of how similar they are.</p>

  <h2>2 - Word analogy task </h2>

In the word analogy task, we complete the sentence "<b>a is to b as c is to ____</b>". An example is '<b>man is to woman as king is to queen'</b>. In detail, we are trying to find a word *d*, such that the associated word vectors are related. We will measure the similarity between <b>e_b - e_a</b> and <b>e_d - e_c</b> using cosine similarity.
</div>



