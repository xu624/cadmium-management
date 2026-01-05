This repo contains files used for the data analysis on Cd risks in croplands in China.
It belongs to the Manuscript `Large-scale nutrient management strategies shape acidification-induced risks for crop yields and food quality by cadmium`

Authors: Donghao Xu<sup>1,2</sup>, Gerard H. Ros<sup>1</sup>, Pengqi Liu<sup>2</sup>, Qichao Zhu<sup>2</sup>, Fusuo Zhang<sup>2</sup>, Wim de Vries<sup>1</sup>

<sup>1</sup> Wageningen University and Research, Earth Systems and Global Change Group, PO Box 47, 6700AA Wageningen, the Netherlands 
<sup>2</sup> College of Resources and Environmental Sciences; National Academy of Agriculture Green Development, China Agricultural University, 100193 Beijing, China

Corresponding authors are qichaozhu@126.com; donghao.xu@wur.nl 

Cd_dynamics.Rmd describes the script for regression models, cadmium dynamics simulation, and scenario analysis, together with data analysis and visualization. 

The datasets supporting the findings of this study, including cadmium model inputs and outputs, scenario analysis datasets, and source data underlying the main and Extended Data figures are stored in folder Data, including:

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

 The folder Figure_Source_Data contains the raw data underlying all Figures (Fig) and Extended Data Figures (EDFig) in the Manuscript