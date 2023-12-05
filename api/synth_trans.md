# `synthesis-service.` and `translate-service.` APIs

These retrieve the speech synthesis and translation results for their respective extensions.

### `GET translate-service.scratch.mit.edu/translate?language=<language code>&text=<text>`

Retrieves the translation of the input text in the given language. Assumed to use Google Translate

### `GET synthesis-service.scratch.mit.edu/synth?locale=<locale>&gender=<gender>&text=<text>`

Retrieves the synthesis of the input text as an audio file
