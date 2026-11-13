# EcoMove Mobility: Data Visualisation Project

A Python data visualisation investigation of urban public transport and shared mobility across twelve European cities, built for the COM7021 Data Visualisation module (MSc Data Science, Arden University Berlin).

The project turns 5,000 daily service records into a single decision-support story for senior managers: where demand is concentrated, whether services are reliable, whether reliability affects satisfaction, how demand is distributed across modes, and whether each mode is financially sustainable. It delivers six static visualisations and one interactive Streamlit dashboard.

## Dataset
### Item    -         Detail
File-	EcoMoveMobility.xlsx (sheet Dataset)

Records-	5,000 daily service summaries

Fields-	18 (operational, financial, environmental and satisfaction measures)

Coverage-	12 cities, 6 countries, 6 transport modes

Period-	1 January 2024 to 31 December 2025

Quality-	No missing values, no duplicate records

## Data preparation

The Date field is stored as Excel serial numbers and is converted to real datetimes, with a monthly period added for time-series aggregation.
Two engineered KPIs: Profit_EUR (ticket revenue minus operating cost) and Cost_Recovery (revenue divided by cost).
Demand is highly right-skewed (64 to 66,416 passengers per record), so a logarithmic scale and medians are used where appropriate.

The dataset is provided by the module. Place EcoMoveMobility.xlsx in the project folder before running the code.4

## The six visualisations

# Chart	Question it answers

1	Dual-axis area and line chart (time series)	Do ridership and punctuality move together over time?

2	Horizontal bar chart, coloured by country (comparison)	Which cities carry the most demand?

3	Masked correlation heatmap (relationship overview)	Which KPIs move together?

4	Scatter plot with trend line (relationship)	Does delay reduce customer satisfaction?

5	Violin and box plot on a log axis (distribution)	How is demand spread across modes?

6	Red/green KPI bar chart with break-even line (performance)	Which modes cover their operating costs?

Every figure uses a colour-blind-safe palette (Okabe-Ito), finding-led titles and labelled axes, following principles from Cleveland and McGill (1984), Tufte (2001) and Knaflic (2015).

## Previews

Figure 1: time series Figure 2: city comparison Figure 3: correlation heatmap Figure 4: delay vs rating Figure 5: demand distribution Figure 6: cost recovery

## Interactive dashboard

A Streamlit dashboard reproduces all six analyses in one view, with five KPI cards and four linked filters (city, transport mode, weather, date range) that update every panel at once.

Dashboard overview

## Intended users

1. Operations managers: monitor on-time performance and target interventions.
   
2. Network planners: match capacity to demand across cities and modes.
   
3. Finance and investment leads: see which services pay their way.

## Key findings

1. Demand is concentrated. Metro carries 63% of all passengers (more than all other modes combined). Berlin (about 11,000 per record) and Paris (about 10,600) lead; Lyon is lowest (about 6,500).
2. Reliability drives satisfaction. Delay and customer rating are strongly negatively correlated (r = -0.82).
3. Bus is the weakest operational link. Lowest on-time rate (74.9%), highest average delay (6.6 minutes) and lowest rating (3.74).
4. Micromobility does not recover its costs. Bike Share and E-Scooter recover only about 6% and 9% of operating costs, while Park and Ride (1.22), Tram (1.18), Metro (1.07) and Bus (1.01) cover theirs.
5. Network-wide: 45.4% of records run at a farebox loss, the two-year net result is roughly break-even (about -EUR 0.47m), and 4.48 kt of CO2 was saved.

## Limitations
1. Records are aggregated daily summaries, not individual trips.
2. Cost recovery uses ticket revenue only (no subsidy data), so "loss-making" means farebox loss-making.
3. Accessibility is only available as a complaint count.
4. Relationships are correlational, and two years of data limit long-term trend claims.

## Tools and libraries

Python, pandas, NumPy, Matplotlib, Seaborn, Plotly, Streamlit, openpyxl.

## References
Cairo, A. (2016) The Truthful Art. Berkeley, CA: New Riders.

Cleveland, W.S. and McGill, R. (1984) 'Graphical perception', Journal of the American Statistical Association, 79(387), pp. 531-554.

Few, S. (2012) Show Me the Numbers. 2nd edn. Burlingame, CA: Analytics Press.

Knaflic, C.N. (2015) Storytelling with Data. Hoboken, NJ: Wiley.

Tufte, E.R. (2001) The Visual Display of Quantitative Information. 2nd edn. Cheshire, CT: Graphics Press.

Wong, B. (2011) 'Points of view: Color blindness', Nature Methods, 8(6), p. 441.

## Author

Khalil Animashaun (2026), MSc Data Science, Arden University Berlin.
