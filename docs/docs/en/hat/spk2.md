# Hat SPK2

## Example Program

> Plays a tone every second for a duration of one second, setting the volume to 6.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/spk2/uiflow_block_hat_spk2_demo.png">

```python
from m5stack import *
from m5ui import *
from uiflow import *
import time
import hat

setScreenColor(0x111111)

hat_spk2_0 = hat.get(hat.SPEAKER_I2S)

while True:
  hat_spk2_0.playTone(220, 1, volume=6)
  wait(1)
  hat_spk2_0.playTone(247, 1, volume=6)
  wait(1)
  hat_spk2_0.playTone(131, 1, volume=6)
  wait(1)
  wait_ms(2)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/spk2/uiflow_block_hat_spk2_play_cloud_wav.svg">

```python
hat_spk2_0.playCloudWAV('', volume=0)
```

- Plays a WAV audio file from a provided cloud URL with adjustable volume.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/spk2/uiflow_block_hat_spk2_play_sing.svg">

```python
hat_spk2_0.playTone(220, 1, volume=0)
```

- Plays a specified tone (e.g., Low A) for 1 beat, with adjustable volume.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/spk2/uiflow_block_hat_spk2_play_tone.svg">

```python
hat_spk2_0.playTone(220, 1, volume=0)
```

- Plays a tone at a specified frequency (e.g., 220 Hz) for 1 beat, with adjustable volume.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/spk2/uiflow_block_hat_spk2_play_wav_dropdown.svg">

```python
/
```

- Selects a WAV audio file from local storage to play, with adjustable volume.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/spk2/uiflow_block_hat_spk2_play_wav_rate.svg">

```python
hat_spk2_0.playWAV('', rate=44100, data_format=hat_spk2_0.F16B, channel=hat_spk2_0.CHN_LR, volume=0)
```

- Plays a specified WAV file with customizable sample rate, data format, channel, and volume.