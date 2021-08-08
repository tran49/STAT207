PEW RESEARCH CENTER FOR THE PEOPLE & THE PRESS
FEBRUARY POLITICAL
February 7-12, 2017
N=1,503

***************************************************************************************************************************

This dataset includes cell phone interviews conducted using an RDD sample of cell phone numbers. 
Cell phone interviews include households that are cell-only as well as those that also have a landline phone. 
The dataset contains several weight variables. 

WEIGHT is the weight for the combined sample of all landline and cell phone interviews. 
Data for all Pew Research Center reports are analyzed using this weight.

Two other weights can be used to compare the combined sample with the landline sample by itself 
and with the cell phone sample by itself.

LLWEIGHT is for analysis of the landline RDD sample only. Interviews conducted by cellphone are not 
given a weight and are excluded from analysis when this weight is used.

CELLWEIGHT is for analysis of the cell RDD sample only. Interviews conducted by landline are not
given a weight and are excluded from analysis when this weight is used.

***************************************************************************************************************************

Beginning in the Fall of 2008, the Pew Research Center started using respondents’ self-reported zip code as  
the basis for geographic variables such as region, state and county. We do this because the error rate in the original 
geographic information associated with the sample is quite high, especially for respondents from the cell phone sample. 

For respondents who do not provide a zip code or for those we cannot match, we use the sample geographic information. 
We continue to include the original sample geographic variables in the datasets (these variables are preceded by an ‘s’) 
for archival purposes only.

To protect the privacy of respondents, telephone numbers, county of residence and zip code have been removed from the data file.

***************************************************************************************************************************

Releases from this survey:

February 16, 2017. "In First Month, Views of Trump Are Already Strongly Felt, Deeply Polarized"
http://www.people-press.org/2017/02/16/in-first-month-views-of-trump-are-already-strongly-felt-deeply-polarized/

February 16, 2017. "More favor than oppose Gorsuch nomination to Supreme Court"
http://www.pewresearch.org/fact-tank/2017/02/16/more-favor-than-oppose-gorsuch-nomination/

February 21, 2017. "Public divided over Keystone XL, Dakota pipelines; Democrats turn decisively against Keystone"
http://www.pewresearch.org/fact-tank/2017/02/21/public-divided-over-keystone-xl-dakota-pipelines-democrats-turn-decisively-against-keystone/

February 22, 2017. "In Trump Era, What Partisans Want From Their Congressional Leaders"
http://www.people-press.org/2017/02/22/in-trump-era-what-partisans-want-from-their-congressional-leaders/

February 23, 2017. "Support for 2010 health care law reaches new high"
http://www.pewresearch.org/fact-tank/2017/02/23/support-for-2010-health-care-law-reaches-new-high/

February 24, 2017. "Most Americans continue to oppose U.S. border wall, doubt Mexico would pay for it"
http://www.pewresearch.org/fact-tank/2017/02/24/most-americans-continue-to-oppose-u-s-border-wall-doubt-mexico-would-pay-for-it/

March 2, 2017. "Large Majorities See Checks and Balances, Right to Protest as Essential for Democracy"
http://www.people-press.org/2017/03/02/large-majorities-see-checks-and-balances-right-to-protest-as-essential-for-democracy/

March 2, 2017. "Public remains divided over role of government in financial regulation"
http://www.pewresearch.org/fact-tank/2017/03/02/public-remains-divided-over-role-of-government-in-financial-regulation/


***************************************************************************************************************************

SYNTAX

***The following syntax is for constructed demographic variables***.

*The combined race variable (racecmb) was computed using the following syntax:
recode race_1 (1=1) (2=2) (3=3) (4 thru 7=5) (8 thru 9=9) into racecmb.
if race_2>0 and race_2 <8 racecmb=4.
variable label racecmb "Combining Race".
value label racecmb
1 "White"
2 "Black or African-American"
3 "Asian or Asian-American"
4 "Mixed Race"
5 "Or some other race"
9 "Don’t know/Refused (VOL.)".

*The race-ethnicity variable (racethn) was computed using the following syntax:
if racecmb=1 and hisp ge 2 racethn=1.
if racecmb=2 and hisp ge 2 racethn=2.
if (racecmb ge 3 and racecmb le 5) and (hisp ge 2) racethn=4.
if racecmb=9 racethn=9.
if hisp=1 racethn=3.
variable label racethn “Race-Ethnicity”.
value label racethn
1 “White non-Hispanic”
2 “Black non-Hispanic”
3 “Hispanic”
4 “Other”
9 “Don’t know/Refused (VOL.)”.