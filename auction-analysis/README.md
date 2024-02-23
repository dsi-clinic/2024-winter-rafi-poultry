(1) Establish auction-analysis directory structure

- auction-analysis
    - data
        - raw
        - cleaned

`TODO: the main point is the streamlit app, so explain how to run that as the primary thing in the README. Include the information about the notebooks, etc. after`

(1.5) Set up environment

- Set up Conda environment
    - `conda create --name <myenv> python=3.9.16`\
- Install necessary packages (from auction-analysis directory)\
    - Run pip install -r requirements.txt

(2) Streamlit app

- Streamlit app will be running in your browswer as a dynamic dashboard
    - Here is more information on the app: https://streamlit.io/
- To run the Streamlit app, download the following three files from the Drive to auction_analysis/data/raw:
    - from Data/auction_info download:
        - auction_info.csv
        - flux.csv
    - from Data/misc/GeoJSONs:
        - states.geojson
- Link to download: https://drive.google.com/drive/folders/1wjdTuK_DPFQba7k9Qx0lt_dvDV6DBnzR?usp=drive_link

- cd into /Users/<username>/2024-winter-rafi-poultry/auction-analysis
- Run command is `(from auction-analysis directory) streamlit run stream.py`

(2.5) Make File Commands & Instructions (running in Docker):

- Below are two commands for building and then running the streamlit app in Docker
- `make build-streamlit` will build the Docker image for the streamlit scripts
- `make run-streamlit` will run the Docker container from the streamlit image and runs the streamlit app

(3) Notebook Explanation & Instructions
- First make sure you install conda: `conda install -n auction ipykernel --update-deps --force-reinstall`\
- The notebook EDA_pipeline.ipynb takes in raw NETS and geojson datasets and generates two cleaned datasets utilized in our streamlit app (auction_info.csv and flux.csv)\
- Note that running the notebook is not required, it is here to show how we generated files that we used in our streamlit app
- To run the notebook, download the following five files from the Drive to auction_analysis/data/raw:\
    from Data/raw/nets:
        - NETSData2022_RAFI(WithAddresses).txt\
        - NAICS2022_RAFI.csv
        - 2022-NAICS-Codes-6-digit.csv
        - rafi_sic.csv
    - from Data/misc/GeoJSONs:
        - states.geojson
- After running the EDA_pipeline.ipynb you should have flux.csv and auction_info.csv saved to data/cleaned
    - Alternatively, you can also download flux.csv and auction_info.csv from Data/auction_info

