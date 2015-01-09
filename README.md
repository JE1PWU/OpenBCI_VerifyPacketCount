# OpenBCI_VerifyPacketCount
Simple sketch that scans OpenBCI data files to check for any dropped packets
The program will prompt you to select a file, then it will scan the sample counter on each line of data to check for dropped packets. After it reads the file, it will print the results in the terminal window in Processing. It will also creat a small text file in the sketch folder with the scan results. Here's an example of the output

    mouse pressed
    User selected /Users/biomurph/Documents/OpenBCI/Verification/Burke/SavedData\OpenBCI-RAW-Kelsey-2.csv
    timing file verification
    %OpenBCI Raw EEG Data
    %
    %Sample Rate = 250.0 Hz
    %First Column = SampleIndex
    %Other Columns = EEG data in microvolts with optional columns at end being unscaled Aux data
    At line 6  96 packets dropped
    At line 15893  1 packets dropped
    read 20320 lines
    nothing left in file
    verify took 53 mS

The first lines show which file was selected, the lines following that begin with % are copied from the OpenBCI data file (OpenBCI uses % as prefix for comments in the data files)

Each line in the data file is a sample, so this shows that at sample #1765, 4 packets were dropped, and that's it out of a total of 97209 samples

