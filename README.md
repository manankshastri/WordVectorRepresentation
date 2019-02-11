# Operations on word vectors

<div>
  <p> - Load pre-trained word vectors, and measure similarity using cosine similarity. </p>
  <p> - Use word embeddings to solve word analogy problems such as Man is to Woman as King is to ______. </p>
  <p> - Modify word embeddings to reduce their gender bias </p>
</div>
<hr>
<div>
  <p>We will use <a href="http://nlp.stanford.edu/data/glove.6B.zip">50-dimensional GloVe vectors</a> to represent words.</p>
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

  <h2>3 - Debiasing word vectors</h2>

We will examine gender biases that can be reflected in a word embedding, and explore algorithms for reducing the bias. 

  <h3>3.1 - Neutralize bias for non-gender specific words </h3>
  
The figure below should help you visualize what neutralizing does. If you're using a 50-dimensional word embedding, the 50 dimensional space can be split into two parts: The bias-direction <b>g</b>, and the remaining 49 dimensions, which we'll call <b>g&perp;</b>.

<img src="images/neutral.png" style="width:800px;height:300px;">
<p align='center'>Figure 2: The word vector for "receptionist" represented before and after applying the neutralize operation.</p>

  <h3>3.2 - Equalization algorithm for gender-specific words</h3>

Next, lets see how debiasing can also be applied to word pairs such as "actress" and "actor." Equalization is applied to pairs of words that you might want to have differ only through the gender property. As a concrete example, suppose that "actress" is closer to "babysit" than "actor." By applying neutralizing to "babysit" we can reduce the gender-stereotype associated with babysitting. But this still does not guarantee that "actor" and "actress" are equidistant from "babysit." The equalization algorithm takes care of this. 

The key idea behind equalization is to make sure that a particular pair of words are equi-distant from the 49-dimensional <b>g&perp;</b>. The equalization step also ensures that the two equalized steps are now the same distance from <b>e<sub>receptionist</sub><sup>debiased</sup></b>, or from any other work that has been neutralized. In pictures, this is how equalization works: 

<img src="images/equalize10.png" style="width:800px;height:400px;">
</div>
<hr>
<h2>References:</h2>
<p>The debiasing algorithm is from Bolukbasi et al., 2016, <a href = "https://papers.nips.cc/paper/6228-man-is-to-computer-programmer-as-woman-is-to-homemaker-debiasing-word-embeddings.pdf"> Man is to Computer Programmer as Woman is to Homemaker? Debiasing Word Embeddings</a></p>
<p>The <a href="https://nlp.stanford.edu/projects/glove/">GloVe word embeddings</a> were due to Jeffrey Pennington, Richard Socher, and Christopher D. Manning.</p>



  
