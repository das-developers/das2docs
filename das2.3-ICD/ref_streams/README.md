# Reference Streams for Das2.3 - Basic format

These streams are provided as a test for new das2.3 parsers.  All off them were
taken from mission data and provide real world processing examples.  Though 
all header packets are present in the reference streams, most of the data packets
have been dropped to conserve space.

All reference streams have been tested against the das2.3-basic.xsd schema file
using the included python script das2_validate.

| File                | Source                      | Plot Type  | Description    |
| :------------------ | :-------------------------- | :--------- | :------------- |
| B23_y-points_01.d2t | Van Allen Probe A location  | Multi-line | Data packet lengths are provided <br>MLT values occupy a circular space |
| B23_y-points_02.d2t | Van Allen Probe A location  | Multi-line | Example of stream y-points_01 after passing through a bin average reducer |
| B23_ | | | |

