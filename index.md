
## Introduction
Pretraining on large-scale noisy data followed by fine-tuning on the target domain has proven highly successful in numerous tasks. In light of this, our objective is to construct a cutting-edge large language model for symbolic music by leveraging the extensive symbolic music dataset available from the MuseScore forum.

## Content

1. Summary of the compared models
2. Best examples
3. Examples in Unconditioned Generation
4. Examples in Music Generation Conditioned on "Genre"
5. Examples in Music Generation Conditioned on "Instrument"
6. Examples in Music Generation Conditioned on "Genre" and "Instrument"


---
### Summary of the Compared Models:
The resolution we set is 12. The max sequence length is 1024. 
<div class="table-wrapper" markdown="block">

| Model | Tag Control | Instrument Control | Total Number of Parameters | Number of Training Sample |
|-|:-:|:-:|:-:|:-:|
| Unconditioned | ✕ | ✕ | 87.15K | 739K |
| Genre Conditioned | __✓__  | ✕ | 87.18K | 158K |
| Instrument Conditioned | ✕ | __✓__ | 87.27K | 739K |
| Genre-Instrument Conditioned | __✓__ | __✓__ | 87.28K  | 158K |
</div>



---
### Best Examples 

> Here we introduce some great examples generated in our model. We are giving one single-track example and one multi-track example for each condition
<div class="table-wrapper" markdown="block">

#### Unconditioned Generation
|__Single Track:__ |{% include audio_player.html filename="audio/uncondition_best/0_unconditioned.mp3" %} |

|__MultiTrack:__ |{% include audio_player.html filename="audio/uncondition_best/1_unconditioned.mp3" %} |

#### Genre Conditioned Generation
|__Single Track:__  | __Ensemble:__ | {% include audio_player.html filename="audio/uncondition_best/0_unconditioned.mp3" %} |

|__MultiTrack:__ | __Ensemble:__ | {% include audio_player.html filename="audio/uncondition_best/1_unconditioned.mp3" %} |

#### Instrument Conditioned Generation
|__Single Track:__ | __Ensemble:__ | {% include audio_player.html filename="audio/uncondition_best/0_unconditioned.mp3" %} |

|__MultiTrack:__ | __Ensemble:__ | {% include audio_player.html filename="audio/uncondition_best/1_unconditioned.mp3" %} |

#### Genre-Instrument Conditioned Generation
|__Single Track:__ | __Ensemble:__ | {% include audio_player.html filename="audio/uncondition_best/0_unconditioned.mp3" %} |

|__MultiTrack:__ | __Ensemble:__ | {% include audio_player.html filename="audio/uncondition_best/1_unconditioned.mp3" %} |

</div>

---
### Unconditioned Generation

> __Settings__: Only a `start-of-song' event is provided to the model. The model generates the instrument list and subsequently the note sequence.
<div class="table-wrapper" markdown="block">

|{% include audio_player.html filename="audio/uncond/0_new_unconditioned.mp3" style="width:240px;" %} | 
| {% include audio_player.html filename="audio/uncond/1_new_unconditioned.mp3" style="width:240px;" %} | 
| {% include audio_player.html filename="audio/uncond/2_unconditioned.mp3" style="width:240px;" %} | 
| {% include audio_player.html filename="audio/uncond/3_unconditioned.mp3" style="width:240px;" %} | 
| {% include audio_player.html filename="audio/uncond/4_unconditioned.mp3" style="width:240px;" %} |

</div>

---

### Genre Conditioned Generation

> __Settings__: The model is provided with a structured music data format, starting with a 'start-of-song' event, followed by a 'start-of-tags' marker. The 'start-of-tags' marker is followed by genre that is used in the music. Finally, the 'start-of-notes' marker indicates the commencement of a sequence of instrument codes, representing musical notes and instrument selections

<div class="table-wrapper" markdown="block">

| __Genre__: classical | {% include audio_player.html filename="audio/genre_cond/0_genre_conditioned.mp3" %} |
| __Genre__: religious music | {% include audio_player.html filename="audio/genre_cond/1_genre_conditioned.mp3" %} |
| __Genre__: soundtrack | {% include audio_player.html filename="audio/genre_cond/2_genre_conditioned.mp3" %} |
| __Genre__: folk | {% include audio_player.html filename="audio/genre_cond/3_genre_conditioned.mp3" %} |
| __Genre__: worldmusic | {% include audio_player.html filename="audio/genre_cond/4_genre_conditioned.mp3" %} |


---
</div>

### Instrument Conditioned Generation

> __Settings__: The model is provided with a structured music data format, starting with a 'start-of-song' event, followed by a 'start-of-program' marker. The 'start-of-program' marker is followed by programs that are used in the music. Finally, the 'start-of-notes' marker indicates the commencement of a sequence of instrument codes, representing musical notes and instrument selections

<div class="table-wrapper" markdown="block">

| __Instrument__: piano, flute, cello | {% include audio_player.html filename="audio/program_cond/0_instrument_conditioned.mp3" %} |

| __Instrument__: voices, piano| {% include audio_player.html filename="audio/program_cond/2_instrument_conditioned.mp3" %} |

| __Instrument__: piano, trumpet, harmonica, guitar, bass and violin| {% include audio_player.html filename="audio/program_cond/47_unconditioned.mp3" %} |

| __Instrument__: recorder | {% include audio_player.html filename="audio/program_cond/4_instrument_conditioned.mp3" %} |

| __Instrument__: church-organ, trombone, tuba, horn | {% include audio_player.html filename="audio/program_cond/10_unconditioned.mp3" %} |

</div>

---

### Genre-Instrument Conditioned Generation

> __Settings__: In this context, there exist five distinctive data event types: 'start-of-song,' 'start-of-program,' 'start-of-tags,' 'start-of-notes,' and 'end-of-song.' The 'start-of-program' event serves as an indicator for the initiation of a program list, while the 'start-of-tags' event marks the commencement of a tag list. Meanwhile, the 'start-of-notes' event signifies the outset of a sequence of music notes.


<div class="table-wrapper" markdown="block">

4A | __Instrument__:Voice, __Genre__: Classical | {% include audio_player.html filename="audio/genre_program_cond/0_both_conditioned.mp3" %} |
4B | __Instrument__:Classical String Guitar, __Genre__: Classical | {% include audio_player.html filename="audio/genre_program_cond/1_both_conditioned.mp3" %} |
4C | __Instrument__:Piano, __Genre__: Classical | {% include audio_player.html filename="audio/genre_program_cond/3_both_conditioned.mp3" %} |
4D | __Instrument__:Organ, Guitar, Lead, Pad, Strings, Drum __Genre__: Hip Hop | {% include audio_player.html filename="audio/genre_program_cond/2_both_conditioned.mp3" %} |
4E | __Instrument__:Vibraphone, Piano, Flute, String-guitar, __Genre__: Pop | {% include audio_player.html filename="audio/genre_program_cond/4_both_conditioned.mp3" %} |

</div>

---