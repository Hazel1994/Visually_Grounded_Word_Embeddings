## Learning Zero-Shot Multifaceted Visually Grounded Word Embeddings via Multi-Task Training
Click [here](https://huggingface.co/datasets/fittar/visually_grounded_embeddings) to download the grounded word embeddings described in our paper: https://aclanthology.org/2021.conll-1.12/

## usage example
The embeddings are in gensim format
```python
import gensim

model_g = gensim.models.KeyedVectors.load_word2vec_format('path_to_embeddings' , binary=True)

#retrieve the most similar words
print(model_g.most_similar('together',topn=10))

[('togther', 0.6425853967666626), ('togehter', 0.6374243497848511), ('togeather', 0.6196791529655457),
('togather', 0.5998020172119141), ('togheter', 0.5819681882858276),('toghether', 0.5738174319267273), 
('2gether', 0.5187329053878784), ('togethor', 0.501663088798523), ('gether', 0.49128714203834534), 
('toegther', 0.48457157611846924)]

print(model_g.most_similar('sad',topn=10))

[('saddening', 0.6763913631439209), ('depressing', 0.6676110029220581), ('saddened', 0.6352651715278625),
('sorrowful', 0.6336953043937683), ('heartbreaking', 0.6180269122123718), ('heartbroken', 0.6099187135696411),
('tragic', 0.6039361953735352), ('pathetic', 0.5848405361175537), ('Sad', 0.5826965570449829),
('mournful', 0.5742306709289551)]

#find the outlier word
print(model_g.doesnt_match(['fire', 'water', 'land', 'sea', 'air', 'car']))

car

```
## Citation
if you find our embeddings useful, please cite our paper:
```
@inproceedings{shahmohammadi-etal-2021-learning,
    title = "Learning Zero-Shot Multifaceted Visually Grounded Word Embeddings via Multi-Task Training",
    author = "Shahmohammadi, Hassan  and
      Lensch, Hendrik P. A.  and
      Baayen, R. Harald",
    booktitle = "Proceedings of the 25th Conference on Computational Natural Language Learning",
    month = nov,
    year = "2021",
    address = "Online",
    publisher = "Association for Computational Linguistics",
    url = "https://aclanthology.org/2021.conll-1.12",
    doi = "10.18653/v1/2021.conll-1.12",
    pages = "158--170"
}
```
## Interested in visually grounded embeddings?
We have also another version of visually grounded embeddings which seems to perform even better. Feel free to [check it out](https://github.com/Hazel1994/Visually_Grounded_Word_Embeddings_2)
