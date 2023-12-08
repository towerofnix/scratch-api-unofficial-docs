# `synthesis-service.` and `translate-service.` APIs

These retrieve the speech synthesis and translation results for their respective extensions.

Valid `locales` and `speech locales` can be viewed in the Text to Speech extension [source code](https://github.com/scratchfoundation/scratch-vm/blob/489111f4d74909c2adac40ade1618f966ba30c34/src/extensions/scratch3_text2speech/index.js#L194-L341)

### `GET translate-service.scratch.mit.edu/translate?language=<locale>&text=<text>`

Retrieves the translation of the input text in the given language. Uses Google Translate [as of Dec. 9, 2019](https://scratch.mit.edu/discuss/post/3778811).

### `GET https://translate-service.scratch.mit.edu/supported`

Retrieves a list of supported language codes for translating text

### `GET synthesis-service.scratch.mit.edu/synth?locale=<speech locale>&gender=<gender>&text=<text>`

Retrieves the synthesis of the input text as an audio file. The gender parameter can be either "male" or "female". Likely uses [Amazon Polly](https://aws.amazon.com/polly/).
