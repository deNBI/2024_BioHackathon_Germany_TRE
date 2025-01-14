# Workflow Submission

This is step-by-step guide for using the WESkit [GUI](https://weskit.bihealth.org) to submit a workflow run. Currently, there are 2 example workflows installed for testing.

## Prerequisites

To submit a workflow, you must be able to log-in via [LS Login](https://lifescience-ri.eu/ls-login/). 

Furthermore, you need to be registered for WESkit itself and have an account on the execution cluster. This is done by an administrator.

## Workflow: Nextflow

The first example workflow represents a simple bioinformatics pipeline based on Nextflow. It performs quality control, read alignment, and summary reporting on genomic data. The workflow is taken from the [SAGC repository](https://github.com/sagc-bioinformatics/nextflow-example-workflow-2024/blob/main/main.nf). It operates on a small, synthetic [data-set](https://github.com/snakemake/snakemake-tutorial-data/tree/master).

To run the workflow, visit the WESkit [Submission page](https://weskit.bihealth.org/submit). 

Choose the `nextflow_example` workflow.

Insert the config in JSON format. Make sure that `genome` contains the path to the genome fasta file and `samples` contains the path to the fastq sample files.

This is an example config JSON:
```json
{
    "genome": "/mnt/biohack_data/data/example-data/data/genome.fa",
    "samples": "/mnt/biohack_data/data/example-data/data/samples/*.fastq"
}
```

Pressing the *submit* button will trigger the execution of the Nextflow workflow. The [Runs page](https://weskit.bihealth.org/runs) contains an overview over all currently running workflows.

## Workflow: Snakemake

The second example workflow represents a simple bioinformatics pipeline based on Snakemake. It performs sequencing data mapping to a reference genome, sorting and indexing the mapped reads, calling genetic variants, and visualizing the quality of the results. The workflow is taken from the official [Snakemake tutorial](https://snakemake.readthedocs.io/en/stable/tutorial/tutorial.html). It operates on a small, synthetic [data-set](https://github.com/snakemake/snakemake-tutorial-data/tree/master).

To run the workflow, visit the WESkit [Submission page](https://weskit.bihealth.org/submit). 

Choose the `snakemake_example` workflow.

Insert the config in JSON format. Make sure that `genome` contains the path to the genome fasta file, `samples` contains a list of the samples and `samples_dir` contains the sample diretory path.

This is an example config JSON:
```json
{
    "genome": "/mnt/biohack_data/data/example-data/data/genome.fa",
    "samples_dir": "/mnt/biohack_data/data/example-data/data/samples/",
    "samples": ["A", "B"]
}
```

Pressing the *submit* button will trigger the execution of the Nextflow workflow. The [Runs page](https://weskit.bihealth.org/runs) contains an overview over all currently running workflows.


