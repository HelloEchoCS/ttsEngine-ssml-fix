# SherpaTTS With SSML tag fix

This repo is forked from [SherpaTTS](https://github.com/woheller69/ttsEngine), which is an Android Text-to-Speech engine based on Next-gen Kaldi. It uses voices from [Piper Voices](https://rhasspy.github.io/piper-samples/) or [Coqui](https://github.com/coqui-ai/TTS/).

## Why this fork exists

Some applications (Here WeGo, for example) will send speech text with SSML tags. For example:
```
<speak> Turn Left, then turn right <break=1000ms /></speak>
```
SherpaTTs currently doesn't support SSML tags. When SherpaTTS sees it, the output speech still reads out the tags:
```
Speak turn left, then turn right break equals 1000ms //speak
```

A fix has been put in place to strip SSML tags from the input text before it is sent to TTS pipeline. This is only a temporary measure until a upstream fix is in place.

For more details about this issue, see: [Implement fix for spoken SSML metadata #115](https://github.com/woheller69/ttsEngine/issues/115)
