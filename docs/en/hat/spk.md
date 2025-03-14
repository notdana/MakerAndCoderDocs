# Hat SPK

## Example

> Adjusts volume and plays a tone every second.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/spk/uiflow_block_hat_spk_demo.png">

```python
from m5stack import *
from m5ui import *
from uiflow import *
import hat
import time
import hat

setScreenColor(0x111111)

hat_spk_0 = hat.get(hat.SPEAKER)

hat_spk_0.setVolume(1)
while True:
  hat_spk_0.sing(220, 1)
  wait(1)
  hat_spk_0.sing(247, 1)
  wait(1)
  hat_spk_0.sing(247, 1)
  wait(1)
  wait_ms(2)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/spk/uiflow_block_hat_speaker_sing.svg">

```python
hat_spk_0.sing(220, 1)
```

- Plays a specified tone (e.g., Low A) for 1 beat. This block can be used to play different tones with specified frequencies and durations, suitable for creating simple sound effects or music demos.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/spk/uiflow_block_hat_speaker_tone.svg">

```python
hat_spk_0.tone(1800, 200)
```

- Produces a beep at a specified frequency. In this example, the frequency is set to 1800 Hz with a duration of 200 milliseconds.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/spk/uiflow_block_hat_speaker_vol.svg">

```python
hat_spk_0.setVolume(1)
```

- Sets the volume of the speaker. Here, the volume is set to 1, which may represent maximum volume or a specific level within a range.