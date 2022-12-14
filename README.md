# spoken-label-recognition

## What’s the point?

The service receives an audio file and uses it as an input for trained model.

## Model details:

The service receives an speech WAV audio file on a 4 languages (English, French, German, Chinese) and uses it as an input to the Wav2Vec2.0 and Conformer models, based on a neural network trained in half-precision using a mixture of natural and synthetic data, and outputs the result of the speech sample recognition in form of a text label. The model runs on a GPU equipped with tensor cores to provide greater service bandwidth. The input audio file size is limited to 4Mb, in practice the optimal duration of the processed audio track should be no more than 90 seconds for 320 kbps audio.

## How does it work?

The user must provide the following inputs in order to start the service and get a response:

Inputs:

 -   `endpoint`: ?
 -   `method`: sl2l
 -   `input_path`: Path to '\*.txt' file containing JSON representation of input argument 'file@data' and its value - path to '\*.wav' input audio file.

Example of input file content:

```
{"file@data": "samples/sample.wav"}
```

## What to expect from this service?

Input audio: samples/sample.wav

Response: 
- `label: "english"`
- `label: "french"`
- `label: "german"`
- `lable: "chinese"`
