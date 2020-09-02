# Reference Streams for Das2.3 - Basic Format

The stream files in this directory are provided for testing new das2.3 parsers.  All 
were taken from mission data and provide real world processing examples.  Though 
all header packets are present in the reference streams, most of the data packets
have been dropped to conserve space.

These stream files have been tested against the [das2.3-basic.xsd](https://github.com/das-developers/das2docs/blob/properties/das2.3-ICD/das2.3-basic.xsd)
schema using the included python3 script [das2_validate](https://github.com/das-developers/das2docs/blob/properties/das2.3-ICD/scripts/das2_validate).

| File                | Source                      | Plot Type  | Description    |
| :------------------ | :-------------------------- | :--------- | :------------- |
| B23_y-points_01.d2t | Van Allen Probe A location  | Multi-line | Data packet lengths are provided <br>MLT values occupy a circular space |
| B23_y-points_02.d2t | Van Allen Probe A location  | Multi-line | Example of stream y-points_01 <br>after passing through a bin average reducer |
| B23_y-sets_01.d2t   | Juno Waves 50 kHz Burst     | Single-line| An example of a set of y values <br> occuring in each packet |


