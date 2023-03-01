# Waste Diversion in Canada
I’ve analyzed [Waste materials diverted data](https://www150.statcan.gc.ca/t1/tbl1/en/tv.action?pid=3810013801) published by Statistics Canada for 2018 and 2020 years and built [dashboard](https://public.tableau.com/app/profile/angela6018/viz/WasteDiversionCanada/WasteDiversion) on top of it.

## Tools used
- Python 3.8 (pandas, io, requests)
- Tableau Public

## Data cleaning
Report contains data for each province and whole Canada split by residential and non-residential source. Some types of material lack information about the source (e.g., the source is not tracked or the value is suppressed to meet the confidentiality requirements of the Statistics Act). 

During the data cleaning step, I created an "Unknown source" category and assigned it to the material types where the source wasn't clearly identified. Because some values are suppressed but still included in the total of all materials diverted, the sum of all sources is less than the value of all materials diverted. Therefore, I calculated the unknown source value for all materials by subtracting the residential and non-residential source from the total diverted value.

## Visualisation
I exported clean data to [waste_can.csv](/waste_can.csv) file and used it as a data source for [Tableau dashboard](https://public.tableau.com/app/profile/angela6018/viz/WasteDiversionCanada/WasteDiversion).

## Conclusion
In 2020, there were 352 tonnes more diverted waste than in 2018. 52% of this waste came from residential sources, 42% from non-residential sources, and 10% had an unknown source.

67% of diverted materials are paper and organics. 

Although, there are some outliers:

- 52% of diverted materials in Yukon, Northwest Territories and Nunavut are ferrous metals and construction waste. 50% of diverted waste here came from non-residential sources.

- Saskatchewan diverted approximately the same amount of paper and organics (43%) and tires and ferrous metals (39%)

However, the absolute values in these provinces are insignificant, so they do not skew the final results.

80% of diverted materials come from Ontario (35%), Quebec (26%) and British Columbia (19%).

It would be interesting to research not only the amount of diverted waste, but also the proportion of diversion from total disposal of waste. That is a topic for further research.
