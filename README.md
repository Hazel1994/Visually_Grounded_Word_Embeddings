## Learning Zero-Shot Multifaceted Visually Grounded Word Embeddings via Multi-Task Training
Click [here](https://unitc-my.sharepoint.com/:f:/g/personal/iighs01_cloud_uni-tuebingen_de/EkHWjuQFBAZKuX5L2Lcg87wByGrYT5okxTVqptdVJnnPaA?e=mGDSro) to download the grounded word embeddings described in our paper: https://arxiv.org/abs/2104.07500

##usage example
The embeddings are in gensim format
```python
import gensim

model_g = gensim.models.KeyedVectors.load_word2vec_format('path_to_embeddings' , binary=True)

#retrieve the most similar words
print(model_g.most_similar('together',topn=10))

[('togther', 0.6425853967666626), ('togehter', 0.6374243497848511), ('togeather', 0.6196791529655457), ('togather', 0.5998020172119141), ('togheter', 0.5819681882858276), ('toghether', 0.5738174319267273), ('2gether', 0.5187329053878784), ('togethor', 0.501663088798523), ('gether', 0.49128714203834534), ('toegther', 0.48457157611846924)]

#find the outlier word
print(model_g.doesnt_match(['fire', 'water', 'land', 'sea', 'air', 'car']))

car

```

