# Reference streams in das2.3-basic format

The stream files in this directory are provided for testing new das2.3 parsers.  All 
were taken from mission data and provide real world processing examples.  Though 
all header packets are present in these streams, most of the data packets have been
dropped to conserve space.

These files have been tested against the [das2.3-basic-strict.xsd](../das2.3-basic-strict.xsd)
schema document except for [ex05_yset_custom_b23.d2t](ex05_yset_custom_b23.d2t) which was validated
using the standard extendable schema [das2.3-basic.xsd](../das2.3-basic.xsd).  Validation
was performed using the included python3 script [das2_validate](../scripts/das2_validate).

| Fil                                                     | Source                     | Plot Type  | Description    |
| :------------------------------------------------------ | :------------------------- | :--------- | :------------- |
| [ex01_y_ephem_b23.d2t](ex01_y_ephem_b23.d2t)            | Van Allen Probe A location | Multi-line    | MLT values occupy a circular space,<br>Provides data packet lengths |
| [ex02_y_reduced_b23.d2t](ex02_y_reduced_b23.d2t)        | Van Allen Probe A location | Multi-line    | Statistics planes caused by passing<br> through a stream reducer |
| [ex03_y_events_b23.d2t](ex03_y_events_b23.d2t)          | Voyager Events List        | Named-events  | Character data with min-max times |
| [ex04_yset_waveform_b23.d2t](ex04_yset_waveform_b23.d2t)| Juno Waves 50 kHz Burst    | Single-line   | Efficent waveforms using time offsets |
| [ex05_yset_custom_b23.d2t](ex05_yset_custom_b23.d2t)    | Juno Waves 50 kHz Burst    | Single-line   | Extending headers with user-defined<br>elements |
| [ex06_yset_binary_b23.d2s](ex06_yset_binary_b23.d2s)    | Juno Waves 50 KHz Burst    | Single-line   | Using explicit X-offsets,<br>Binary data packets |
| [ex07_z_satter_b23.d2t](ex07_z_satter_b23.d2t)          | MEX MARSIS Plasma Density  | Color-scatter | Scatter data in polar coordinates |
| [ex08_zset_dynaspec_b23.d2t](ex08_zset_dynaspec_b23.d2t)| Galileo PWS Survey         | Spectrogram   | Sweep frequency reciever output |
| [ex09_zset_multispec_b23.d2t](ex09_zset_multispec_b23.d2t)| Cassini RPWS Survey      | Spectrogram   | Covering frequency space via multiple<br>receivers |
| [ex10_zset_ephemspec_b23.d2t](ex10_zset_ephemspec_b23.d2t)| Cassini RPWS Survey      | Spectrogram   | Adds location data to survey values |
| [ex11_zset_wanderspc_b23.d2t](ex11_zset_wanderspc_b23.d2t)| Juno Waves Shifted Burst | Spectrogram   | Spectra from an Fce tracking mixer |
| [ex12_wset_sounder_b23.d2t](ex12_wset_sounder_b23.d2t)  | MEX MARSIS Radargram       | Volume-slice  | Data values as a function of three<br>coordinates |

