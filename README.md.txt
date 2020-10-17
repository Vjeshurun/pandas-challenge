Note 
Instructions have been included for each segment. You do not have to follow them exactly, but they are included to help you think through the steps. 

Out[1]:  
Purchase ID  SN  Age  Gender  Item ID  Item Name  Price  
0  0  Lisim78  20  Male  108  Extraction, Quickblade Of Trembling Hands  3.53  
1  1  Lisovynya38  40  Male  143  Frenzied Scimitar  1.56  
2  2  Ithergue48  24  Male  92  Final Critic  4.88  
3  3  Chamassasya86  24  Male  100  Blindscythe  3.27  
4  4  Iskosia90  23  Male  131  Fury  1.44  
...  ...  ...  ...  ...  ...  ...  ...  
775  775  Aethedru70  21  Female  60  Wolf  3.54  
776  776  Iral74  21  Male  164  Exiled Doomblade  1.63  
777  777  Yathecal72  20  Male  67  Celeste, Incarnation of the Corrupted  3.46  
778  778  Sisur91  7  Male  92  Final Critic  4.19  
779  779  Ennrian78  24  Male  50  Dawn  4.60  
780 rows × 7 columns  
Player Count  
Display the total number of players  



Out[2]: 
Purchase ID Age Item ID Price 
count 780.000000 780.000000 780.000000 780.000000 mean 389.500000 22.714103 91.755128 3.050987 std 225.310896 6.659444 52.697702 1.169549 min 0.000000 7.000000 0.000000 1.000000 25% 194.750000 20.000000 47.750000 1.980000 50% 389.500000 22.000000 92.000000 3.150000 75% 584.250000 25.000000 138.000000 4.080000 max 779.000000 45.000000 183.000000 4.990000 

Out[3]: 
Total Players 0 576 


Purchasing Analysis (Total) 
Run basic calculations to obtain number of unique items, average price, etc. Create a summary data frame to hold the results Optional: give the displayed data cleaner formatting Display the summary data frame 





In [6]: 


Out[8]:  0  Number of Unique Items Average Price 179 $3.05  Number of Purchases 780  Total Revenue $2,379.77  
Gender Demographics  
Percentage and Count of Male Players Percentage and Count of Female Players Percentage and Count of Other / Non-Disclosed  


Out[9]:  Purchase ID  SN  Age  Gender  Item ID  Item Name  Price  
0  0  Lisim78  20  Male  108  Extraction, Quickblade Of Trembling Hands  3.53  
1  1  Lisovynya38  40  Male  143  Frenzied Scimitar  1.56  
2  2  Ithergue48  24  Male  92  Final Critic  4.88  
3  3  Chamassasya86  24  Male  100  Blindscythe  3.27  
4  4  Iskosia90  23  Male  131  Fury  1.44  


Out[10]: Male 484 Female 81 Other / Non-Disclosed 11 Name: Gender, dtype: int64 

Out[11]: Male 84.027778 Female 14.062500 Other / Non-Disclosed 1.909722 Name: Gender, dtype: float64 

Out[13]: 
Total Count Percentage of Players 
Male  484  84.03%  
Female  81  14.06%  
Other / Non-Disclosed  11  1.91%  



Purchasing Analysis (Gender) 
Run basic calculations to obtain purchase count, avg. purchase price, avg. purchase total per person etc. by gender Create a summary data frame to hold the results Optional: give the displayed data cleaner formatting Display the summary data frame 

<pandas.core.groupby.generic.DataFrameGroupBy object at 0x000001ED8A1BD048> 
Out[14]: 
Purchase ID SN Age Item ID Item Name Price 
Gender 
Female  113  113  113  113  113  113  
Male  652  652  652  652  652  652  
Other / Non-Disclosed  15  15  15  15  15  15  


Out[15]: Gender Female 113 Male 652 Other / Non-Disclosed 15 Name: Purchase ID, dtype: int64 

