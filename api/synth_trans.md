# `synthesis-service.` and `translate-service.` APIs

These retrieve the speech synthesis and translation results for their respective extensions.

## `https://translate-service.scratch.mit.edu/`

### `GET /translate?language=<locale>&text=<text>`

Retrieves the translation of the input text in the given language. `locale` is generally a two-letter language code. Refer to [this gist](https://gist.github.com/towerofnix/d4369e64604c5a0d7dca94954a83ab35) for a list of supported languages, or check the exports from [`scratch-translate-extension-languages`](https://www.npmjs.com/package/scratch-translate-extension-languages).

Uses Google Translate [as of Dec. 9, 2019](https://scratch.mit.edu/discuss/post/3778811).

### `GET https://translate-service.scratch.mit.edu/supported`

Retrieves a list of supported language codes for translating text.

Legacy endpoint - still online, but [no longer used](https://github.com/scratchfoundation/scratch-vm/pull/1159).

## `https://synthesis-service.scratch.mit.edu/`

### `GET /synth?locale=<speech locale>&gender=<gender>&text=<text>`

Retrieves the synthesis of the input text as an audio file. `gender` is either "male" or "female"; `speech locale` is a "speech synth locale" as described in [the extension's source code](https://github.com/scratchfoundation/scratch-vm/blob/489111f4d74909c2adac40ade1618f966ba30c34/src/extensions/scratch3_text2speech/index.js#L194-L341).

Likely uses [Amazon Polly](https://aws.amazon.com/polly/).
