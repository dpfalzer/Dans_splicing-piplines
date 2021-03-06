## Run with GTEX data
You can run pipeline on GTEX data otained directly from Gen3-DRS if you specify input option:
```
--download_from 'GTEX'
```

You will be needing two things from - https://gen3.theanvil.io/

1. [manifest file](https://github.com/TheJacksonLaboratory/splicing-pipelines-nf/blob/dev-v2.1/examples/GTEX/manifest.json)
2. credentials file

Original downloaded `manifest.json` will be converted into `manifest.csv` with pipeline using: https://csvkit.readthedocs.io/en/latest/ 

The manifest.csv will be subset using the `reads.csv` file provided in `--reads` param. (This allows you to download a complete manifest and later select the samples of interest.) For example: [gtex.reads](https://github.com/TheJacksonLaboratory/splicing-pipelines-nf/blob/dev-v2.1/examples/GTEX/reads.csv)

Downloaded `credentials.json` file can be provided in `--key_file` param.
NOTE: Make sure `credentials.json` is a latest one. They have expiration dates when you download.

If you running with AnviL Gen3-DRS to download CRAM files you also need to provide a Genome fasta file with `--genome_fasta`, which will be used to convert CRAM files to BAM format. If you are donwloading bam files, you can skip this parameter.

For a minimal params list check [gtex.config](../conf/examples/GTEX_config.md)
