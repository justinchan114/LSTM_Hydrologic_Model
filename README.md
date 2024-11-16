# LSTM_Hydrologic_Model
A LSTM (Long Short-Term Memory) Model is trained for rainfall-runoff forecast for ~480 catchments in Pacific Northwest and South Atlantic States.

# Dataset selected
The dataset used in for this study is HYSETS (https://osf.io/rpc3w/), which encompasses comprehensive hydrological modeling data across 14425 catchments in North America, spanning
from 1950 to 2020. The database includes catchment properties, hydro-metric gauging station discharge time-series and other meteorological data.

For this study, two areas of focus were selected. One in Pacifi c Northwest (near Washington, Oregon, US, and BC, Canada); the other in southeast Atlantic Coast (near Georgia, Alabama). Each of these are contains ~240 watersheds. In light of the fact that smaller catchments can display highly variable hydrological responses due to their limited area and more direct runoff processes, watersheds with area <200km<sup>2</sup> have been removed to ensure homogeneity. This reduces the number of watersheds for Pacific and Atlantic to 183 and 182 respectively.
![extent](https://github.com/user-attachments/assets/3ee0d471-18e2-4c92-ac94-3e1b320fdb66)

