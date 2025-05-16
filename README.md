# Carbon-Emission-Analysis
## Overview
This report analyzes carbon emissions across industries, countries, and years to identify the highest-emitting sectors and related trends. The goal is to understand the environmental impact of each industry to support sustainable development decisions.
## Data Overview
The dataset consists of 4 tables containing information regarding carbon emissions generated during the production of goods.
### Table 'product_emissions'
Column Name  | Description
------------- | -------------
id  | Identifier for each product emission record.  
company_id  | Identifier for the company associated with the product.  
country_id  | Identifier for the country where the product is being produced.
industry_group_id  | Identifier for the industry group to which the product belongs.  
year  | The year in which the emissions data was recorded.  
product_name  | The name of the product associated with the emissions data.
weight_kg  | The weight of the product in kilograms.  
carbon_footprint_pcf  | The carbon footprint of the product, measured in CO2 equivalent. 
upstream_percent_total_pcf  | The percentage of the total carbon footprint attributed to upstream activities.  
operations_percent_total_pcf  | The percentage of the total carbon footprint attributed to operations. 
downstream_percent_total_pcf  | The percentage of the total carbon footprint attributed to downstream activities.
<pre>SELECT * FROM product_emissions 
LIMIT 10;</pre>
| id            | company_id | country_id | industry_group_id | year | product_name                                                    | weight_kg | carbon_footprint_pcf | upstream_percent_total_pcf                       | operations_percent_total_pcf                     | downstream_percent_total_pcf                     | 
| ------------: | ---------: | ---------: | ----------------: | ---: | --------------------------------------------------------------: | --------: | -------------------: | -----------------------------------------------: | -----------------------------------------------: | -----------------------------------------------: | 
| 10056-1-2014  | 82         | 28         | 2                 | 2014 | Frosted Flakes(R) Cereal                                        | 0.7485    | 2                    | 57.50                                            | 30.00                                            | 12.50                                            | 
| 10056-1-2015  | 82         | 28         | 15                | 2015 | "Frosted Flakes, 23 oz, produced in Lancaster, PA (one carton)" | 0.7485    | 2                    | 57.50                                            | 30.00                                            | 12.50                                            | 
| 10222-1-2013  | 83         | 28         | 8                 | 2013 | Office Chair                                                    | 20.68     | 73                   | 80.63                                            | 17.36                                            | 2.01                                             | 
| 10261-1-2017  | 14         | 16         | 25                | 2017 | Multifunction Printers                                          | 110       | 1488                 | 30.65                                            | 5.51                                             | 63.84                                            | 
| 10261-2-2017  | 14         | 16         | 25                | 2017 | Multifunction Printers                                          | 110       | 1818                 | 25.08                                            | 4.51                                             | 70.41                                            | 
| 10261-3-2017  | 14         | 16         | 25                | 2017 | Multifunction Printers                                          | 110       | 2274                 | 20.05                                            | 3.61                                             | 76.34                                            | 
| 10324-1-2016  | 15         | 16         | 19                | 2016 | KURALON  fiber                                                  | 1500      | 10000                | N/a (product with insufficient stage-level data) | N/a (product with insufficient stage-level data) | N/a (product with insufficient stage-level data) | 
| 10418-1-2013  | 84         | 9          | 19                | 2013 | Portland Cement                                                 | 1000      | 1102                 | N/a (product with insufficient stage-level data) | N/a (product with insufficient stage-level data) | N/a (product with insufficient stage-level data) | 
| 10661-10-2014 | 85         | 28         | 11                | 2014 | Regular Straight 505® Jeans – Steel (Water                      | 0.7665    | 15                   | N/a (product with insufficient stage-level data) | N/a (product with insufficient stage-level data) | N/a (product with insufficient stage-level data) | 
| 10661-10-2015 | 85         | 28         | 6                 | 2015 | Regular Straight 505® Jeans – Steel (Water                      | 0.7665    | 15                   | N/a (product with insufficient stage-level data) | N/a (product with insufficient stage-level data) | N/a (product with insufficient stage-level data) | 
### Table 'industry_groups'
Column Name  | Description
------------- | -------------
id  | Unique identifier for each industry group. 
industry_group  | The name of the industry group, categorizing businesses within similar sectors based on their products or services offered.
<pre>SELECT * FROM industry_groups
LIMIT 10;</pre>
| id | industry_group                                                         | 
| -: | ---------------------------------------------------------------------: | 
| 1  | "Consumer Durables, Household and Personal Products"                   | 
| 2  | "Food, Beverage & Tobacco"                                             | 
| 3  | "Forest and Paper Products - Forestry, Timber, Pulp and Paper, Rubber" | 
| 4  | "Mining - Iron, Aluminum, Other Metals"                                | 
| 5  | "Pharmaceuticals, Biotechnology & Life Sciences"                       | 
| 6  | "Textiles, Apparel, Footwear and Luxury Goods"                         | 
| 7  | Automobiles & Components                                               | 
| 8  | Capital Goods                                                          | 
| 9  | Chemicals                                                              | 
| 10 | Commercial & Professional Services                                     | 
### Table 'companies'
Column Name  | Description
------------- | -------------
id  | Unique identifier for each company.
company_name  | The name of the company, identifying the specific organization within the dataset.
<pre>SELECT * FROM companies
LIMIT 10;</pre>
| id | company_name                                   | 
| -: | ---------------------------------------------: | 
| 1  | "Autodesk, Inc."                               | 
| 2  | "Casio Computer Co., Ltd."                     | 
| 3  | "Cisco Systems, Inc."                          | 
| 4  | "CNX Coal Resources, LP"                       | 
| 5  | "Coca-Cola Enterprises, Inc."                  | 
| 6  | "Compañía Española de Petróleos, S.A.U. CEPSA" | 
| 7  | "Daikin Industries, Ltd."                      | 
| 8  | "Elitegroup computer systems co., Ltd."        | 
| 9  | "Fuji Xerox Co., Ltd."                         | 
| 10 | "Gamesa Corporación Tecnológica, S.A."         | 
### Table 'countries'
Column Name  | Description
------------- | -------------
id  | Unique identifier for each country.
country_name  | The name of the country.
<pre>SELECT * FROM countries
LIMIT 10;</pre>
| id | country_name | 
| -: | -----------: | 
| 1  | Australia    | 
| 2  | Belgium      | 
| 3  | Brazil       | 
| 4  | Canada       | 
| 5  | Chile        | 
| 6  | China        | 
| 7  | Colombia     | 
| 8  | Finland      | 
| 9  | France       | 
| 10 | Germany      | 
## Analysis
### 1. Which products contribute the most to carbon emissions?
<pre>select product_name, carbon_footprint_pcf
from product_emissions
order by carbon_footprint_pcf desc
limit 3;</pre>
| product_name                 | carbon_footprint_pcf | 
| ---------------------------: | -------------------: | 
| Wind Turbine G128 5 Megawats | 3718044              | 
| Wind Turbine G132 5 Megawats | 3276187              | 
| Wind Turbine G114 2 Megawats | 1532608              |
### 2. What are the industry groups of these products?
<pre>SELECT pe.product_name, ig.industry_group, pe.carbon_footprint_pcf
FROM product_emissions pe
JOIN industry_groups ig ON pe.industry_group_id = ig.id
ORDER BY pe.carbon_footprint_pcf DESC
LIMIT 3;</pre>
| product_name                 | industry_group                     | carbon_footprint_pcf | 
| ---------------------------: | ---------------------------------: | -------------------: | 
| Wind Turbine G128 5 Megawats | Electrical Equipment and Machinery | 3718044              | 
| Wind Turbine G132 5 Megawats | Electrical Equipment and Machinery | 3276187              | 
| Wind Turbine G114 2 Megawats | Electrical Equipment and Machinery | 1532608              | 
### 3. What are the industries with the highest contribution to carbon emissions?
<pre>SELECT ig.industry_group, ROUND(SUM(pe.carbon_footprint_pcf), 2) AS total_emissions
FROM product_emissions pe
JOIN industry_groups ig ON pe.industry_group_id = ig.id
GROUP BY ig.industry_group
ORDER BY total_emissions DESC
Limit 10;</pre>
| industry_group                                   | total_emissions | 
| -----------------------------------------------: | --------------: | 
| Electrical Equipment and Machinery               | 9801558.00      | 
| Automobiles & Components                         | 2582264.00      | 
| Materials                                        | 577595.00       | 
| Technology Hardware & Equipment                  | 363776.00       | 
| Capital Goods                                    | 258712.00       | 
| "Food, Beverage & Tobacco"                       | 111131.00       | 
| "Pharmaceuticals, Biotechnology & Life Sciences" | 72486.00        | 
| Chemicals                                        | 62369.00        | 
| Software & Services                              | 46544.00        | 
| Media                                            | 23017.00        | 
### 4. What are the companies with the highest contribution to carbon emissions?
<pre>SELECT c.company_name, ROUND(SUM(pe.carbon_footprint_pcf), 2) AS total_emissions
FROM product_emissions pe
JOIN companies c ON pe.company_id = c.id
GROUP BY c.company_name
ORDER BY total_emissions DESC
LIMIT 10;</pre>
| company_name                            | total_emissions | 
| --------------------------------------: | --------------: | 
| "Gamesa Corporación Tecnológica, S.A."  | 9778464.00      | 
| Daimler AG                              | 1594300.00      | 
| Volkswagen AG                           | 655960.00       | 
| "Mitsubishi Gas Chemical Company, Inc." | 212016.00       | 
| "Hino Motors, Ltd."                     | 191687.00       | 
| Arcelor Mittal                          | 167007.00       | 
| Weg S/A                                 | 160655.00       | 
| General Motors Company                  | 137007.00       | 
| "Lexmark International, Inc."           | 132012.00       | 
| "Daikin Industries, Ltd."               | 105600.00       | 
### 5. What are the countries with the highest contribution to carbon emissions?
<pre>SELECT co.country_name, ROUND(SUM(pe.carbon_footprint_pcf), 2) AS total_emissions
FROM product_emissions pe
JOIN countries co ON pe.country_id = co.id
GROUP BY co.country_name
ORDER BY total_emissions DESC
LIMIT 10;</pre>
| country_name | total_emissions | 
| -----------: | --------------: | 
| Spain        | 9786130.00      | 
| Germany      | 2251225.00      | 
| Japan        | 653237.00       | 
| USA          | 518381.00       | 
| South Korea  | 186965.00       | 
| Brazil       | 169337.00       | 
| Luxembourg   | 167007.00       | 
| Netherlands  | 70417.00        | 
| Taiwan       | 62875.00        | 
| India        | 24574.00        | 
### 6. What is the trend of carbon footprints (PCFs) over the years?
<pre>SELECT year, ROUND(SUM(carbon_footprint_pcf), 2) AS total_emissions
FROM product_emissions
GROUP BY year
ORDER BY year;</pre>
| year | total_emissions | 
| ---: | --------------: | 
| 2013 | 503857.00       | 
| 2014 | 624226.00       | 
| 2015 | 10840415.00     | 
| 2016 | 1640182.00      | 
| 2017 | 340271.00       | 
### 7. Which industry groups has demonstrated the most notable decrease in carbon footprints (PCFs) over time?




