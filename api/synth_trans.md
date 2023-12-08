# `synthesis-service.` and `translate-service.` APIs

These retrieve the speech synthesis and translation results for their respective extensions.

### `GET translate-service.scratch.mit.edu/translate?language=<language code>&text=<text>`

Retrieves the translation of the input text in the given language. Uses Google Translate [as of Dec. 9, 2019](https://scratch.mit.edu/discuss/post/3778811).

### `GET https://translate-service.scratch.mit.edu/supported`

Retrieves a list of supported language codes for translating text

### `GET synthesis-service.scratch.mit.edu/synth?locale=<locale>&gender=<gender>&text=<text>`

Retrieves the synthesis of the input text as an audio file. Likely uses [Amazon Polly](https://aws.amazon.com/polly/)
