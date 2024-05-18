# GEOG5990 
# 1 ipynb use
The crime_rating.ipynb shows how to obtain the yearly crime data. Upload the crime dataset to run it first, then run the final_project.ipynb.
I have exported the crime_rating.csv and zipped it in the data file, so you do not have to download it and then upload to final_project.ipynb.

# 2 Data Source
1.1 boundaries data
  https://geoportal.statistics.gov.uk
1.2 crime data
  https://www.police.uk/pu/your-area/west-yorkshire-police/bradford-city/?yourlocalpolicingteam=about-us
1.3 Access to Health Assets Hazards data
  https://data.cdrc.ac.uk/dataset/access-healthy-assets-hazards-ahah-previous-versions
1.4 population density data
  https://www.nomisweb.co.uk/query/construct/summary.asp?mode=construct&version=0&dataset=2026
1.5 commute distance data
  https://www.nomisweb.co.uk/query/construct/summary.asp?mode=construct&version=0&dataset=2075
1.6 estate price data
  https://data.cdrc.ac.uk/dataset/dwelling-ages-and-prices

# 3 Data use
  LSOA11CD                      hpmd202103                 ahah                                                   ah3g                          
    code                       estate price          Health Domain Score                                 Green/Bluespace Domain Score   
   
    ah3e                           ah3r                   ah3ahah
Air quality Domain Score    Retail Domain Score     Access to Healthy Assets and Hazards index score

# 4 Topic
Is livable environment associated with population density in Bradford? is my topic. Take LSOAs’ crime rate, retail, access to health, greenspace, air quality, and commute time to measure the livability. First, population density will affect people’s quality of life (Cramer, Torgersen and Kringlen, 2004), disease transmission (Li, Richmond and Roehner, 2018), etc. One survey results show that people prefer to live in areas with large green areas, high air quality, many leisure areas, and low living costs (such as low rent), places with easy access to free medical services and low crime rate (Ülengin, Ülengin and Güvenç, 2001). According to this survey, the population density in livable areas will be larger, but people may feel crowded after the change.

# 5 Models
# 5.1 Analytical Hierarchy Process (AHP)
I used the AHP when I determined the weight of each index. This method can quantify the impact of each factor clearly. The weight is obtained by calculating the eigenvector of the evaluation matrix. It is a method that simulates the way people think in their decision-making process, so it can handle many practical problems. However, because it mainly starts from the evaluator's understanding of the nature of the evaluation problem, evaluation is relatively subjective. Different evaluators have different evaluation criteria for the same target. For example, A and B evaluate a bag. A focuses on price and quality, B focuses on appearance and lightness. Suppose comprehensiveness of the evaluation is to be ensured by adding evaluation factors. In that case, it is often difficult to determine the importance of each factor when the amount of data statistics is too large.
# 5.2 Pearson coefficient
I used the Pearson coefficient for non-spatial visualization to discuss the correlation between livable factors, livability level and population density. The advantage of Pearson is to analyze the linear relationship between two variables, so that the correlation can be highlighted directly. And also, factors that have lower correlation can be identified easily. Based on previous research, there is already a possible linear relationship between them, so I did not choose Spearman method. However, the data of my study is relatively small, so the estimation of the correlation may be unstable.
# 5.3 Quantiles
In terms of spatial clustering, I chose Quantiles to classify population density, which is a traditional method. Because it can express population density more intuitively. It ensures that each class contains approximately equal amounts of data, so population density can be identified by quantiles, with the larger the quantile, the greater the population density. But it requires customizing the number of bins, I used the Sturges' Formula to estimate as scientifically as possible, which calculates the number of bins (or categories) after knowing the total number of data in the dataset.

# Reference
Cramer, V., Torgersen, S. and Kringlen, E. 2004. Quality of life in a city: The effect of population density. Social indicators research. 69(1), pp. 103–116. 
Li, R., Richmond, P. and Roehner, B. M. 2018. Effect of population density on epidemics. Physica A. 510, pp. 713–724.
Ülengin, B., Ülengin, F. and Güvenç, Ü. 2001. A multidimensional approach to urban quality of life: The case of Istanbul. European journal of operational research. 130(2), pp. 361–374. 
