# Steam Games Analysis

## Overview
This project explores a large dataset of games listed on the Steam platform using Python and Pandas. The notebook reads the data, fixes a column alignment problem in the file, removes columns with too many missing values, creates new columns, and visualizes how many games were released each year and which operating systems the games support.

## Dataset
Steam Games Dataset (Kaggle): https://www.kaggle.com/datasets/fronkongames/steam-games-dataset

File used: `games.csv`

- About **130,100 games**
- **39 columns** in the original file, including `AppID`, `Name`, `Release date`, `Estimated owners`, `Peak CCU`, `Required age`, `Price`, `Windows`, `Mac`, `Linux`, `Metacritic score`, `User score`, `Positive` and `Negative`

## Files in this Repository
| File | Description |
|------|-------------|
| `4SF25CI116_3A.ipynb` | Python notebook with all the code and outputs |
| `games.csv` | Dataset used for the analysis |
| `README.md` | Project overview |

## Steps Performed
1. **Reading the data:** loaded `games.csv` into a Pandas DataFrame.
2. **Understanding the data:** checked the columns, summary statistics (`describe()`), data types (`info()`) and null values (`isnull().sum()`).
3. **Fixing misaligned columns:** the values of the first seven columns (`AppID` to `Price`) were shifted one position to the left, so `AppID` held game names. The values were moved one position to the right, and `AppID` was rebuilt from the DataFrame index.
4. **Dropping unnecessary columns:** removed `Reviews`, `Metacritic url`, `Score rank`, `Movies`, `Website`, `Support url` and `Notes` because they have many missing values.
5. **Adding new columns:**
   - `Is Free`: `True` if the game's price is 0, otherwise `False`.
   - `Release_year`: the year taken from the release date.
6. **Changing the data type:** converted `Release date` to datetime format.
7. **Visualization:** created the two charts listed below.

## Visualizations
- **Games released per year:** a bar chart of the number of games for each release year.
- **Game platform distribution:** a pie chart showing how many games support Windows, Mac and Linux.

## Tools Used
- Python
- Pandas
- Matplotlib
- Seaborn

## How to Run
1. Download `games.csv` from the Kaggle link above and keep it in the same folder as the notebook.
2. Install the libraries:
   ```
   pip install pandas matplotlib seaborn notebook
   ```
3. Open the notebook in Jupyter and run the cells from top to bottom.
