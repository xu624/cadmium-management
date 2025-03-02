This repo contains files used for the data analysis on Cd risks in croplands in China.
It belongs to the Manuscript `Large-scale impacts of nutrient management strategies on acidification-induced risks for crop yields and food quality by cadmium`

Authors: Donghao Xu<sup>1,2</sup>, Gerard H. Ros<sup>1</sup>, Pengqi Liu<sup>2</sup>, Qichao Zhu<sup>2</sup>, Fusuo Zhang<sup>2</sup>, Wim de Vries<sup>1</sup>

<sup>1</sup> Wageningen University and Research, Earth Systems and Global Change Group, PO Box 47, 6700AA Wageningen, the Netherlands 
<sup>2</sup> College of Resources and Environmental Sciences; National Academy of Agriculture Green Development, China Agricultural University, 100193 Beijing, China

Corresponding authors are qichaozhu@126.com; donghao.xu@wur.nl 

The pri_Cd_data.csv stores raw data to derive the cadmium regression model for soil-crop and soil-solution relationships with the Rmarkdown file cadmium regression model.Rmd. 
The definitions of the parameters are:
* X: longtitude (WGS84, EPSG:4326)
* Y: latitude (WGS84,  EPSG:4326)
* land_use: land use type, as Paddy if the crop type is rice, otherwise Upland
* pH: soil pH measured in water
* SoilCdtot: Soil total Cd content in a 0-20cm soil layer
* RiceCd: Cd content in rice grain
* StrawCd: Cd content in rice straw
* SoilCdavi: Cd concentration in soil solution in a 0-20cm soil layer
* OC: soil organic carbon content
* Clay: soil clay content in a 0-20cm soil layer

source: clay content in some sites were measured, otherwise the values were derived from SoilGrids — global gridded soil information 
