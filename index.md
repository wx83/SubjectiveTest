__Multitrack Music Transformer__
{:.center .larger}

## Content

1. Music Generation Conditioned on "Genre"
2. Music Generation Conditioned on "Program"
3. Music Generation Conditioned on "Genre" and "Program"



## Best samples {#best-samples}

### Best genre-informed generation samples 

> __Settings__: The model is provided with a structured music data format, starting with a 'start-of-song' event, followed by a 'start-of-tags' marker. The 'start-of-tags' marker is followed by genre tags that describe the music. Finally, the 'start-of-notes' marker indicates the commencement of a sequence of instrument codes, representing musical notes and instrument selections
<div class="table-wrapper" markdown="block">

| {% include audio_player.html filename="audio/sod/best/3_unconditioned.mp3" style="width:240px;" %} | {% include audio_player.html filename="audio/sod/best/12_unconditioned.mp3" style="width:240px;" %} | {% include audio_player.html filename="audio/sod/best/16_unconditioned.mp3" style="width:240px;" %} | {% include audio_player.html filename="audio/sod/best/23_unconditioned.mp3" style="width:240px;" %} |
| {% include audio_player.html filename="audio/sod/best/31_unconditioned.mp3" style="width:240px;" %} | {% include audio_player.html filename="audio/sod/best/39_unconditioned.mp3" style="width:240px;" %} | {% include audio_player.html filename="audio/sod/best/43_unconditioned.mp3" style="width:240px;" %} | {% include audio_player.html filename="audio/sod/best/45_unconditioned.mp3" style="width:240px;" %} |

</div>

### Best program-informed generation samples

> __Settings__: The model is provided with a structured music data format, starting with a 'start-of-song' event, followed by a 'start-of-program' marker. The 'start-of-program' marker is followed by programs that are used in the music. Finally, the 'start-of-notes' marker indicates the commencement of a sequence of instrument codes, representing musical notes and instrument selections

<div class="table-wrapper" markdown="block">k

| __Ensemble__: piano, church-organ, voices | {% include audio_player.html filename="audio/sod/best/7_instrument-informed.mp3" %} |
| __Ensemble__: contrabass, harp, english-horn, flute | {% include audio_player.html filename="audio/sod/best/40_instrument-informed.mp3" %} |
| __Ensemble__: trumpet, trombone | {% include audio_player.html filename="audio/sod/best/33_instrument-informed.mp3" %} |
| __Ensemble__: church-organ, viola, contrabass, strings, voices, horn, oboe | {% include audio_player.html filename="audio/sod/best/10_instrument-informed.mp3" %} |

</div>

### Best program-genre-informed generation samples

> __Settings__: In this context, there exist five distinctive data event types: 'start-of-song,' 'start-of-program,' 'start-of-tags,' 'start-of-notes,' and 'end-of-song.' The 'start-of-program' event serves as an indicator for the initiation of a program list, while the 'start-of-tags' event marks the commencement of a tag list. Meanwhile, the 'start-of-notes' event signifies the outset of a sequence of music notes.

<div class="table-wrapper" markdown="block">

| {% include audio_player.html filename="audio/sod/best/9_4-beat-continuation.mp3" %} | {% include audio_player.html filename="audio/sod/best/19_4-beat-continuation.mp3" %} | {% include audio_player.html filename="audio/sod/best/23_4-beat-continuation.mp3" %}
| {% include audio_player.html filename="audio/sod/best/26_4-beat-continuation.mp3" %} | {% include audio_player.html filename="audio/sod/best/34_4-beat-continuation.mp3" %} | {% include audio_player.html filename="audio/sod/best/35_4-beat-continuation.mp3" %} |

</div>

---

## Examples of unconditioned generation (unselected) {#unconditional}

