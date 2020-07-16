Predicting Sales Prices for Ames Dataset
by: Steve Diamond (https://github.com/StevenWDiamond)

## Problem Statement

Our data science team at the Ames Chamber of Commerce has been tasked to understand housing in and around the Ames area. Our goal is to understand which home features are the most important drivers of real estate prices and which are not important at all (paying close attention to those things that are typically assumed to be true).

We have obtained a dataset from the Assessor's office which was compiled by Dean De Cock at Truman State University. It includes 2,051 home sales in the area between 2006 and 2010. To analyze our data, will be regression modeling and judging our models using the RMSE metric. This metric allows us to translate our results into units (in this case dollars) and understand the direct impact of each feature.


## Executive Summary

Our team at the Ames Chamber of Commerce was tasked with looking a real estate sales dataset from the Ames area, understanding its implictions and making recommendations on how we can leverage this knowledge to the benefit of our members.

To accomplish this task, we will do the following:

- Clean the data
- Perform an Exploratory Data Analysis to understand what we can from the data itself, add additional information through feature engineering and create a dataset that is completely numerical
- Apply multiple regression methods to determine which best suits this data
- Chose one of these methods, tune the model by varying the inputs and then examine the model


## Table of Contents

- Loading Data
- Data Cleaing
- Exploratory Data Analysis
- Modeling
- Model Selection
- Model Evaluation
- Conclusions and Recommendations


## Data Dictionary

|**Feature Name**|**Data Type**|**Description**|
|:---|:---|:---|
|ms_subclass|Nominal|Type of dwelling|
|ms_zoning|Nominal|Zoning classification|
|lot_frontage|Continuous (Ft.)|Feet of street connected to property|
|lot_area|Continuous (Sq. Ft.)|Lot size|
|street|Nominal|Street Access|
|alley|Nominal|Alley Access|
|lot_shape|Ordinal|General shape of property|
|land_contour|Nominal|Flatness of the property|
|utilities|Ordinal|Type of utilities available|
|lot_config|Nominal|Lot configuration|
|land_slope|Ordinal|Slope of property|
|neighborhood|Nominal|Physical locations within Ames city limits|
|condition_1|Nominal|Proximity to various conditions|
|condition_2|Nominal|Proximity (if more than one is present)|
|bldg_type|Nominal|Type of dwelling|
|house_style|Nominal|Style of dwelling|
|overall_qual|Ordinal|Overall quality of house|
|overall_cond|Ordinal|Overall condition of house|
|year_built|Discrete|Original construction date|
|year_remod/add|Discrete|Remodel date (same as construction date if no remodeling or additions)|
|roof_style|Nominal|Type of roof|
|roof_matl|Nominal|Roofing material|
|exterior_1|Nominal|Exterior covering on house|
|exterior_2|Nominal|Exterior covering (if more than one material)|
|mas_vnr_type|Nominal|Masonry veneer type|
|mas_vnr_area|Continuous (Sq. Ft.)|Masonry veneer area|
|exter_qual|Ordinal|Quality of exterior material|
|exter_cond|Ordinal|Condition of exterior material|
|foundation|Nominal|Type of foundation|
|bsmt_qual|Ordinal|Quality of basement|
|bsmt_cond|Ordinal|Condition of basement|
|bsmt_exposure|Ordinal|Refers to walkout or garden level walls|
|bsmtfin_type_1|Ordinal|Rating of finished basement|
|bsmtfin_sf_1|Continuous (Sq. Ft.)|Tyoe 1 finished basement area|
|bsmtfin_type_2|Ordinal|Rating of finished basement (if multiple types)|
|bsmtfin_sf_2|Continuous (Sq. Ft.)|Tyoe 2 finished basement area|
|bsmt_unf_sf|Continuous (Sq. Ft.)|Unfinished basement area|
|total_bsmt_sf|Continuous (Sq. Ft.)|Total basement area|
|heating|Nominal|Type of heating|
|central_air|Nominal|Central air conditioning|
|electrical|Ordinal|Electrical system|
|1st_flr_sf|Continuous (Sq. Ft.)|First floor area|
|2nd_flr_sf|Continuous (Sq. Ft.)|Second floor area|
|low_qual_fin_sf|Continuous (Sq. Ft.)|Low quality finished area (all floors)|
|gr_liv_area|Continuous (Sq. Ft.)|Above grade (ground) living area|
|bsmt_full_bath|Discrete|Basement full bathrooms|
|bsmt_half_bath|Discrete|Basement half bathrooms|
|full_bath|Discrete|Full bathrooms above grade|
|half_bath|Discrete|Half baths above grade|
|bedroom|Discrete|Bedrooms above grade (does NOT include basement bedrooms)|
|kitchen|Discrete|Kitchens above grade|
|kitchenqual|Ordinal|Kitchen quality|
|totmmsabvgrd|Discrete|Total rooms above grade (does not include bathrooms)?
|functional|Ordinal|Home functionality (Assume typical unless deductions are warranted)|
|fireplaces|Discrete|Number of fireplaces|
|fireplace_qu|Ordinal|Fireplace quality|
|garage_type|Nominal|Garage location|
|garage_yr_blt|Discrete|Year garage was built|
|garage_finish|Ordinal|Interior finish of the garage|
|garage_cars|Discrete|Size of garage in car capacity|
|garage_area|Continuous (Sq. Ft.)|Area of garage|
|garage_qual|Ordinal|Garage quality|
|garage_cond|Ordinal|Garage condition|
|paved_drive|Ordinal|Paved driveway|
|wood_deck_sf|Continuous (Sq. Ft.)|Wood deck area|
|open_porch_sf|Continuous (Sq. Ft.)|Open porch area|
|enclosed_porch|Continuous (Sq. Ft.)|Enclosed porch area|
|3ssn_porch|Continuous (Sq. Ft.)|Three season porch area|
|screen_porch|Continuous (Sq. Ft.)|Screen porch area|
|pool_area|Continuous (Sq. Ft.)|Pool area|
|pool_qc|Ordinal|Pool quality|
|fence|Ordinal|Fence quality|
|misc_feature|Nominal|Miscellaneous feature not covered in other categories|
|misc_val|Continuous (US Dollar)|Value of miscellaneous feature|
|mo_sold|Discrete|Month Sold (MM)|
|yr_sold|Discrete|Year Sold (YYYY)|
|sale_type|Nominal|Type of sale|
|sale_condition|Nominal|Condition of sale|
|saleprice|Continuous (US Dollar)|Sale price|      
