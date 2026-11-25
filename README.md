# Moonlight Companion · Input and Attention Demo

Moonlight is Parsa’s experimental AI companion. This standalone Python demo presents two modules from the project. Enter a Persian or English sentence to see how Moonlight normalizes it, identifies a question, and represents the message alongside a simulated doorbell in its attention map.

## Run locally

Tested with Python 3.12. The demo uses only the Python standard library and runs offline. From the folder containing demo.py, run

```sh
python demo.py
python demo.py "Can you hear the doorbell?"
```

The default example converts “اين صدا از كجاست؟” to “این صدا از کجاست؟” and reports the language as fa. Try changing the punctuation or mixing scripts to explore the limits of the language and question heuristics.

## Inside the demo

- `mino/signal_processor.py` normalizes input and attaches features such as language, question punctuation and command markers.
- `lobes/parietal_lobe.py` maintains attention items, merges similar labels and returns a ranked snapshot.
- `demo.py` connects these modules through their public methods. The example assigns starting scores to a text item and a synthetic audio cue. The resulting scores are relative attention weights.

This repository contains an excerpt of Moonlight. The demo processes text supplied on the command line. It requires no microphone, model service or credentials.
