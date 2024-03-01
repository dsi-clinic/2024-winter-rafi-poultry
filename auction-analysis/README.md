Follow the instructions to run the Streamlit app for the auction houses dashboard.

### (1)Data Directory Structure
- Set up the following data directory structure in your local `auction-analysis` folder
  ```
  auction-analysis/
  ├── data/
  │   ├── raw/
  │   └── cleaned/
  ```

### (1.5) Environment Preparation
- Set up Conda environment
  ```
  conda create --name <myenv> python=3.9.16
  ```
- Install necessary packages (from auction-analysis directory)
  ```
  Run pip install -r requirements.txt
  ```

### (2) Download Files
To run the Streamlit app, download the required data files from Google Drive into the respective directories:

- From [Drive - Data/auction_info](https://drive.google.com/drive/folders/1bZITx8lz-NR0e7vdLbYzGErer4iqWCot)  download and place into (local) `data/cleaned` directory:
  - auction_info.csv
  - flux.csv
- From [Drive - Data/misc/GeoJSONs](https://drive.google.com/drive/folders/1BD7YG3yEobUCEbcwFBa2znu2OOaFA2gB)  download the following files and place into (local) `data/raw` directory:
  - states.geojson

### (3) Run the Streamlit app
Streamlit app will be running in your browswer as a dynamic dashboard. (Additional documentation on Streamlit: https://streamlit.io/)
- **Option 1: Running in Docker:**
  
  - Ensure Docker Desktop is running.
  
  - cd into `2024-winter-rafi-poultry/auction-analysis`
  
  - Run the command for building the Docker image for the streamlit scripts
    ```
     make build-streamlit
    ```
  - Run the Docker container from the built Docker image and runs the streamlit app
    ```
     make run-streamlit
    ```
     If you encounter a "port is already allocated" error, terminate the active Docker container and retry.
- **Option 2: Running locally:**
  - cd into `2024-winter-rafi-poultry/auction-analysis`
  - To launch the Streamlit app
    ```
     streamlit run stream.py
    ```


### (4) Notebook Explanation & Instructions (`EDA_pipeline.ipynb`)
The notebook is used for two purposes: initial EDA and creating cleaned datasets (`auction_info.csv` and `flux.csv`). Therefore, if the datasets are already downloaded from the drive, running the notebooks is not necessary for running the streamlit app
### To run the notebook, 
- There are five raw datafiles that are needed to be placed in (local) `auction-analysis/data/raw`:
  - From [Drive - Data/raw/nets](https://drive.google.com/drive/folders/1ayKn9SdtrIAO-q8AU9ScmuBK8Qv9ZlbS):
    - NETSData2022_RAFI(WithAddresses).txt
    - NAICS2022_RAFI.csv
    - 2022-NAICS-Codes-6-digit.csv
    - rafi_sic.csv
  - From [Drive - Data/misc/GeoJSONs](https://drive.google.com/drive/folders/1BD7YG3yEobUCEbcwFBa2znu2OOaFA2gB):
    - states.geojson
    
      (Note that this is the same geojson that is needed for the Streamlit app so if already downloaded there is no need to redownload it)
- After running the `EDA_pipeline.ipynb`, `flux.csv` and `auction_info.csv` will be saved to `data/cleaned`
