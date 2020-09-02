# Reference Streams for Das2.3 - Basic Format

The stream files in this directory are provided for testing new das2.3 parsers.  All 
were taken from mission data and provide real world processing examples.  Though 
all header packets are present in the reference streams, most of the data packets
have been dropped to conserve space.

These stream files have been tested against the [das2.3-basic.xsd](../das2.3-basic.xsd)
schema using the included python3 script [das2_validate](../scripts/das2_validate).

| File                | Source                      | Plot Type  | Description    |
| :------------------ | :-------------------------- | :--------- | :------------- |
| [B23_y-points_01.d2t](B23_y-points_01.d2t) | Van Allen Probe A location | Multi-line    | MLT values occupy a circular space,<br>Provides data packet lengths |
| [B23_y-points_02.d2t](B23_y-points_02.d2t) | Van Allen Probe A location | Multi-line    | Statistics planes caused by passing<br> through a stream reducer |
| [B23_y-sets_01.d2t](B23_y-sets_01.d2t)     | Juno Waves 50 kHz Burst    | Single-line   | Efficent waveforms using time offsets |
| [B23_y-sets_02.d2t](B23_y-sets_02.d2t)     | Juno Waves 50 kHz Burst    | Single-line   | Extending headers with user-defined<br>elements |
| [B23_y-sets_03.d2s](B23_y-sets_03.d2t)     | Juno Waves 50 KHz Burst    | Single-line   | Using explicit X-offsets,<br>Binary data packets |
| [B23_z-points_01.d2t](B23_z-points_01.d2t) | MEX MARSIS Plasma Density  | Color-scatter | Scatter data in polar coordinates |
| [B23_z-sets_01.d2t](B23_z-sets_01.d2t)     | Galileo PWS Survey         | Spectrogram   | Sweep frequency reciever output |
| [B23_z-sets_02.d2t](B23_z-sets_02.d2t)     | Cassini RPWS Survey        | Spectrogram   | Covering frequency space via multiple<br>receivers |
| [B23_z-sets_03.d2t](B23_z-sets_03.d2t)     | Cassini RPWS Survey        | Spectrogram   | Adds location data to survey values |
| [B23_z-sets_04.d2t](B23_z-sets_04.d2t)     | Juno Waves Shifted Burst   | Spetrogram    | Dual side-band spectra from a tunable<br> mixer |
| [B23_w-sets_01.d2t](B23_w-sets_01.d2t)     | MEX MARSIS Radargram       | Volume-slice  | Data values as a function of three<br>coordinates |
