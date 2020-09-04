# Schemas, validators, stream examples and control documents for das2.3

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
	 