Out[16]: Gender Female 3.203009 Male 3.017853 Other / Non-Disclosed 3.346000 Name: Price, dtype: float64 

Out[17]: Gender Female 361.94 Male 1967.64 Other / Non-Disclosed 50.19 Name: Price, dtype: float64 In [21]: # Format the price columns purchasing_analysis_summary['Average Purchase Price'] = purchasing_analysis_su mmary['Average Purchase Price'].astype(float).map("${:,.2f}".format) purchasing_analysis_summary['Total Purchase Value'] = purchasing_analysis_summ ary['Total Purchase Value'].astype(float).map("${:,.2f}".format) purchasing_analysis_summary['Avg Total Purchase per Person'] = purchasing_anal ysis_summary['Avg Total Purchase per Person'].astype(float).map("${:,.2f}".for mat) purchasing_analysis_summary 

Out[18]:  Female  4.468395  
Male  4.065372  
Other / Non-Disclosed  4.562727  
dtype: float64  


Out[21]: 
Purchase Average Purchase Total Purchase Avg Total Purchase per Count Price Value Person 

Gender 
Female 113 $3.20 $361.94 $4.47 Male 652 $3.02 $1,967.64 $4.07 Other / Non­
15 $3.35 $50.19 $4.56

Disclosed 


Age Demographics 

Establish
 bins for ages 


Categorize
 the existing players using the age bins. Hint: use pd.cut() 


Calculate
 the numbers and percentages by age group 


Create
 a summary data frame to hold the results 



Optional: round the percentage column to two decimal points 

Display Age Demographics Table 

Out[24]: 
Purchase ID Age Item ID Price 
count 576.000000 576.000000 576.000000 576.000000 mean 350.331597 22.741319 92.527778 3.070573 std 222.226127 6.838568 53.923997 1.164585 min 0.000000 7.000000 0.000000 1.000000 25% 158.750000 19.000000 46.000000 1.980000 50% 336.500000 22.000000 93.000000 3.160000 75% 529.250000 25.000000 142.000000 4.102500 max 778.000000 45.000000 183.000000 4.990000 


Purchasing Analysis (Age) 

Bin
 the purchase_data data frame by age 


Run
 basic calculations to obtain purchase count, avg. purchase price, avg. purchase total per person etc. in the table below 


Create
 a summary data frame to hold the results 



Optional: give the displayed data cleaner formatting 

Display the summary data frame 

Out[33]:  0 1 2 3 4  Purchase ID 0 1 2 3 4  SN Lisim78 Lisovynya38 Ithergue48 Chamassasya86 Iskosia90  Age 20 40 24 24 23  Gender Male Male Male Male Male  Item ID 108 143 92 100 131  Item Name Extraction, Quickblade Of Trembling Hands Frenzied Scimitar Final Critic Blindscythe Fury  Price 3.53 1.56 4.88 3.27 1.44  AgeGroup 20-24 40+ 20-24 20-24 20-24  
...  ...  ...  ...  ...  ...  ...  ...  ...  
775  775  Aethedru70  21  Female  60  Wolf  3.54  20-24  
776  776  Iral74  21  Male  164  Exiled Doomblade  1.63  20-24  
777 778  777 778  Yathecal72 Sisur91  20 7  Male Male  67 92  Celeste, Incarnation of the Corrupted Final Critic  3.46 4.19  20-24 <10  
779  779  Ennrian78  24  Male  50  Dawn  4.60  20-24  
780 rows × 8 columns  


Out[39]:  
Purchase ID  SN  Age  Gender  Item ID  Item Name  Price  AgeGroup  
0  0  Lisim78  20  Male  108  Extraction, Quickblade Of Trembling Hands  3.53  20-24  
1  1  Lisovynya38  40  Male  143  Frenzied Scimitar  1.56  40+  
2  2  Ithergue48  24  Male  92  Final Critic  4.88  20-24  
3  3  Chamassasya86  24  Male  100  Blindscythe  3.27  20-24  
4  4  Iskosia90  23  Male  131  Fury  1.44  20-24  


