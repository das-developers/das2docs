# Das2.3 - Control Documents, Examples, Schemas, and Validators

This project is in progress.  Though the ICD covers more aspects of the das2
system then the stream format, updates to the stream format and it's 
documentation is the major development focus for das2.3.  New features for
das2 streams are:

  * Data planes are now explicit, not implicit, items.  This
    solves many problems and makes reduction with statistics (mean,
    standard deviation, count, etc.) easier.

  * Start vs. center time points are now explicit.

  * Int8 values have been added to stream CDF TT2000 times.

  * Char values have been added for streaming schedules of events.

  * Time offsets for sweep frequency receivers may be explicitly
    denoted.

  * Widths in an axis, such as reciver channel bandwidths, error ranges
    etc. can be explicitly denoted.

  * Reference and offset coordinates explicitly denoted.  This allows
    waveforms, apparent altitude and down-mixing receiver data to all
    be handled in a consistant manner.

  * All stream item names consistently start with the letter of the
    axis for which they provide data (yscan --> zset)

  * The header XSD schema is extensible at explicit points so that
    site customizations may be added without breaking standard/older
    tools.

  * The W axis has been added for streaming volumetric data, such as 
    Mars Express radargrams.

  * Data joins across packets are now explicit using the group 
    attribute, this way each array can have a unique name in the
    stream (helps Juno Survey data).

  * Data packets can have explicit lengths, but these are not required
    unless data packets are appened with extra non-standard stuff.
	 
The [das2.3-ICD.pdf](das2.3-ICD.pdf) provides normative rules for generating,
transfroming, and reading das2.3 streams.
	 

# Das2.3 Reference Streams

The files in the [streams](./streams) directory are provided for testing new 
das2.3 parsers.  All were taken from mission data and provide real world
processing examples.  Though all header packets are present in these streams,
most of the data packets have been dropped to conserve space.

These files have been tested against the 
[das2.3-basic-strict.xsd](das2.3-basic-strict.xsd) schema document except for
[ex05_yset_custom_2.3.d2t](ex05_yset_custom_2.3.d2t) which was validated
using the standard extendable schema [das2.3-basic.xsd](das2.3-basic.xsd).
Validation was performed using the included python3 script
[das2_validate](das2_validate).

| File                                                    | Source                     | Plot Type  | Description    |
| :------------------------------------------------------ | :------------------------- | :--------- | :------------- |
| [ex01_y_ephem_2.3.d2t](streams/ex01_y_ephem_2.3.d2t)            | Van Allen Probe A location | Multi-line    | MLT values occupy a circular space,<br>Provides data packet lengths |
| [ex02_y_reduced_2.3.d2t](streams/ex02_y_reduced_2.3.d2t)        | Van Allen Probe A location | Multi-line    | Statistics planes caused by passing<br> through a stream reducer |
| [ex03_y_events_2.3.d2t](streams/ex03_y_events_2.3.d2t)          | Voyager Events List        | Named-events  | Character data with min-max times |
| [ex04_yset_waveform_2.3.d2t](streams/ex04_yset_waveform_2.3.d2t)| Juno Waves 50 kHz Burst    | Single-line   | Efficent waveforms using time offsets |
| [ex05_yset_custom_2.3.d2t](streams/ex05_yset_custom_2.3.d2t)    | Juno Waves 50 kHz Burst    | Single-line   | Extending headers with user-defined<br>elements |
| [ex06_yset_binary_2.3.d2s](streams/ex06_yset_binary_2.3.d2s)    | Juno Waves 50 KHz Burst    | Single-line   | Using explicit X-offsets,<br>Binary data packets |
| [ex07_z_scatter_2.3.d2t](streams/ex07_z_scatter_2.3.d2t)          | MEX MARSIS Plasma Density  | Color-scatter | Scatter data in polar coordinates |
| [ex08_zset_dynaspec_2.3.d2t](streams/ex08_zset_dynaspec_2.3.d2t)| Galileo PWS Survey         | Spectrogram   | Sweep frequency reciever output |
| [ex09_zset_multispec_2.3.d2t](streams/ex09_zset_multispec_2.3.d2t)| Cassini RPWS Survey      | Spectrogram   | Covering frequency space via multiple<br>receivers |
| [ex10_zset_ephemspec_2.3.d2t](streams/ex10_zset_ephemspec_2.3.d2t)| Cassini RPWS Survey      | Spectrogram   | Adds location data to survey values |
| [ex11_zset_wanderspc_2.3.d2t](streams/ex11_zset_wanderspc_2.3.d2t)| Juno Waves Shifted Burst | Spectrogram   | Spectra from an Fce tracking mixer |
| [ex12_wset_sounder_2.3.d2t](streams/ex12_wset_sounder_2.3.d2t)  | MEX MARSIS Radargram       | Volume-slice  | Data values as a function of three<br>coordinates |


# Das2.2 Reference Streams

Das2-developers have no intention of dropping support for the older das2.2
stream fromat.  Though we hope that in time, new data sources will take
adavantage of the extra precision and flexibility of das2.3 streams,
we understand that devoting resources to retrofitting older servers is
not always possible, nor wise.  Given these realities, new das2.3 parsers
are asked to maintain support for das2.2 streams **indefinitily**.

To support backwards compatibility the validator script [das2_validate](das2_validate) 
also reads and checks das2.2 streams.  Since das2.2 did not follow XML
convertions regarding namespaces, the validator internally translates
the older `<properties>` elements during parsing into a form that can be
verified via XML schemas.  The following files in the [streams](streams) 
directory have been tested against 
[das2.2-mostly-strict.xsd](das2.2-mostly-strict.xsd) after modification
of thier `<properties>` elements in RAM.

| File                                                    | Source                     | Plot Type  | Description    |
| :------------------------------------------------------ | :------------------------- | :--------- | :------------- |
| [ex96_yscan_multispec_2.2.d2t](streams/ex96_yscan_multispec_2.2.d2t) | Cassini RPWS Survey   | Spectrogram | Covering frequency space via multiple<br>receivers |








