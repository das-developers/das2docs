# Reference Streams for Das2.3 - Basic Format

The stream files in this directory are provided for testing new das2.3 parsers.  All 
were taken from mission data and provide real world processing examples.  Though 
all header packets are present in the reference streams, most of the data packets
have been dropped to conserve space.

These stream files have been tested against the [das2.3-basic.xsd](../das2.3-basic.xsd)
schema using the included python3 script [das2_validate](../scripts/das2_validate).

| File                | Source                      | Plot Type  | Description    |
| :------------------ | :-------------------------- | :--------- | :------------- |
| [B23_y-points_01.d2t](B23_y-points_01.d2t) | Van Allen Probe A location  | Multi-line | Data packet lengths are provided MLT values occupy a circular space |
| [B23_y-points_02.d2t](B23_y-points_02.d2t) | Van Allen Probe A location  | Multi-line | **y-points_01** source, after passing through a bin average reducer |
| [B23_y-sets_01.d2t](B23_y-points_02.d2t)   | Juno Waves 50 kHz Burst     | Single-line| Efficent waveforms using time offsets |
| [B23_y-sets_02.d2t](B23_y-sets_02.d2t)     | Juno Waves 50 kHz Burst     | Single-line| Extends the headers in **y-sets_01** with user-defined elements |
| [B23_y-sets_03.d2s](B23_y-points_01.d2t)   | Juno Waves 50 KHz Burst     | Single-line| As **y-sets_01** but X-offsets explicitly enumerated and <br> data packets are binary |


