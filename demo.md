__Leverage Large Language Model on Conditional Music Generation__
{:.center .larger}

## Introduction
Pretraining on large-scale noisy data followed by fine-tuning on the target domain has proven highly successful in numerous tasks. In light of this, our objective is to construct a cutting-edge model for symbolic music by leveraging the extensive symbolic music dataset available from the MuseScore forum.

## Content

1. Summary of the compared models
2. Examples in Music Generation Conditioned on "Program"
3. Examples in Music Generation Conditioned on "Genre" and "Program"
4. Examples in Unconditioned Generation

### Summary of the Compared Models:
The resolution we set is 12. The max sequence length is 1024. 
<div class="table-wrapper" markdown="block">

| Model | Tag Control | Program Control | Total Number of Parameters | Number of Training Sample |
|-|:-:|:-:|:-:|:-:|
| Genre_Informed | __✓__ | ✕ | 87,180,084 | 157,641 |
| Program_Informed | ✕  | __✓__ | 87,274,605| 738,815 |
| Genre_Program_Informed | __✓__ | __✓__ |87,281,526| 157,641 |
| Unconditioned | ✕ | ✕ | 87,281,526  | 157,641 |
</div>

### Genre-informed generation samples 

> __Settings__: The model is provided with a structured music data format, starting with a 'start-of-song' event, followed by a 'start-of-tags' marker. The 'start-of-tags' marker is followed by genre tags that describe the music. Finally, the 'start-of-notes' marker indicates the commencement of a sequence of instrument codes, representing musical notes and instrument selections
<div class="table-wrapper" markdown="block">

| __Ensemble__: piano, church-organ, voices | {% include audio_player.html filename="audio/genre_cond/0_genre_conditioned.mp3" %} |
| __Ensemble__: contrabass, harp, english-horn, flute | {% include audio_player.html filename="audio/genre_cond/1_genre_conditioned.mp3" %} |
| __Ensemble__: trumpet, trombone | {% include audio_player.html filename="audio/genre_cond/2_genre_conditioned.mp3" %} |
| __Ensemble__: church-organ, viola, contrabass, strings, voices, horn, oboe | {% include audio_player.html filename="audio/genre_cond/3_genre_conditioned.mp3" %} |
| __Ensemble__: church-organ, viola, contrabass, strings, voices, horn, oboe | {% include audio_player.html filename="audio/genre_cond/4_genre_conditioned.mp3" %} |



</div>

### Program-informed generation samples

> __Settings__: The model is provided with a structured music data format, starting with a 'start-of-song' event, followed by a 'start-of-program' marker. The 'start-of-program' marker is followed by programs that are used in the music. Finally, the 'start-of-notes' marker indicates the commencement of a sequence of instrument codes, representing musical notes and instrument selections

<div class="table-wrapper" markdown="block">k

| __Ensemble__: piano, church-organ, voices | {% include audio_player.html filename="audio/program_cond/0_instrument_conditioned.mp3" %} |
| __Ensemble__: piano, church-organ, voices | {% include audio_player.html filename="audio/program_cond/1_instrument_conditioned.mp3" %} |
| __Ensemble__: piano, church-organ, voices | {% include audio_player.html filename="audio/program_cond/2_instrument_conditioned.mp3" %} |
| __Ensemble__: piano, church-organ, voices | {% include audio_player.html filename="audio/program_cond/3_instrument_conditioned.mp3" %} |
| __Ensemble__: piano, church-organ, voices | {% include audio_player.html filename="audio/program_cond/4_instrument_conditioned.mp3" %} |

</div>

### Program-genre-informed generation samples

> __Settings__: In this context, there exist five distinctive data event types: 'start-of-song,' 'start-of-program,' 'start-of-tags,' 'start-of-notes,' and 'end-of-song.' The 'start-of-program' event serves as an indicator for the initiation of a program list, while the 'start-of-tags' event marks the commencement of a tag list. Meanwhile, the 'start-of-notes' event signifies the outset of a sequence of music notes.

<div class="table-wrapper" markdown="block">

| __Ensemble__: piano, church-organ, voices | {% include audio_player.html filename="audio/genre_program_cond/0_both_conditioned.mp3" %} |
| __Ensemble__: piano, church-organ, voices | {% include audio_player.html filename="audio/genre_program_cond/1_both_conditioned.mp3" %} |
| __Ensemble__: piano, church-organ, voices | {% include audio_player.html filename="audio/genre_program_cond/2_both_conditioned.mp3" %} |
| __Ensemble__: piano, church-organ, voices | {% include audio_player.html filename="audio/genre_program_cond/3_both_conditioned.mp3" %} |
| __Ensemble__: piano, church-organ, voices | {% include audio_player.html filename="audio/genre_program_cond/4_both_conditioned.mp3" %} |

</div>

---

## Unconditioned generation 

> __Settings__: Only a `start-of-song' event is provided to the model. The model generates the instrument list and subsequently the note sequence.

<div class="table-wrapper" markdown="block">
| {% include audio_player.html filename="audio/uncond/0_unconditioned.mp3" style="width:240px;" %} | {% include audio_player.html filename="audio/uncond/1_unconditioned.mp3" style="width:240px;" %} | {% include audio_player.html filename="audio/uncond/2_unconditioned.mp3" style="width:240px;" %} | {% include audio_player.html filename="audio/uncond/3_unconditioned.mp3" style="width:240px;" %} | | {% include audio_player.html filename="audio/uncond/4_unconditioned.mp3" style="width:240px;" %} |

</div>

---


