## This project demonstrates the creation of a comprehensive IPL dashboard using Power BI. It covers data extraction from a SQL database, data processing and DAX queries, dashboard design, and sharing insights. The project aims to provide real-time insights into  operations, enabling  to monitor and analyze performance efficiently.  


- Devlope Comprehensive credit card weekly dashborad provides real time weekly insight  insights 
- insight into key performance matrix and trend 
- Enable to stasck honder to moniter and analyze operation effectively  


## 1. Project objective
## 2. Data from SQL
## 3. Data processing & DAX
## 4. Dashboard & insights
## 5. Export & share project

### Project Objective

- To develop a comprehensive IPL Dashboard  that
provides real-time insights into key
performance metrics and trends,
enabling stakeholders to monitor
and analyze IPL data  operations
effectively.

### step. 1 import dta from sql   

### step.2 load data tables from sql 

### step. 3 Data processing and DAX queries   
- Calender Table = CALENDAR(min('public ipl_matches_2008_2022'[match_date]),max('public         ipl_matches_2008_2022'[match_date])) 

- Year = YEAR('Calender Table'[Date])
- 

- AVG_by_bowler = DIVIDE(
     SUMX(
        FILTER('public ipl_ball_by_ball_2008_2022','public ipl_ball_by_ball_2008_2022'[extra_type]<>"legbyes" && 'public ipl_ball_by_ball_2008_2022'[extra_type]<> "byes" ),'public ipl_ball_by_ball_2008_2022'[total_run]),SUM('public ipl_ball_by_ball_2008_2022'[iswicket_delivery])
)

- Batter Runs = CONCATENATE(SUM('public ipl_ball_by_ball_2008_2022'[batsman_run])," Runs") 

- Bowler Wicket = CONCATENATE(SUM('public ipl_ball_by_ball_2008_2022'[iswicket_delivery])," Wickets")

- Bowling SR = COUNT('public ipl_ball_by_ball_2008_2022'[bowler])/SUM('public           ipl_ball_by_ball_2008_2022' [iswicket_delivery])

- Strike Rate for batsman = (SUM('public ipl_ball_by_ball_2008_2022'[batsman_run])/COUNT('public ipl_ball_by_ball_2008_2022'[ball_number]))*100  

- Matches_won_by_toss_decision = CALCULATE(COUNTROWS('public ipl_matches_2008_2022'),'public ipl_matches_2008_2022'[toss_winner]='public ipl_matches_2008_2022'[winning_team])

- Title Winner = VAR max_date = CALCULATE(MAX('Calender Table'[Date]),ALLSELECTED('public ipl_matches_2008_2022'),VALUES('public ipl_matches_2008_2022'))
Var title_winner= CALCULATE(SELECTEDVALUE('public ipl_matches_2008_2022'[winning_team]),'Calender Table'[Date]=max_date)
return title_winner



#### we take these dashbord wrt year and yearto chaeck which team is won wrt to that year  




Project Insights-
WoW change:
- • 
- • 
- • 
- • 
- • 
- • 
- • 
- • 

 



