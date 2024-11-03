<h1> Strawberries - Neem Oil : A Good pesticide and fertilizer?</h1>

<h2> Data Description</h2>

`strawberries25_v3.csv` contains the original data which is having following columns: 
1. Program - CENSUS, SURVEY
2. Year - 2022 etc.
3. Period - YEAR, YEAR - AUG FORECAST
4. Week Ending
5. Geo Level - COUNTY, STATE
6. State - Almbama, Florida etc.
7. State ANSI
8. AgDistrict
9. AgDistrict Code
10. County
11. County ANSI
12. Zip Code
13. Region
14. Watershed 
15. watershed_code
16. Commodity
17. Data Item
18. Domain
19. Domain Category
20. Value
21. CV (%)

Many of these columns were dropped due to having one values in them. 
<h2> Analysis</h2>

After cleaning the dataset, it was found that in the Value column there were a lot of NAs and observing the pattern, it was found that whenever there was `TOTAL` in the `Domain`, `Value` contained the sum of the previous  
values in the same group ( group decided based on `BEARING`, `NON-BEARING`etc. in the `BEARING TYPE` column). This pattern is observed everywhere execpt first two groups where difference of `1` was found from the total.
Hence, a function was created which would use the previous values to fill in NAs and where there was no value or group, it was filled with 0. 

It was also found that only two states : Florida and California had the chemical data. Upon observing what kind of chemicals were used in both the states, I was surprised to find `NEEM OIL` in the list followed by the  
`GARLIC OIL`, `CANOLA OIL` and `MUSTARD OIL`. More Surprinsingly, `NEEM OIL` was being used in California. California is one of largest strawberry producers in te US and quite evidently, use of chemicals is also one of  
main concerns people have for the Cali strawberries. `MUSTARD OIL` has a lot of controversy in INDIA as it is not so really good health. It is claimed to be source of many digestion related issues. Many companies in India  
faced backlash from the people due to using  `MUSTARD OIL`. But it is being used in `FLORIDA` - which made me have a far fetched spectulation - Is it due to presence of so many indians in the california that `NEEM OIL` is  
being used there but Mustard oil isn't? 
Also, Is `NEEM OIL` as good for the strawberries as it is claimed to be? Afterall, it has the most bitter taste.
  
<h2> Files Description</h2>

`USDA-NASS data cleaning Original.qmd` -  contains code which I submitted for the cleaning of strawberry dataset. It was an attempt to clean the whole dataset to some extent before it was split based on different creteria to observe  
different information such as CENSUS, SURVEY. But it was wrong step to take. It is to be noted that to some extent when dealing with large datasets, it is better to use divide and conquer.
`USDA-NADD data cleaning.qmd` -contains code submitted for the chemical analysis. This is improved version of Original approach which means that strawberry dataset is divided into different small datasets before cleaning. This approach  
does have its own disadvantages - doing some steps multiple times for different chunks which further tells us importance of creation of functions. 
`census_data.csv` - Census Data
`survey_data.csv` - Survey Data
`census_organic.csv` -  Census and Organic
`census_non_organic.csv` -  Census and Non Organic 
`survey_chemical.csv` -  Survey and Chemical
`survey_non_chemical.csv` -  Survey and Non-Chemical
`survey_fert.csv` - Survey and Fertilizer 
`survey_total.csv` - Survey and Total 
`strawberry_cleaneddata.csv` - Cleaned Strawberry dataset with original approach




