<h1 align="center"><img src="http://www.pacb.com/wp-content/themes/pacific-biosciences/img/pacific-biosciences-logo-mobile.svg"/></h1>
<h1 align="center">bax2bam</h1>
<p align="center">bax2bam converts the legacy PacBio basecall format (bax.h5) into the BAM
basecall format</p>

***

## Availability
Latest version can be installed via bioconda package `bax2bam`.

Please refer to our [official pbbioconda page](https://github.com/PacificBiosciences/pbbioconda)
for information on Installation, Support, License, Copyright, and Disclaimer.

## Command-line interface

```

Usage: bax2bam [options] <input files...>

bax2bam converts the legacy PacBio basecall format (bax.h5) into the BAM
basecall format.

Options:
  -h, --help            show this help message and exit
  --version             show program's version number and exit

  Input/output files:
    movie.1.bax.h5 movie.2.bax.h5 ...
                        Input files which should be from the same movie
    --xml=STRING        DataSet XML file containing a list of movie names
    -f STRING, --fofn=STRING
                        File-of-file-names containing a list of input files
    -o STRING           Prefix of output filenames. Movie name will be used if
                        no prefix provided
    --output-xml=STRING
                        Explicit output XML name. If none provided via this arg,
                        bax2bam will use -o prefix (<prefix>.dataset.xml). If
                        that is not specified either, the output XML filename
                        will be <moviename>.dataset.xml

  Output read types (mutually exclusive):
    --subread           Output subreads (default)
    --hqregion          Output HQ regions
    --polymeraseread    Output full polymerase read
    --ccs               Output CCS sequences

  Pulse feature options:
    Configure pulse features in the output BAM. Supported features include:
        Pulse Feature:    BAM tag:  Default:
        DeletionQV        dq        Y
        DeletionTag       dt        Y
        InsertionQV       iq        Y
        IPD               ip        Y
        PulseWidth        pw        Y
        MergeQV           mq        Y
        SubstitutionQV    sq        Y
        SubstitutionTag   st        N
    If this option is used, then only those features listed will be included,
    regardless of the default state.

    --pulsefeatures=STRING
                        Comma-separated list of desired pulse features, using
                        the names listed above.
                        
    --losslessframes    Store full, 16-bit IPD/PulseWidth data, instead of
                        (default) downsampled, 8-bit encoding.

  Output BAM file type:
    --internal          Output BAMs in internal mode. Currently this indicates
                        that non-sequencing ZMWs should be included in the
                        output scraps BAM file, if applicable.

```

DISCLAIMER
----------
THIS WEBSITE AND CONTENT AND ALL SITE-RELATED SERVICES, INCLUDING ANY DATA, ARE PROVIDED "AS IS," WITH ALL FAULTS, WITH NO REPRESENTATIONS OR WARRANTIES OF ANY KIND, EITHER EXPRESS OR IMPLIED, INCLUDING, BUT NOT LIMITED TO, ANY WARRANTIES OF MERCHANTABILITY, SATISFACTORY QUALITY, NON-INFRINGEMENT OR FITNESS FOR A PARTICULAR PURPOSE. YOU ASSUME TOTAL RESPONSIBILITY AND RISK FOR YOUR USE OF THIS SITE, ALL SITE-RELATED SERVICES, AND ANY THIRD PARTY WEBSITES OR APPLICATIONS. NO ORAL OR WRITTEN INFORMATION OR ADVICE SHALL CREATE A WARRANTY OF ANY KIND. ANY REFERENCES TO SPECIFIC PRODUCTS OR SERVICES ON THE WEBSITES DO NOT CONSTITUTE OR IMPLY A RECOMMENDATION OR ENDORSEMENT BY PACIFIC BIOSCIENCES.
