
<!-- Improved compatibility of back to top link: See: https://github.com/othneildrew/Best-README-Template/pull/73 -->
<a name="readme-top"></a>
<!--
*** Thanks for checking out the Best-README-Template. If you have a suggestion
*** that would make this better, please fork the repo and create a pull request
*** or simply open an issue with the tag "enhancement".
*** Don't forget to give the project a star!
*** Thanks again! Now go create something AMAZING! :D
-->



<!-- PROJECT SHIELDS -->
<!--
*** I'm using markdown "reference style" links for readability.
*** Reference links are enclosed in brackets [ ] instead of parentheses ( ).
*** See the bottom of this document for the declaration of the reference variables
*** for contributors-url, forks-url, etc. This is an optional, concise syntax you may use.
*** https://www.markdownguide.org/basic-syntax/#reference-style-links
-->
![Power BI](https://img.shields.io/static/v1?style=for-the-badge&message=Power+BI&color=222222&logo=Power+BI&logoColor=F2C811&label=)
[![MIT License][license-shield]][license-url]
[![LinkedIn][linkedin-shield]][linkedin-url]

[license-shield]: https://img.shields.io/github/license/othneildrew/Best-README-Template.svg?style=for-the-badge
[license-url]: https://github.com/JoshuaOlubori/sql-employee-analysis-a/blob/698fb9fe82c62ece6efcbfacfd0b0da29204812a/LICENSE.txt
[linkedin-shield]: https://img.shields.io/badge/-LinkedIn-black.svg?style=for-the-badge&logo=linkedin&colorB=555
[linkedin-url]: https://linkedin.com/in/clientname


<!-- PROJECT LOGO -->
<br />
<div align="center">

  <h3 align="center">UK Road Accidents and Casualties Tracking Dashboard (2021 - 2022)</h3>

  <p align="center">
    Featuring data modeling in Power BI, 
    and Dax <br />



<!-- TABLE OF CONTENTS -->
<details>
  <summary>Table of Contents</summary>
  <ol>
    <li>
      <a href="#requirement">Requirement gathering</a>
      <ul>
        <li><a href="#stakeholders">Identifying stakeholders</a></li>
      </ul>
    </li>
    <li>
      <a href="#raw-data">Understanding raw data</a>
      <ul>
        <li><a href="#data-cleansing">Data cleansing </a></li>
        <li><a href="#data-processing">Data processing</a></li> 
<li><a href="#modeling">Data modeling</a></li>
      </ul>
    </li>
  
  </ol>
</details>



<!-- ABOUT THE PROJECT -->
## About The Project 🍪 

![Dashboard](https://github.com/JoshuaOlubori/sql-employee-analysis-a/blob/ddfa9521399eadd8cea5f425101dffd880edaa39/dashboard.PNG)

Tracking Accidents and Casualties across UK Roads in 2012

### Requirement Gathering

Client wants to create a dashboard on road accidents for the year 2021 and 2022.

a. Primary KPIs - Total casualties and total accident values for the current year and the YoY growth

- Total casualties by accident severity for the current year and YoY growth

b. Secondary KPIs - Total casualties with respect to vehicle type for the current year

- Monthly trend showing comparison of casualties for the current year and previous year

- Casualties for road type for current year

- Current year casualties by area/location & day/night

- Total casualties and total accidents by location

<!-- -->
## Identifying Stakeholders 🧑🏽‍💼

- Emergency Services Departments
- Road Safety Corps
- Traffic Management Agencies
- Police Force
- General public

### Understanding Raw Data 🥩

| First Header  | Second Header |
| ------------- | ------------- |
| Content Cell  | Content Cell  |
| Content Cell  | Content Cell  |

I created a connection to the instance of MySQL on my machine by providing the server name and the database name as shown below .
Instead of connecting to the whole database and importing all tables, I only imported two views that I had created earlier, as best practice suggests to limit data access.
The views encompass joins that would otherwise have impacted the performance of the Power BI engine if the raw tables were imported.

Before loading the data, I used Power Query to check for errors in the data like nulls or misspellings. Later on while writing DAX, I figured I would need a `Age` column, so I went back to Power Query to use the Columns From Example feature to generate ages from the birthdate column in the employees table.

### DAX Measures ✨

As most Power BI experts preach, I avoided using implicit measures and stuck to writing all my measures in DAX.
Here’s a list of DAX measures I wrote:
   ```% Female = DIVIDE([Total Female Employees], [Head Count])
% Male = DIVIDE([Total Male Employees],[Head Count])

Age = 
    IFERROR(
    VALUES('employees v_employee_details'[Age]),
    "select an employee")

Avg Salary = AVERAGE('employees v_employee_details'[salary])

Current Department = CALCULATE(VALUES('employees v_employee_details'[dept_name]),'employees v_employee_details'[dept_start_date] = MAX('employees v_employee_details'[dept_start_date]))

Current Salary = 
    IFERROR(
    CALCULATE(VALUES('employees v_employee_details'[salary]),
    'employees v_employee_details'[salary_from_date] = MAX('employees v_employee_details'[salary_from_date])),
    "select an employee")

Current Title = 
    IFERROR(
    CALCULATE(VALUES('employees v_employee_details'[title]),
    'employees v_employee_details'[title_from_date] = MAX('employees v_employee_details'[title_from_date])),
    "select an employee")

Employee Full Name = SELECTEDVALUE('employees v_employee_details'[first_name]) & " " & SELECTEDVALUE('employees v_employee_details'[last_name])

Gender = 
    IFERROR(
    VALUES(('employees v_employee_details'[gender])),
    "select an employee")

Head Count = DISTINCTCOUNT('employees v_employee_details'[emp_no])

Max Employee Age = MAX('employees v_employee_details'[Age])

Total Amount Spent on Salary = SUM('employees v_employee_details'[salary])

Total Female Employees = CALCULATE([Head Count],'employees v_employee_details'[gender] = "F")

Total Male Employees = calculate([Head Count], 'employees v_employee_details'[gender] = "M")

Welcome Text = 
VAR Hour = HOUR(NOW())
VAR Greeting =
SWITCH(
	TRUE(),
	Hour >= 0 && Hour < 5, "Good Night",
	Hour >= 5 && Hour < 12, "Good Morning",
	Hour >= 12 && Hour < 18, "Good Afternoon",
	Hour >= 18 && Hour < 24, "Good Afternoon"
)
RETURN
Greeting & ", Boss!"
   ```


<!-- CONTACT  ☎️ -->
## Contact

Edun Joshua Olubori - [connect on linkedin](https://www.linkedin.com/in/joshua-edun) - joshuaolubori@gmail.com

Project Link: [Check out the project website](https://joshuaolubori.my.canva.site/project-001)

<p align="right">(<a href="#readme-top">back to top</a>)</p>



