## HR Attendance Data Analysis Project

1. Data is present in HR_Attendance_Sheet_2022-23.xlsx file above. Download `HR_Attendance_Sheet_2022-23.xlsx` file to your local computer for analysis.

### Data analysis using Power BI


1. Formula to create Office Working days column

`Office Working days = 
Var totaldays = [Count]

VAR nonworkdays = CALCULATE([Count],'Final Data'[Value] in {"HO", "WO"})

RETURN
totaldays-nonworkdays column`

2. Formula to create Attendance % column

`Attendace % = DIVIDE([Present Days],[Office Working days],0)`

3. Formula to create Count column

`Count = COUNT('Final Data'[Value])`

4. Formula to create HFWH Count column

`HFWH Count = CALCULATE([Count],'Final Data'[Value]="HWFH")`

5. Formula to create Present Days column

`Present Days = CALCULATE([Count],'Final Data'[Value] in {"P", "WFH"})`

6. Formula to create SL% column

`SL % = DIVIDE('Measures (2)'[SL Count], [Office Working days])`

7. Formula to create SL Count column

`SL Count = SUM('Final Data'[SL Count])`

8. Formula to create WFH% column

`WFH % = DIVIDE([WFH Count],'Measures (2)'[Present Days],0)`

9. Formula to create WFH count column

`WFH Count = SUM('Final Data'[WFH Count])`