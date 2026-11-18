# Play.ht is deprecated

Play.ht has discontinued its TTS service. `swarmauri_tts_playht`,
`swarmauri_llm_playht`, `PlayhtTTS` and legacy `PlayHTModel` imports are deprecated.
The SDK retains import compatibility and raises a local migration error on use.

Install the replacement with `uv add swarmauri_standard` or
`pip install swarmauri_standard`, then configure a new `OPENAI_API_KEY`:

```python
import os
from swarmauri_standard.tts.OpenaiTTS import OpenaiTTS

tts = OpenaiTTS(
    api_key=os.environ["OPENAI_API_KEY"],
    name="gpt-4o-mini-tts",
    voice="alloy",
)
tts.predict("Welcome to Swarmauri.", "welcome.mp3")
```

This preserves file output, async, batch and streaming workflows. Play.ht
credentials and voice IDs cannot be transferred. Voice cloning and management
require separate provisioning and provider-specific integration.

See the [SDK migration guide](https://github.com/swarmauri/swarmauri-sdk/blob/master/docs/migrations/playht.md)
and [provider deprecation notice](https://docs.audiostack.ai/changelog/30th-july-2025-playht-deprecation-notice).
