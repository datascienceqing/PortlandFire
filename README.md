## PortlandFire

__This is an exploratory data analysis (EDA) on fire dispatch data provided to HACK Oregon Emergency Response Team. The goal for this analysis is to find out the interesting pattern or trend between different years accross different Fire Management Area (FMA). I first connected to the AWS EC2 instance where the database resides. Secondly, I extracted the data from different tables and calculated the time between response steps for a given incident. After checked the overview and distribution, I threw out some obvious incorrect data. Finally, I calculated means and plot them against years and FMAs.__

__Based on the analysis, average Response_Time is 5.67 min, and average OnScene_Time is 28.35 min during the period from 2010 to 2016. The average OnScene_Time decreased from 30.87 min in 2010 to 27.72 min in 2016, while average Response_Time did not change very much.__

__The analysis also showed most of the FMA performed very consistent over the years-- the mean Response_Time and OnScene_Time did not vary very much (see Cell 15 and 19), but the mean Response_Times are quite different--varying from less than 5 min to beyond 10 min. The dataset needs some cleaning. The "fmarespcomp" should only be integer, but see some non-integers; and we observed very large scale of variations are related to some fma codes. It is worth noting that Response_Time for "fmarespcomp" 210 and 27 are obvious two outliers in Response_Time plot (see Cell 15), their OnScene_Times don't seem to vary that much from the main group(see Cell 19).__

__The mean Response_Time over the years (see Cell 14) shows the highest deviation in 2014, while the same year shows 4 FMA mean OnScene_Times under 10 min (see Cell 18). So we might need to take a closer look on year 2014 first.__

## False Alarm Analysis

__False alarm is one hot issue in Portland Fire Department. It consumes resources and frustrats the fire fighters. I also made an analysis using Random Forest model to search what are the major factors that are related to the false alarm in past 7 years. The results showed the auto-alarms installed in commercial facilities are the major culprits, which is line with the information from Portland Fire Department. I then did further analysis using this method to find out the top10 fire blocks, so Portland Fire Department can send out investigator to check the auto-alarms in these fire blocks first. This is a targeted approach, which would address the false alarm issue more efficiently.__ 
