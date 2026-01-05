This repo contains files used for the data analysis on Cd risks in croplands in China.
It belongs to the Manuscript `Large-scale nutrient management strategies shape acidification-induced risks for crop yields and food quality by cadmium`

Authors: Donghao Xu<sup>1,2</sup>, Gerard H. Ros<sup>1</sup>, Pengqi Liu<sup>2</sup>, Qichao Zhu<sup>2</sup>, Fusuo Zhang<sup>2</sup>, Wim de Vries<sup>1</sup>

<sup>1</sup> Wageningen University and Research, Earth Systems and Global Change Group, PO Box 47, 6700AA Wageningen, the Netherlands 
<sup>2</sup> College of Resources and Environmental Sciences; National Academy of Agriculture Green Development, China Agricultural University, 100193 Beijing, China

Corresponding authors are qichaozhu@126.com; donghao.xu@wur.nl 

Cd_dynamics.Rmd describes the script for regression models, cadmium dynamics simulation, and scenario analysis, together with data analysis and visualization. 

The folder model_data includes datasets supporting the findings of this study, including cadmium model inputs and outputs, scenario analysis datasets, including:

-all_observation.csv:
 Observations in the year of 2014 and 2019 for soil total cadmium content (SoilCd, mg/kg), soil organic carbon content (SOC, %) and soil pH (pH)
 Columns include: ID, Year, value, Variable.
  
-Cd_regression_data.csv:
 Raw data to derive the cadmium regression model for soil-crop and soil-solution relationships. 
 The definitions of the parameters (columns) are:
 * X: longtitude (WGS84, EPSG:4326)
 * Y: latitude (WGS84,  EPSG:4326)
 * land_use: land use type, as Paddy if the crop type is rice, otherwise Upland
 * pH: soil pH measured in water
 * SoilCdtot: Soil total Cd content in a 0-20cm soil layer (mg/kg)
 * RiceCd: Cd content in rice grain (mg/kg)
 * StrawCd: Cd content in rice straw (mg/kg)
 * SoilCdavi: Cd concentration in soil solution in a 0-20cm soil layer (μg/L)
 * OC: soil organic carbon content (%)
 * Clay: soil clay content in a 0-20cm soil layer (%)
 * source: clay content in some sites were measured (mea_clay), otherwise the values were derived from SoilGrids — global gridded soil information 
 * code: ID of the site
 * with_survey: if farm surveys were carried out at the sampled site (1 indicates with farm survey data)

-historical_Cd_input.csv:
 input data for cadmium flux simulation in the historical period (1985-2019)
 Columns include: 
 * site, ID, Year: identifiers for the samples and year
 * CEC: soil cation exchange capacity in the 0-20cm soil layer (meq/kg)
 * clay: soil clay content in the 0-20cm soil layer (%)
 * bulkdens: soil bulk density in the 0-20cm soil layer (kg/m3)
 * soil_type: indicate the soil is calcareous or non-calcareous soils
 * SOC: soil organic carbon content (%)
 * pH: soil pH measured in water
 * soilCd: soil total Cd content in a 0-20cm soil layer (mg/kg)
 * PS: mean annual precipitation surplus (m/year)
 * dep, irr, fer, man: annual mean cadmium input (g Cd /ha/year) from deposition, irrigation, mineral fertilizer and manure
 * rice_yield, straw_yield, straw_recy: the annual yield of rice grain and straw (t/ha) and the fraction of straw that recycled into the field (straw_recy)

-scenario_input_with_lime.csv:
 input data for different management scenario analysis (2020-2050)
 Columns are mostly same as histrocial_Cd_input.csv, additional parameters include:
 * lime: annual mean lime application rate (kg/ha/yr)
 * scenario: different management scenarios

 The folder spatial_data contains the spatial data underlying all maps in the Manuscript, with coordinate reference system of EPSG:4326
 * dep_irr.shp :
   Point-based deposition and irrigation samples in Qiyang Country in 2019. Value for deposition are in unit of g/ha/yr, for irrigaition are in unit of μg/L

 * Qiyang_county.shp:
   Boundary of Qiyang County.

 * rice_cover.tiff:
   Rice cultivation mask used to define interpolation grid at 1km * 1km.

 * soil_crop_2019.shp :
   Point-based soil-crop samples in Qiyang Country in 2019, including measured total soil and crop Cd content (SoilCdtot, RiceCd, StrawCd), soil avaiable Cd content (SoilCdavi), soil organic carbon content (OC, g/kg) and soil clay content (Clay, %), as well as if the samples were taken with survey data (with_survey = 1). 
   Columns include: X, Y, land_use, SoilCdtot, RiceCd, StrawCd, SoilCdavi, OC, Clay, source, code, with_survey

* spatial_deposition_Cd.shp :
  Point-based Cd input of atmospheric deposition (g ha−1 yr−1) used as input for spatial interpolation.
  Columns include: ID, X, Y, BNPR, BNPRLopt1, BNPRLopt2.
  where BNPRLopt1 indicates the option 1 in BNPRLopt scenario to prioritize reducing manure Cd input, and BNPRLopt2 indicates the option 2 in BNPRLopt scenario to prioritize reducing atmospheric deposition Cd input.

* spatial_lime.shp:
  Point-based mean lime input (ton ha−1) every 5 years during 2020-2050, used as input for spatial interpolation.
  Columns include: ID, X, Y, BNPRLopt1, BNPRLopt2.

* spatial_manure_Cd.shp 
  Point-based Cd input of manure (g ha−1 yr−1) used as input for spatial interpolation.
  Columns include: ID, X, Y, BNPR, BNPRLopt1, BNPRLopt2.

The folder Figure_Source_data contains source data underlying the main and Extended Data figures