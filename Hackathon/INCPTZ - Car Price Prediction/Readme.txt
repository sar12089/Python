Inceptez - Care Price Prediction

Problem: Predict the car price

Preprocessing:
1. Load train/test, replace the column names with valid name using metadata file for better understanding about the data
2. Only 4 columns have NaN
	* GearBoxType - Replaced NaN with Mode
	* TypeOfTheFuelUsed - Using "NameOfTheVehicle" derived for few. For others, replaced NaN with Mode
	* VehicleType - Replaced NaN with Mode
	* IsDamageRepaired - Replaced NaN with Mode
3. Converted Date like columns to DateTime dtype
4. Derived new metric "DaydiffAd", to find the number of days between Ad last creation date and last seen
5. Derived "DistranceTravelledmod" metrics form "DistranceTravelledmod" and Convered "DistranceTravelled" as Object for converting it as category
6. From "YearOfVehicleRegistration" and "MonthOfVehicleRegistration" - derived "DateofReg"
7. From "DateOfAdCreation" and "DateofReg" - derived "Usage"
8. From "PowerOfTheEngine" , derived "PowerOfTheEnginecat", by splitting it into 4 categories
9. Removed Date fields, 'ZipCode','OfferType','SellerType','NameOfTheVehicle','NumberOfPictures'
10. Converted Categorical columns to One Hot
11. Separated Train and Test files

Modelling:
Using Random Forest, Identified value added features and used the same features for all modelling

1. Random Forest
	Train MAPE : 0.27%
	Test MAPE : 0.29%

2. Ada Boost
	Train MAPE : 0.77%
	Test MAPE : 0.77%

3. Linear Regression:
	Train MAPE : 0.46%
	Test MAPE : 0.46%

4. Linear - Ridge:
	Train MAPE : 0.46%
	Test MAPE : 0.46%

5. Linear - Laszo:
	Train MAPE : 0.48%
	Test MAPE : 0.48%

6. Linear - ElasticNet:
	Train MAPE : 0.46%
	Test MAPE : 0.46%
