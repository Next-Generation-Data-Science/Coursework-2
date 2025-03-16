# GoLang Code Generation

<figure>
  <img src="https://www.sectigo.com/uploads/images/_950xAUTO_fit_center-center_none/golang-large.png" width="350" height="200" alt="GoLang Logo">
  <figcaption><small><i>GoLang Programming Language - Image from Sectigo</i></small></figcaption>
</figure>

## Overview
This repository contains the code and dataset for analysing gas flaring trends in Algeria from 2015 to 2019. The analysis is based on two datasets: one from the World Bank and another from the annual global flare site surveys. The project involves data preprocessing, clustering, and regression modeling to understand the evolution of gas flaring over time.

## Repository Structure
```
📁 Coursework-2/  
├── 📁 data/                                                    # Folder containing the input datasets  
│    ├── 📄 2012-2023-individual-flare-volume-estimates.csv     # World Bank dataset
│    └── 📄 eog_global_flare_survey_2015_flare_list.csv         # Visible Infrared Imaging Radiometer Suite (VIIRS) dataset
├── 📁 output/                                                  # Folder for generated output files  
│    ├── 📄 analysis_results.txt                                # Results from GoLang script  
│    ├── 📄 combined_dataset.csv                                # Combined dataset after clustering and averaging  
│    └── 📄 dangling_viirs.csv                                  # Dangling rows from VIIRS dataset  
├── 📄 README.md                                                # Contains this readme file  
├── 📄 code.go                                                  # GoLang script  
└── 📄 gas_analysis.exe                                         # Executable script of GoLang script  
```

## Coursework Description

### Background
According to the World Bank, "Gas flaring is the burning of the natural gas associated with oil extraction". The practice is a byproduct of oil production and has persisted for over 160 years. Gas flaring has a significant impact on the environment; In 2023, oil production sites around the world burned about 148 billion cubic meters of gas through flaring, with each cubic meter of gas burned producing 2.6 kilograms of CO<sub>2</sub> equivalent emissions. This adds up to more than 350 million tons of CO<sub>2</sub>-equivalent emissions every year!

### Dataset Description
The following datasets are used in this analysis:
  - `2012-2023-individual-flare-volume-estimates.csv` (World Bank dataset) – This is the 'definitive truth'.
  - `eog_global_flare_survey_2015_flare_list.csv` (VIIRS satellite dataset) – This contains flare site measurements.
The country of interest is Algeria, and you are looking to understand how flaring has evolved from 2015 to 2019 across all sites with data from both dates. However, there is uncertainty around how the two files can be consolidated. Hence, your role, as a data scientist, is to use the information in both files to deliver a representative view.

### Task
You are asked to write the code in a language called GoLang. As this language is not taught at uni, you can use generative AI with appropriate prompt engineering to generate the code. You are required to annotate and validate the code to provide confidence in the results. Hence:
  1. Explore the variables in the files.
  2. Slice the data such that you only have flaring sites from Algeria.
  3. Join the files using flare location with the World Bank dataset as the primary location. As the measures are subject to random error, use clustering such that any flares within a Euclidean distance of 3km would belong to the same location. Use averages to combine the records.
  4. Explore resulting dataset. Devise a strategy on how you would deal with records that do not match (these are called dangling rows).
  5. Use resulting dataset to create a regression model to explain flaring volume in 2019 using the dataset you created in Step 3.
  6. State your observations of gas flaring in 2019 compared to 2015.

## How to Run the GoLang Code File (`code.go`)

### Option 1: Clone the Repository Locally and Run
1. Install GoLang:  
   ```
   https://go.dev/doc/install
   ```
2. Clone the Repository:
   ```
   git clone https://github.com/Next-Generation-Data-Science/Coursework-2.git
   ```
3. Navigate to the project directory:
   ```
   cd Coursework-2
   ```
4. Run the GoLang script:
   ```
   go run code.go
   ```
5. View Outputs:
     - 📄 `analysis_results.txt`: Results from GoLang script
     - 📄 `combined_dataset.csv`: Combined dataset after clustering and averaging
     - 📄 `dangling_viirs.csv`: Dangling rows from VIIRS dataset

### Option 2: Run in GitHub Codespaces
1. If you are a Collaborator:
    1. Click the `<> Code` button at the top right of the repository page.
    2. Select `Open with CodeSpaces`.
    3. Once the CodeSpace opens, run the GoLang script by opening a terminal and running:
       ```
       go run code.go
       ```
    4. The output will appear in the terminal.
2. If you are not a Collaborator:
    1. Forking:
        1. Click `Fork` in the top right of the repository page.
        2. In the forked version:
            1. Click the `<> Code` button at the top right of the repository page.
            2. Select `Open with CodeSpaces`.
            3. Once the CodeSpace opens, run the GoLang script by opening a terminal and running:
               ```
               go run code.go
               ```
        3. The output will appear in the terminal.
    2. Pre-Configured Codespace Link:
        1. Use the following link: https://codespaces.new/Next-Generation-Data-Science/Coursework-2
        2. Click the `Create codespace` button.
        3. Once the CodeSpace opens, run the GoLang script by opening a terminal and running:
           ```
           go run code.go
           ```
        4. The output will appear in the terminal.

## How to Run the GoLang Executable File (`gas_analysis.exe`)
1. Download a local copy of `gas_analysis.exe`.
2. Run the file by double-clicking it.
3. This will produce three files:
    - 📄 `analysis_results.txt`: Results from GoLang script
    - 📄 `combined_dataset.csv`: Combined dataset after clustering and averaging
    - 📄 `dangling_viirs.csv`: Dangling rows from VIIRS dataset
