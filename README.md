# LSTM_Hydrologic_Model
A LSTM (Long Short-Term Memory) Model is trained for rainfall-runoff forecast for ~480 catchments in Pacific Northwest and South Atlantic States.

## Dataset selected
The dataset used in for this study is HYSETS (https://osf.io/rpc3w/), which encompasses comprehensive hydrological modeling data across 14425 catchments in North America, spanning
from 1950 to 2020. The database includes catchment properties, hydro-metric gauging station discharge time-series and other meteorological data.

For this study, two areas of focus were selected. One in Pacifi c Northwest (near Washington, Oregon, US, and BC, Canada); the other in southeast Atlantic Coast (near Georgia, Alabama). Each of these are contains ~240 watersheds. In light of the fact that smaller catchments can display highly variable hydrological responses due to their limited area and more direct runoff processes, watersheds with area <200km<sup>2</sup> have been removed to ensure homogeneity. This reduces the number of watersheds for Pacific and Atlantic to 183 and 182 respectively.
![extent](https://github.com/user-attachments/assets/3ee0d471-18e2-4c92-ac94-3e1b320fdb66)

The dataset is separated into Train, Validation and Test set.  The test set contains an ‘Unseen’ and a ‘Seen’ subset. The ’Unseen’ subset is comprised of records from catchments that were not included in the training dataset, providing a basis for testing the model’s generalizability. Conversely, the ’Seen’ subset includes the final quarter of datafrom certain catchments, sorted by date.  The initial three-quarters of data from these ’Seen’ catchments have been utilized in either the training or validation sets. We also separated another 20% of data as Validation set to be used for hyperparameter tuning and the rest 60% was used for training.

## PyTorch mode
Two LSTM model from PyTorch is trained for runoff estimation, for the atlantic and pacific watersheds. Initial trials indicated that the LSTM model performed similarly with window sizes of 5 and 15 days; therefore, the smaller window size was selected to enhance training efficiency (a longer period like 365 days may also brings signficiant difference, but is yet to be explored). The input matrix includes meterological data, static catchment attributes, and daily peak flow, with a window size of 5 days. The output is a one day runoff forecast of flow for day t+1. Hyperparameters tuning and a qualitative assessment by visual inspection is conducted, to identify any systematic errors or biases in the predictions. For more details may prefer to the Jupyter Notebook developed.

## Results
The LSTM model demonstrated strong predictive capacities on the validation set. The model is then applied to the unseen test set (other watersheds in the same region), we were able to achieve a mean NSE of 0.75 for Atlantic and 0.89 for Pacific, which is considered as a good hydrologic prediction model.
