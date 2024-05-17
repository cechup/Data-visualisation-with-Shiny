# Data Visualization Project

## Overview
This project explores the impact of globalization on music, focusing on how diverse music genres have spread across the globe. Using data from Spotify and Musicbrainz APIs, we examine the rise of international music collaborations and the changing landscape of musical genres over time.

## Problem Characterization
Globalization is blending cultures and transforming various societal aspects, including music. The spread of genres like reggaeton, African beats, and American hip-hop in Europe and beyond illustrates this phenomenon. Our study aims to explore how globalization has facilitated these trends and led to collaborative creations among artists of different nationalities.

## Data Abstraction
Due to the unavailability of a comprehensive dataset online, we collected data using the Spotify API via the Spotipy interface and supplemented it with Musicbrainz API. We created several datasets:

1. **Artists Table**: Contains 1229 artists from Spotify's top 50 playlists (October) in the USA, UK, Italy, France, Argentina, Mexico, and Spain.
    - Columns: `ID`, `Name`, `Popularity`, `Country`, `Genre`

2. **Albums Table**: Contains 4782 albums or singles by the artists.
    - Columns: `ID`, `Name`, `Date`, `Main Artist`

3. **Songs Table**: Contains 27272 songs from the albums.
    - Columns: `ID`, `Name`, `Main Artist`, `Album ID`, `Album Name`, `Popularity`

4. **Featurings Table**: Contains 7497 rows of songs with featuring artists.
    - Columns: `SongID`, `Song Name`, `Artist1ID`, `Artist1Name`, `Artist2ID`, `Artist2Name`

To standardize genres, an additional `Main Genre` column was included in the artists' dataset.

## Interaction and Visual Encoding
The ShinyApp provides three main analysis tools:

1. **Analysis of International Collaborations (Featuring) Over Time**:
    - Line charts display the number of international collaborations among artists from the USA, Latin America and the Caribbean, and Europe from 2000 to 2023.
    - Allows comparison of collaborations from different regions.
    
2. **Comparative Network Analysis**:
    - Network graphs illustrate artist collaborations, with nodes representing artists and edges representing collaborations.
    - Networks are color-coded by geographical origins (USA, Latin America and Caribbean, Europe) and allow for time period comparison.

3. **Bar Graph of Song Production by Genre**:
    - Bar charts show the number of songs released in various genres from 1977 to 2023.
    - Interactive elements allow users to explore changes in music trends over decades.

## Algorithmic Implementation

### Work Environment and Libraries
The project was developed in RStudio using the Shiny package. Other libraries used include:
- `shiny`
- `dplyr`
- `networkD3`
- `data.table`
- `countrycode`
- `lubridate`
- `ggplot2`
- `shinyjs`
- `forcats`

### Data Manipulation
1. **Reading Data**: CSV files were read using `fread`.
2. **Data Processing**: Added continent information using `countrycode`. Filtered and merged datasets to create final dataframes for visualization.
3. **Visualization Choices**: Shiny app allows users to select different idioms for analysis.

### Visualization Pages
1. **Line Chart Page**:
    - Displays the trend of musical collaborations over time using ggplot.

2. **Network Page**:
    - Interactive network graphs created using `forceNetwork` from `networkD3`, showing artist collaborations and their geographical origins.

3. **Bar Chart Page**:
    - Bar charts created using ggplot to display the frequency of songs by genre over time.

## Instructions to Run the Application

### Visualize Using shinyapps.io
The Shiny app is hosted on shinyapps.io and can be accessed [here](https://datavisualization-karla.shinyapps.io/data_visualization_project/).

### Run Locally
1. **Install R and RStudio**: Ensure you have the latest versions of R and RStudio installed.
2. **Install Necessary Libraries**:
    ```R
    install.packages("networkD3")
    install.packages("dplyr")
    install.packages("data.table")
    install.packages("countrycode")
    install.packages("shiny")
    install.packages("lubridate")
    install.packages("ggplot2")
    install.packages("shinyjs")
    install.packages("forcats")
    ```
3. **Prepare the Data**: Ensure the files `artist.csv`, `albums.csv`, `songs.csv`, `featurings.csv` are in the correct paths. Modify file paths in the script if necessary.
4. **Run the App**:
    - From the IDE: Open the app file in your IDE and click "Run App".
    - From the console: Use the command `shiny::runApp()`.
5. **Interact with the Application**: Use the app interface to select options and explore the visualizations.
6. **Troubleshooting**: Ensure all packages are installed, file paths are correct, and there is a stable internet connection for package installation.

## License
This project is licensed under the MIT License - see the LICENSE file for details.

## Authors
Cecilia Peccolo
Federico Paschetta
Karla Paola Gonzalez Romero