> __Settings__: Only a `start-of-song' event is provided to the model. The model generates the instrument list and subsequently the note sequence.

<div class="table-wrapper" markdown="block">

| | Sample 1 | Sample 2 | Sample 3 |
|:-:|:-:|:-:|:-:|
| MMT (ours) | {% include audio_player.html filename="audio/sod/ape/0_unconditioned.mp3" style="width:250px;" %} | {% include audio_player.html filename="audio/sod/ape/1_unconditioned.mp3" style="width:250px;" %} | {% include audio_player.html filename="audio/sod/ape/2_unconditioned.mp3" style="width:250px;" %} |
| MMM        | {% include audio_player.html filename="audio/sod/mmm/0_unconditioned.mp3" style="width:250px;" %} | {% include audio_player.html filename="audio/sod/mmm/1_unconditioned.mp3" style="width:250px;" %} | {% include audio_player.html filename="audio/sod/mmm/2_unconditioned.mp3" style="width:250px;" %} |
| REMI+      | {% include audio_player.html filename="audio/sod/remi/0_unconditioned.mp3" style="width:250px;" %} | {% include audio_player.html filename="audio/sod/remi/1_unconditioned.mp3" style="width:250px;" %} | {% include audio_player.html filename="audio/sod/remi/3_unconditioned.mp3" style="width:250px;" %} |

</div>

---

## Examples of instrument-informed generation (unselected) {#instrument-informed}

> __Settings__: The model is given a 'start-of-song' event followed by a sequence of instrument codes and a 'start-of-notes' event to start with. The model then generates the note sequence.

<div class="table-wrapper" markdown="block">

| | Sample  1 | Sample 2 | Sample 3 |
|:-:|:-:|:-:|:-:|
| MMT (ours) | {% include audio_player.html filename="audio/sod/ape/0_instrument-informed.mp3" style="width:250px;" %} | {% include audio_player.html filename="audio/sod/ape/1_instrument-informed.mp3" style="width:250px;" %} | {% include audio_player.html filename="audio/sod/ape/2_instrument-informed.mp3" style="width:250px;" %} |

</div>

---

## Examples of 4-beat continuation (unselected) {#continuation-4-beat}

> __Settings__: All instrument and note events in the first 4 beats are provided to the model. The model then generates subsequent note events that continue the input music.

<div class="table-wrapper" markdown="block">

| | Sample 1 | Sample 2 | Sample 3 |
|:-:|:-:|:-:|:-:|
| MMT (ours) | {% include audio_player.html filename="audio/sod/ape/0_4-beat-continuation.mp3" style="width:250px;" %} | {% include audio_player.html filename="audio/sod/ape/1_4-beat-continuation.mp3" style="width:250px;" %} | {% include audio_player.html filename="audio/sod/ape/2_4-beat-continuation.mp3" style="width:250px;" %} |
| Ground truth | {% include audio_player.html filename="audio/sod/truth/0_truth.mp3" style="width:250px;" %} | {% include audio_player.html filename="audio/sod/truth/1_truth.mp3" style="width:250px;" %} | {% include audio_player.html filename="audio/sod/truth/3_truth.mp3" style="width:250px;" %} |

</div>

---

## Examples of 16-beat continuation (unselected) {#continuation-16-beat}

> __Settings__: All instrument and note events in the first 16 beats are provided to the model. The model then generates subsequent note events that continue the input music.

<div class="table-wrapper" markdown="block">

| | Sample 1 | Sample 2 | Sample 3 |
|:-:|:-:|:-:|:-:|
| MMT (ours) | {% include audio_player.html filename="audio/sod/ape/0_16-beat-continuation.mp3" style="width:250px;" %} | {% include audio_player.html filename="audio/sod/ape/1_16-beat-continuation.mp3" style="width:250px;" %} | {% include audio_player.html filename="audio/sod/ape/2_16-beat-continuation.mp3" style="width:250px;" %} |
| Ground truth | {% include audio_player.html filename="audio/sod/truth/0_truth.mp3" style="width:250px;" %} | {% include audio_player.html filename="audio/sod/truth/1_truth.mp3" style="width:250px;" %} | {% include audio_player.html filename="audio/sod/truth/2_truth.mp3" style="width:250px;" %} |

</div>

