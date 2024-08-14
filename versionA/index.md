
# Introduction
Pretraining on large-scale noisy data followed by fine-tuning on the target domain has proven highly successful in numerous tasks. In light of this, our objective is to construct a cutting-edge large language model for symbolic music by leveraging the extensive symbolic music dataset available from the MuseScore forum.

# Content

1. Model Summary
2. Best examples
3. Examples in Unconditioned Generation
4. Examples in Music Generation Conditioned on "Genre"
5. Examples in Music Generation Conditioned on "Instrument"
6. Examples in Music Generation Conditioned on "Genre" and "Instrument"


---
## Model Summary:
The resolution we set is 12. The max sequence length is 1024. 
<div class="table-wrapper" markdown="block">

| Model | Tag Control | Instrument Control | Total Number of Parameters | Number of Training Sample |
|-|:-:|:-:|:-:|:-:|
| Unconditioned/Pretrained | ✕ | ✕ | 87.15K | 1.3M |
| Genre Conditioned | __✓__  | ✕ | 87.18K | 158K |
| Instrument Conditioned | ✕ | __✓__ | 87.27K | 739K |
| Genre-Instrument Conditioned | __✓__ | __✓__ | 87.28K  | 158K |

</div>


__1. Single Track:__ {% include audio_player.html filename="genre_cond/0_genre_conditioned.mp3" %} 

