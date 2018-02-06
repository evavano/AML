# Metadata

***
This table represents the number of earthquakes in the United States from 2000 to 2010. 

The United States Geological Survey (USGS) detects but does not generally locate mine blasts (explosions) throughout the United States on any given business day. For more information, see “Routine United States Mining Seismicity.” [Click here for information on “Top Earthquake States,”](http://earthquake.usgs.gov/earthquakes/states/top_states.php)

**Data source**: [U.S. Geological Survey, Earthquake Facts and Statistics](http://earthquake.usgs.gov/earthquakes/eqarchives)


### Data cleaning in OpenRefine

1) Transfer values to numbers
2) Removing column names from data rows 
3) Adding column names
4) Removing al collumsn and rows with no data or metadata
5) creating this metadata file

Datacleaning openRefine JSON code:

[
  {
    "op": "core/text-transform",
    "description": "Text transform on cells in column Column 13 using expression value.toNumber()",
    "engineConfig": {
      "mode": "row-based",
      "facets": []
    },
    "columnName": "Column 13",
    "expression": "value.toNumber()",
    "onError": "keep-original",
    "repeat": false,
    "repeatCount": 10
  },
  {
    "op": "core/text-transform",
    "description": "Text transform on cells in column Column 12 using expression value.toNumber()",
    "engineConfig": {
      "mode": "row-based",
      "facets": []
    },
    "columnName": "Column 12",
    "expression": "value.toNumber()",
    "onError": "keep-original",
    "repeat": false,
    "repeatCount": 10
  },
  {
    "op": "core/column-rename",
    "description": "Rename column Table with row headers in column A and column headers in rows 4.  Leading dots indicate sub-parts. to Magnitude",
    "oldColumnName": "Table with row headers in column A and column headers in rows 4.  Leading dots indicate sub-parts.",
    "newColumnName": "Magnitude"
  },
  {
    "op": "core/column-rename",
    "description": "Rename column Column 2 to 2000",
    "oldColumnName": "Column 2",
    "newColumnName": "2000"
  },
  {
    "op": "core/column-rename",
    "description": "Rename column Column 3 to 2001",
    "oldColumnName": "Column 3",
    "newColumnName": "2001"
  },
  {
    "op": "core/column-rename",
    "description": "Rename column Column 4 to 2003",
    "oldColumnName": "Column 4",
    "newColumnName": "2003"
  },
  {
    "op": "core/column-rename",
    "description": "Rename column 2003 to 2002",
    "oldColumnName": "2003",
    "newColumnName": "2002"
  },
  {
    "op": "core/column-rename",
    "description": "Rename column Column 5 to 2003",
    "oldColumnName": "Column 5",
    "newColumnName": "2003"
  },
  {
    "op": "core/column-rename",
    "description": "Rename column Column 6 to 2004",
    "oldColumnName": "Column 6",
    "newColumnName": "2004"
  },
  {
    "op": "core/column-rename",
    "description": "Rename column Column 7 to 2005",
    "oldColumnName": "Column 7",
    "newColumnName": "2005"
  },
  {
    "op": "core/column-rename",
    "description": "Rename column Column 8 to 2006",
    "oldColumnName": "Column 8",
    "newColumnName": "2006"
  },
  {
    "op": "core/column-rename",
    "description": "Rename column Column 9 to 2007",
    "oldColumnName": "Column 9",
    "newColumnName": "2007"
  },
  {
    "op": "core/column-rename",
    "description": "Rename column Column 10 to 2008",
    "oldColumnName": "Column 10",
    "newColumnName": "2008"
  },
  {
    "op": "core/column-rename",
    "description": "Rename column Column 11 to 2009",
    "oldColumnName": "Column 11",
    "newColumnName": "2009"
  },
  {
    "op": "core/column-rename",
    "description": "Rename column Column 12 to 2010\\",
    "oldColumnName": "Column 12",
    "newColumnName": "2010\\"
  },
  {
    "op": "core/column-rename",
    "description": "Rename column Column 14 to 1974-2003",
    "oldColumnName": "Column 14",
    "newColumnName": "1974-2003"
  },
  {
    "op": "core/column-rename",
    "description": "Rename column Column 13 to Top earthquake states",
    "oldColumnName": "Column 13",
    "newColumnName": "Top earthquake states"
  },
  {
    "op": "core/row-removal",
    "description": "Remove rows",
    "engineConfig": {
      "mode": "row-based",
      "facets": [
        {
          "omitError": false,
          "expression": "value",
          "selectBlank": true,
          "selection": [],
          "selectError": false,
          "invert": false,
          "name": "2000",
          "omitBlank": false,
          "type": "list",
          "columnName": "2000"
        }
      ]
    }
  },
  {
    "op": "core/row-removal",
    "description": "Remove rows",
    "engineConfig": {
      "mode": "row-based",
      "facets": [
        {
          "omitError": false,
          "expression": "value",
          "selectBlank": false,
          "selection": [
            {
              "v": {
                "v": "Magnitude",
                "l": "Magnitude"
              }
            }
          ],
          "selectError": false,
          "invert": false,
          "name": "Magnitude",
          "omitBlank": false,
          "type": "list",
          "columnName": "Magnitude"
        }
      ]
    }
  },
  {
    "op": "core/column-rename",
    "description": "Rename column 2010\\ to 2010",
    "oldColumnName": "2010\\",
    "newColumnName": "2010"
  },
  {
    "op": "core/column-rename",
    "description": "Rename column Top earthquake states to Top_earthquake_states",
    "oldColumnName": "Top earthquake states",
    "newColumnName": "Top_earthquake_states"
  },
  {
    "op": "core/column-rename",
    "description": "Rename column 1974-2003 to 1974_2003",
    "oldColumnName": "1974-2003",
    "newColumnName": "1974_2003"
  }
]