<pandas.core.groupby.generic.DataFrameGroupBy object at 0x000001ED8B306A90> 
Out[43]: 
Purchase ID SN Age Gender Item ID Item Name Price 
Age Group 
<10 171717 17 17 17 17 10-14 222222 22 22 22 22 15-19 107 107 107 107 107 107 107 20-24 258 258 258 258 258 258 258 25-29 777777 77 77 77 77 30-34 525252 52 52 52 52 35-39 313131 31 31 31 31 
40+ 121212 12 12 12 12 

Out[49]: Age Group 
<10 17 
10-14 22 
15-19 107 
20-24 258 
25-29 77 
Name: Purchase ID, dtype: int64 

Out[57]: 20-24 365 15-19 136 25-29 101 30-34 73 35-39 41 10-14 28 <10 23 40+ 13 Name: Age Group, dtype: int64 Out[60]: Age Group 

<10 3.353478 
10-14 2.956429 
15-19 3.035956 
20-24 3.052219 
25-29 2.900990 
Name: Price, dtype: float64 

Out[61]: Age Group 
<10 77.13 
10-14 82.78 
15-19 412.89 
20-24 1114.06 
25-29 293.00 
Name: Price, dtype: float64 

Out[47]: 20-24 258 15-19 107 25-29 77 30-34 52 35-39 31 10-14 22 <10 17 40+ 12 Name: Age Group, dtype: int64 

Out[62]: <10 4.537059 10-14 3.762727 15-19 3.858785 20-24 4.318062 25-29 3.805195 30-34 NaN 35-39 NaN 40+ NaN dtype: float64 


Out[53]:  
Total Count  Percentage of Players  
Age Group  
<10 17 2.951389 10-14 22 3.819444 15-19 107 18.576389 20-24 258 44.791667 25-29 77 13.368056 



Out[54]:  
Total Count  Percentage of Players  
Age Group  
<10 17 2.95% 10-14 22 3.82% 15-19 107 18.58% 20-24 258 44.79% 25-29 77 13.37% 



Out[55]: 

Total Count Percentage of Players 

Out[63]:  
Purchase Count  Average PurchasePrice  Total Purchase Value  Avg Total Purchase perPerson  
<10  23  3.353478  77.13  4.537059  
10­14  28  2.956429  82.78  3.762727  
15­19  136  3.035956  412.89  3.858785  
20­24  365  3.052219  1114.06  4.318062  
25­29  101  2.900990  293.00  3.805195  
30­34  73  NaN  NaN  NaN  
35­39  41  NaN  NaN  NaN  
40+  13  NaN  NaN  NaN  

In [65]: 
Purchasing_Analysis_Summary['Average Purchase Price'] = Purchasing_Analysis_Su mmary['Average Purchase Price'].astype(float).map("${:,.2f}".format) Purchasing_Analysis_Summary['Total Purchase Value'] = Purchasing_Analysis_Summ ary['Total Purchase Value'].astype(float).map("${:,.2f}".format) Purchasing_Analysis_Summary['Avg Total Purchase per Person'] = Purchasing_Anal ysis_Summary['Avg Total Purchase per Person'].astype(float).map("${:,.2f}".for mat) Purchasing_Analysis_Summary 
Out[65]:  
Purchase  Average Purchase  Total Purchase  Avg Total Purchase per  
Count  Price  Value  Person  

<10 23 $3.35 $77.13 $4.54 10­
28 $2.96 $82.78 $3.76
14 
15­
136 $3.04 $412.89 $3.86
19 
20­
365 $3.05 $1,114.06 $4.32
24 
25­
101 $2.90 $293.00 $3.81
29 
30­
73 $nan $nan $nan
34 
35­
41 $nan $nan $nan
39 40+ 13 $nan $nan $nan 


