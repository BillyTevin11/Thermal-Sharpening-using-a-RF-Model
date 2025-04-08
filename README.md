# <ins>Thermal Sharpening Using a Random Forest Model</ins>

This project implements a _thermal sharpening_ technique using a _Random Forest (RF) machine learning model_ in the Google Earth Engine (EE) environment. The primary goal is to enhance the spatial resolution of coarse thermal imagery (1km resolution from MODIS) by leveraging higher-resolution optical data (250m resolution NDVI from MODIS).

Further, it outlines the need for thermal sharpening due to the inherent lower spatial resolution of thermal sensors compared to optical sensors on satellites like Landsat and MODIS. It briefly describes various thermal sharpening techniques, including regression-based, wavelet transform, HRV-NIR, and hybrid/AI-based methods, with a focus on the RF approach.

The RF model is employed to learn the statistical relationship between the lower-resolution thermal data (Land Surface Temperature - LST) and the higher-resolution optical data (Normalized Difference Vegetation Index - NDVI). 

**Key steps involved are:**

1. Data Collection and Preprocessing: Importing MODIS LST (1km) and NDVI (250m) data for a specified time period (2020-2021) and a user-defined Area of Interest (ROI) in Earth Engine.
2. Feature Selection: Using NDVI as the predictor variable and LST as the target variable.
3. Training the Random Forest Model: Splitting the 1km resolution LST and NDVI data into training (95%) and testing (5%) sets and training an RF regressor model.
4. Prediction & Thermal Sharpening: Using the trained RF model to predict high-resolution (250m) LST values based on the 250m resolution NDVI data.

The project then evaluates the performance of the RF model using metrics like _Root Mean Squared Error (RMSE)_ and _R-squared (R<sup>2</sup>)_. Finally, it visualizes the original 1km resolution LST and the sharpened 250m resolution LST side-by-side using _Matplotlib_, demonstrating the enhanced spatial detail achieved through the thermal sharpening process. The script utilizes the _ee, geemap, xarray, xee_, and _scikit-learn_ libraries for Earth Engine interaction, data manipulation, and machine learning.


