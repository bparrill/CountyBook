# USA County Coloring Book
Maps of counties are available from the [US Census](https://www2.census.gov/geo/maps/general_ref/stco_outline/cen2k_pgsz/).  This project uses [stco_2000.pdf](https://www2.census.gov/geo/maps/general_ref/stco_outline/cen2k_pgsz/stco_2000.pdf) which contains all states and territories.

A list of counties is available from the [US Census](https://www.census.gov/data/datasets/time-series/demo/popest/2020s-counties-total.html).  This project uses [co-est2021-pop.xlsx](https://www2.census.gov/programs-surveys/popest/tables/2020-2021/counties/totals/co-est2021-pop.xlsx) which is a list of all counties in all states.

**NOTE:** There were some discrepencies with the county list for Alaska and the map of Alaska. For more information, see this: [https://www.census.gov/programs-surveys/geography/technical-documentation/county-changes.2010.html](https://www.census.gov/programs-surveys/geography/technical-documentation/county-changes.2010.html)

`qpdf` was used to combine the map file and the county lists:

```
qpdf  --empty --collate --pages stco_2000.pdf CountyTables.pdf -- CountyColor.pdf
```

Add cover page:

```
qpdf --empty --pages CoverPage.pdf CountyColor.pdf -- CountyColorWTitle..pdf
```

To do:
* Add Canada, World
* Fix Alaska
