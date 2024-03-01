(1) Establish auction-analysis directory structure

- auction-analysis
  - data
    - raw
    - cleaned

(1.5) Set up environment
- Set up Conda environment
  - `conda create --name <myenv> python=3.9.16`
- Install necessary packages (from auction-analysis directory)
  - `Run pip install -r requirements.txt`

(2) Download Files
- To run the Streamlit app, there are three data files needed from the Drive:
  - from (Drive - https://drive.google.com/drive/folders/1bZITx8lz-NR0e7vdLbYzGErer4iqWCot) Data/auction_info download and place into (local) data/clean directory:
    - auction_info.csv
    - flux.csv
  - from (Drive - https://drive.google.com/drive/folders/1BD7YG3yEobUCEbcwFBa2znu2OOaFA2gB) Data/misc/GeoJSONs download and place into (local) data/raw directory:
    - states.geojson

(3) Streamlit app
- Streamlit app will be running in your browswer as a dynamic dashboard
  - Additional documentation on Streamlit: https://streamlit.io/
- Running in Docker:
    - Below are two commands for building and then running the streamlit app in Docker (note that Docker must be running for these to work)
    - `make build-streamlit` will build the Docker image for the streamlit scripts
    - `make run-streamlit` will run the Docker container from the streamlit image and runs the streamlit app
- Running locally:
    - cd into 2024-winter-rafi-poultry/auction-analysis
    - Run command is (from directory that contains the app) `streamlit run stream.py`

- Link to download: https://drive.google.com/drive/folders/1wjdTuK_DPFQba7k9Qx0lt_dvDV6DBnzR?usp=drive_link

(4) Notebook Explanation & Instructions
- The notebooks were used for two purposes: initial EDA and creating cleaned datasets (auction_info.csv and flux.csv)
    - Therefore, if downloaded from the drive, running the notebooks is not necessary for running the streamlit app
- To run the notebook, there are five raw datafiles that are needed to be placed in (local) auction-analysis/data/raw:
- From (Drive - https://drive.google.com/drive/folders/1ayKn9SdtrIAO-q8AU9ScmuBK8Qv9ZlbS) Data/raw/nets:
    - NETSData2022_RAFI(WithAddresses).txt
    - NAICS2022_RAFI.csv 
    - 2022-NAICS-Codes-6-digit.csv 
    - rafi_sic.csv
- From (Drive - https://drive.google.com/drive/folders/1BD7YG3yEobUCEbcwFBa2znu2OOaFA2gB) Data/misc/GeoJSONs:
    - states.geojson
        - Note that this is the same geojson that is needed for the Streamlit app so if already downloaded there is no need to redownload it
- After running the EDA_pipeline.ipynb flux.csv and auction_info.csv will be saved to data/cleaned