Top Spenders 

Run
 basic calculations to obtain the results in the table below 


Create
 a summary data frame to hold the results 


Sort
 the total purchase value column in descending order 



Optional: give the displayed data cleaner formatting 

Display a preview of the summary data frame 
In [73]: 
# Group purchase data by screen names 
spender_stats = purchase_data.groupby("SN") 
# Count the total purchases by name 
purchase_count_spender = spender_stats["Purchase ID"].count() 
# Calculate the average purchase by name 
avg_purchase_price_spender = spender_stats["Price"].mean() 
# Calculate purchase total 
purchase_total_spender = spender_stats["Price"].sum() 
# Create data frame with obtained values 
top_spenders = pd.DataFrame({"Purchase Count": purchase_count_spender, 
"Average Purchase Price": avg_purchase_price_spen der, 
"Total Purchase Value":purchase_total_spender}) 
# Sort in descending order to obtain top 5 spender names 
formatted_spenders = top_spenders.sort_values(["Total Purchase Value"], ascend ing=False).head() 
# Format with currency style 
formatted_spenders.style.format({"Average Purchase Price":"${:,.2f}", "Total Purchase Value":"${:,.2f}"}) 
Out[73]:  
Purchase Count  Average Purchase Price  Total Purchase Value  
SN  
Lisosia93  5  $3.79  $18.96  
Idastidru52  4  $3.86  $15.45  
Chamjask73  3  $4.61  $13.83  
Iral74  4  $3.40  $13.62  
Iskadarya95  3  $4.37  $13.10  
Most Popular Items  


Retrieve
 the Item ID, Item Name, and Item Price columns 


Group
 by Item ID and Item Name. Perform calculations to obtain purchase count, average item price, and total purchase value 


Create
 a summary data frame to hold the results 


Sort
 the purchase count column in descending order 



Optional: give the displayed data cleaner formatting 

Display a preview of the summary data frame 
In [75]: 
# create a df with above 3 cols 
item_df = purchase_data[['Item ID','Item Name','Price']] 
#group by Item ID & Item Name 
item_stats = item_df.groupby(['Item ID','Item Name']) 
# purchase count 
Item_Purchase_Count = item_stats['Price'].count() 
# Total Purchase count 
Item_Total_Purchase_Value = (item_stats['Price'].sum()) 
# Average Item price 
Item_average_item_price = (item_stats['Price'].mean()) 
# Create summary DF 
item_summary = pd.DataFrame({"Purchase Count":Item_Purchase_Count, "Item Price": Item_average_item_price, "Total Purchase Value":Item_Total_Purchase_Value }) 
item_summary_formatted =item_summary.sort_values(['Purchase Count'],ascending= False).head() 
# Format with currency style 
item_summary_formatted.style.format({"Item Price":"${:,.2f}", "Total Purchase Value":"${:,.2f}"}) 
Out[75]:  
Purchase  Item  Total Purchase  
Count  Price  Value  
Item ID  Item Name  
92  Final Critic  13  $4.61  $59.99  
178  Oathbreaker, Last Hope of the BreakingStorm  12  $4.23  $50.76  
145  Fiery Glass Crusader  9  $4.58  $41.22  
132  Persuasion  9  $3.22  $28.99  
108  Extraction, Quickblade Of Trembling Hands  9  $3.53  $31.77  


Out[76]:  Item ID 92 178 82 145 103  Item Name Final Critic Oathbreaker, Last Hope of the Breaking Storm Nirvana Fiery Glass Crusader Singed Scalpel  Purchase Count 13 12 9 9 8  Item Price $4.61 $4.23 $4.90 $4.58 $4.35  Total Purchase Value $59.99 $50.76 $44.10 $41.22 $34.80  
Most Profitable Items  
Sort the above table by total purchase value in descending order Optional: give the displayed data cleaner formatting Display a preview of the data frame  



