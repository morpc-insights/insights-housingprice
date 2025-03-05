# Data Kit - Home prices and income

## Version

Current version: 2025-03-05

## Provider

  - Organization: [Mid-Ohio Regional Planning Commission](https://morpc.org)
  - Contact: 
    - Name: Adam Porr
	- E-mail: aporr@morpc.org
	- Phone: 614-233-4216

## Introduction

The Multiple Listing Service (MLS) is a database of real estate transactions that is used primarily by real estate agents to broker transactions, however the data is also useful in the aggregate to understand trends in home properties in geographies of interest.  Thanks to the cooperation of Columbus Realtors, MORPC was able to obtain MLS data to use for this purpose.  

This data kit is the final stage in a pipeline that retrieves, standardizes, and summarizes the MLS data. It produces a standardized dataset suitable for use in the MORPC Insights platform containing summary data for the MORPC 15-county region and the counties and select communities contained therein.  It also produces charts depicting the median home price to median income ratio for each geography, where the median income used in all cases is the median income for the Columbus MSA, as obtained from the U.S. Census Bureau.


## Outputs

This data kit produces a semi-wide form table in CSV format (see `./output_data/housingcost-long.csv`) which includes the following variables by geography by year (where available):

  - Number of sales	
  - Median home sale price (2023 dollars)	
  - Median home sale price (year-of dollars)	
  - Median income (2023 dollars)	
  - Median income (year-of dollars)	
  - Median income MOE (year-of dollars)	
  - Mean income (2023 dollars)	
  - Mean income (year-of dollars)	
  - Mean income MOE (year-of dollars)	
  - Median sale price/income ratio (MSA med inc)

  
The data is accompanied by a [Frictionless Resource file](https://specs.frictionlessdata.io/data-resource/), which provides a high-level description of the data and a link to the associated table schema.  The Resource file also provides the [MD5 checksum](https://en.wikipedia.org/wiki/Md5sum) ("hash") and the file size ("bytes") of the data file to allow for integrity checking.

The table schema is described by a [Frictionless Schema file](https://specs.frictionlessdata.io/table-schema/), which describes each of the fields contained in the table, including its name and type, and sometimes provides additional metadata about the table.

## Processes

The output table is is produced by a [Jupyter notebook](https://jupyter.org/) (see `./insights-housingprice.ipynb`).

The process is fully automated, but depends on outputs from several upstream processes.

## Inputs

The process requires the following inputs:

  1. MLS real estate transaction records summarized by geography. This is produced by upstream process [morpc-housingcost-profile](https://github.com/morpc/morpc-housingcost-profile). See `./input_data/morpc-housingcost-profile.csv`.
  1. MORPC standard geographies lookup table, which is produced by upstream process [morpc-geos-collect](https://github.com/morpc/morpc-geos-collect)
  1. [MORPC's member list](https://github.com/morpc/morpc-lookup/blob/main/Member_List.xlsx)
  
Note that access to some of the upstream content is restricted to MORPC staff.

## Revision history

Revisions are listed in reverse chronological order.

### 2025-03-05 Adam Porr <aporr@morpc.org>

Initial release.