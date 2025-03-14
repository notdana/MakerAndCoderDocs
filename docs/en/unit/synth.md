# [Unit Synth](/en/unit/Unit-Synth)

## Example

Play notes with a 300ms interval.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/synth/uiflow_block_example.svg">

```python
from m5stack import *
from m5stack_ui import *
from uiflow import *
import time
import unit

screen = M5Screen()
screen.clean_screen()
screen.set_screen_bg_color(0xFFFFFF)
synth_0 = unit.get(unit.SYNTH, unit.PORTB)

synth_0.set_channel_volume(0, 121)
synth_0.set_change_instrument(0, 0, 112)
while True:
  synth_0.set_note_on(0, 80, 23)
  synth_0.set_note_on(0, 57, 73)
  wait_ms(300)
  synth_0.set_note_on(0, 66, 101)
  synth_0.set_note_on(0, 60, 52)
  wait_ms(2)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/synth/uiflow_block_unit_synth_set_all_drums.svg">

```python
synth_0.set_all_drums()
```

- Send a System Exclusive message to reset all drums on channel to their default settings.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/synth/uiflow_block_unit_synth_set_all_note_off.svg">

```python
synth_0.set_all_notes_off(0)
```

- Stop sending MIDI messages to a specified channel.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/synth/uiflow_block_unit_synth_set_change_instrument.svg">

```python
synth_0.set_change_instrument(0, 0, 1)
```

- Change the program (instrument) on a specified MIDI channel.
  - bank - programmed source selector (bank0 GM: Standard source /bank127: MT-32 source)
  - channel – MIDI channel (0-15).
  - value – Program number (0-127).

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/synth/uiflow_block_unit_synth_set_channel_volume.svg">

```python
synth_0.set_channel_volume(0, 0)
```

- Set the channel volume for a specified MIDI channel.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/synth/uiflow_block_unit_synth_set_chorus.svg">

```python
synth_0.set_chorus(0, 0, 0, 0, 0)
```

- Configure a chorus effect on a specified MIDI channel.
  - channel – MIDI channel (0-15).
  - program – Chorus program number (0-7).
  - level – Chorus level (0-127).
  - feedback – Chorus feedback amount (0-127).
  - chorusdelay – Chorus delay amount (0-127).

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/synth/uiflow_block_unit_synth_set_device_reset.svg">

```python
synth_0.midi_reset()
```

- Send a MIDI System Exclusive Reset command.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/synth/uiflow_block_unit_synth_set_envelope.svg">

```python
synth_0.set_envelope(0, 0, 0, 0)
```

- Set the pitch bend range for a specified MIDI channel.
  - channel – MIDI channel to apply the pitch bend (0-15).
  - attack – Attack time (0-127, note: this may be a misunderstanding as pitch bend does not traditionally have attack/decay/release times).
  - decay – Decay time (0-127, same note as above).
  - release – Release time (0-127, same note as above). These parameters might be intended for another envelope type, not pitch bend.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/synth/uiflow_block_unit_synth_set_eq.svg">

```python
synth_0.set_equalizer(0, 0, 0, 0, 0, 0, 0, 0, 0)
```

- Set the equalizer levels and frequencies for a specified MIDI channel.
  - channel – MIDI channel (0-15).
  - Low Band – Low-band level (-12dB to +12dB).
  - MedLowBand – Mid-low-band level (-12dB to +12dB).
  - MedHighBand – Mid-high-band level (-12dB to +12dB).
  - High Band – High-band level (-12dB to +12dB).
  - LowFreq – Low-band frequency (Hz).
  - MedLowFreq – Mid-low-band frequency (Hz).
  - MedHighFreq – Mid-high-band frequency (Hz).
  - HighFreq – High-band frequency (Hz).

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/synth/uiflow_block_unit_synth_set_master_volume.svg">

```python
synth_0.set_master_volume(0)
```

- Use a standard System Exclusive message to set the master volume (0-127).

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/synth/uiflow_block_unit_synth_set_mod_wheel.svg">

```python
synth_0.set_mod_wheel(0, 0, 0, 0, 0, 0, 0, 0)
```

- Set modulation wheel parameters affecting various effects on a specified MIDI channel.
  - channel – MIDI channel to apply modulation (0-15).
  - pitch – Pitch modulation depth.
  - tvtcutoff – Cutoff frequency modulation depth (TVT may refer to a specific filter type or be a typo).
  - amplitude – Amplitude modulation depth.
  - rate – Modulation rate.
  - pitchdepth – Pitch modulation depth (redundant with "pitch").
  - tvfdepth – TVF (Tone Voltage Filter, or possibly a typo) modulation depth.
  - tvadepth – TVA (Tone Volume Amplifier, or possibly a typo) modulation depth.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/synth/uiflow_block_unit_synth_set_note_off.svg">

```python
synth_0.set_note_off(0, 0)
```

- Send a MIDI Note Off message to a specified MIDI channel.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/synth/uiflow_block_unit_synth_set_note_on.svg">

```python
synth_0.set_note_on(0, 0, 0)
```

- Send a MIDI Note On message to a specified MIDI channel.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/synth/uiflow_block_unit_synth_set_pan.svg">

```python
synth_0.set_pan(0, 0)
```

- Set the pan position for a specified MIDI channel.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/synth/uiflow_block_unit_synth_set_pitch_bend.svg">

```python
synth_0.set_pitch_bend(0, 0)
```

- Send a MIDI Pitch Bend message to a specified MIDI channel.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/synth/uiflow_block_unit_synth_set_pitch_bend_range.svg">

```python
synth_0.set_pitch_bend_range(0, 0)
```

- Set the pitch bend range on a specified MIDI channel.
  - channel – MIDI channel (0-15).
  - value – Pitch bend value (0-16383).

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/synth/uiflow_block_unit_synth_set_reverb.svg">

```python
synth_0.set_reverb(0, 0, 0, 0)
```

- Configure a reverb effect on a specified MIDI channel.
  - channel – MIDI channel (0-15).
  - program – Reverb program number (0-7).
  - level – Reverb level (0-127).
  - delayfeedback – Delay feedback amount (0-127).

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/synth/uiflow_block_unit_synth_set_scale_tuning.svg">

```python
synth_0.set_scale_tuning(0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0)
```

- Set scale tuning for a specified MIDI channel.
  - channel – MIDI channel to apply scale tuning (0-15).
  - v1~v12 – Tuning values for each note in the scale (0-127).

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/synth/uiflow_block_unit_synth_set_tuning.svg">

```python
synth_0.set_tuning(0, 0, 0)
```

- Set tuning for a specified MIDI channel.
  - channel – MIDI channel (0-15).
  - fine – Fine tuning value (cents).
  - coarse – Coarse tuning value (semitones).

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/synth/uiflow_block_unit_synth_set_tvf.svg">

```python
synth_0.set_tvf(0, 0, 0)
```

- Set TVF (Tone Voltage Filter, or possibly a specific filter type) parameters on a specified MIDI channel.
  - channel – MIDI channel to apply the filter (0-15).
  - cutoff – Filter cutoff frequency (0-127).

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/synth/uiflow_block_unit_synth_set_vibrate.svg">

```python
synth_0.set_vibrate(0, 0, 0, 0)
```

- Set vibrato effect parameters on a specified channel
  - channel: The MIDI channel (0-15) to apply the vibrato effect to
  - rate: Vibrato rate (0-127)
  - depth: Vibrato depth (0-127)
  - delay: Vibrato delay (0-127)
