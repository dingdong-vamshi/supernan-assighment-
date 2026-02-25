# ai video dubbing and lip sync pipeline

this project builds a complete end to end ai video dubbing system.
the system takes an input video in english and automatically generates a hindi dubbed video with synchronized lip movements.

the pipeline combines speech recognition, translation, voice cloning and visual lip synchronization models into a single workflow.

---

## what the system does

input: english speaking video
output: same video + hindi voice + matching lips

steps:

1 extract audio from video
2 convert speech to english text (speech recognition)
3 translate english text to hindi
4 generate hindi speech (voice synthesis)
5 sync lips of the speaker with new audio
6 export final dubbed video

---

## architecture overview

video → audio → text → translated text → hindi voice → lip sync → final video

models used:

* openai whisper large v3 → speech to text
* translation model → english to hindi
* edge tts → natural hindi speech generation
* wav2lip → lip synchronization

---

## why two notebooks

wav2lip only works on python 3.10
modern speech ai tools work best on python 3.12

so the pipeline is split:

### notebook 1 (python 3.12)

handles ai understanding

* audio extraction
* speech recognition
* translation
* hindi voice generation

output:
hindi.wav

### notebook 2 (python 3.10)

handles computer vision

* face detection
* mouth movement generation
* video rendering

output:
final_result.mp4

---

## how to run

### step 1

upload a video file:
clip.mp4

run notebook 1 → produces:

* original.wav
* english.txt
* hindi.txt
* hindi.wav

### step 2

open wav2lip notebook

upload:

* clip.mp4
* hindi.wav

run wav2lip inference

final output:
final_result.mp4

---

## technologies used

python
pytorch
openai whisper
edge tts
ffmpeg
wav2lip
opencv

---

## learning outcomes

* multimodal ai (audio + video)
* speech recognition
* neural text to speech
* translation pipelines
* computer vision face alignment
* generative ai synthesis

this project demonstrates how multiple ai systems can be orchestrated into a single real world application.
