# GEO Data Processing Pipeline
## Project Overview
This project provides a data processing pipeline that uses various scripts and tools to download, process, and import data into Lamindb. The pipeline includes steps from data download to quality control and final data storage, ensuring a streamlined process for managing GEO datasets.

## Directory Structure
The following is the structure of the project directory:

```
bash/
    ├── download_xlsx.sh
    └── run_data_pipeline.sh1
geneid/
    ├── human_grch38_symbol_ensembl.csv
    └── mouse_grcm39_symbol_ensembl.csv
python/
    ├── DataExtract.py
    ├── GPT.py
    ├── QualityControl.py
    ├── UploadLamindb.py
    ├── __pycache__/
    │   ├── GPT.cpython-312.pyc
    │   └── prompt_column_match_2.txt
run_data_pipeline.sh
workdir/
    ├── data_pipeline2_env.yml
    └── data_pipeline2_requirements.txt
```
* `bash/`: Contains shell scripts for downloading data and running the pipeline.
* `geneid/`: Stores CSV files with __gene symbol mappings__ for different species.
* `python/`: Contains Python scripts for data extraction, processing, quality control, and uploading data to Lamindb.
* `run_data_pipeline.sh`: The __main script__ to run the data pipeline.
* `workdir/`: The __work directory__, and contains environment configuration files for setting up the project dependencies.

## Dependencies
The project requires the following dependencies, which are listed in the `data_pipeline2_env.yml` and `data_pipeline2_requirements.txt` files:
* Python 3.12
* Libraries as specified in `data_pipeline2_requirements.txt` (e.g., requests, pandas, lamindb, etc.)
* Conda environment setup as specified in `data_pipeline2_env.yml`.

## Installation Steps
To set up this project locally, follow these steps:
1. Clone the repository:

```
git clone https://github.com/gefujing/data_pipeline2
cd data_pipeline2
```

2. Navigate to the `workdir` folder:

```
cd workdir
```

3. Create and activate the environment using `conda`:

```
conda env create -f data_pipeline2_env.yml
conda activate lamindb
pip install -r data_pipeline2_requirements.txt
```
__NOTE:__ AWS servers do not require additional environment configuration.

## Usage
After setting up the environment, run the following command from within the `workdir` directory to execute the data processing pipeline:

```
bash -i ../run_data_pipeline.sh GSE161382
```
This command will start the pipeline using the specified GEO dataset ID (e.g., `GSE161382`), which will go through data download, processing, quality control, and upload to Lamindb.


















