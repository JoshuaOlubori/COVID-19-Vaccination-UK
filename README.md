
<!-- Improved compatibility of back to top link: See: https://github.com/othneildrew/Best-README-Template/pull/73 -->
<a name="readme-top"></a>
<!--
*** Thanks for checking out the Best-README-Template. If you have a suggestion
*** that would make this better, please fork the repo and create a pull request
*** or simply open an issue with the tag "enhancement".
*** Don't forget to give the project a star!
*** Thanks again! Now go create something AMAZING! :D
-->


![Power BI](https://img.shields.io/static/v1?style=for-the-badge&message=Power+BI&color=222222&logo=Power+BI&logoColor=F2C811&label=)
[![MIT License][license-shield]][license-url]
[![LinkedIn][linkedin-shield]][linkedin-url]

[license-shield]: https://img.shields.io/github/license/othneildrew/Best-README-Template.svg?style=for-the-badge
[license-url]: https://github.com/JoshuaOlubori/COVID-19-Vaccination-UK/blob/209cd42deaec81334a18ef4f59affb090356263a/LICENSE.txt
[linkedin-shield]: https://img.shields.io/badge/-LinkedIn-black.svg?style=for-the-badge&logo=linkedin&colorB=555
[linkedin-url]: https://linkedin.com/in/joshua-edun


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
  <ul>
    <li><a href="#requirement">Requirement gathering</a></li>
        <li><a href="#stakeholders">Identifying stakeholders</a></li>
        <li> <a href="#raw-data">Understanding raw data</a></li>
        <li><a href="#data-processing">Data processing</a></li> 
<li><a href="#modeling">Data modeling</a></li>
   <li><a href="#visualization">Data visualization</a></li> 
    <li><a href="#insights">Insights</a></li>
    <li><a href="#contact">Contact</a></li>
  </ul>
</details>


<div align="left">
<!-- ABOUT THE PROJECT -->
  
## About The Project 🍪 

![Dashboard](https://github.com/JoshuaOlubori/COVID-19-Vaccination-UK/blob/9658ed47b28d57aa1e6b5825adf9b42bb3c24425/screenshot.png)

Tracking COVID-19 vaccination data across the UK
<a name="requirement"/>
### Requirement Gathering

Client wants a dashboard to capture a big picture of the COVID-19 vaccination data in the UK

#### a. Primary KPIs
- Number of people who had not received a vaccination

- Number of people who had received one vaccination only

- Number of people who had received two vaccinations only

- Number of people who had received at least 4 vaccinations



#### b. Secondary KPIs
- Proportion of people who had received at least 4 vaccinations by age group, ethnicity and religion


<!-- -->
  <a name="stakeholders"/>
  
### Identifying Stakeholders 🧑🏽‍💼

- NHS
- Hospitals
- Ministy of Health
  
<a name="raw-data"/>
  
### Understanding Raw Data 🥩

The data resides in a Excel file with 4 sheets. The data I need resides in sheet Table_1
  
| Field | Description |
| ----- | ----------- |
| Characteristic | The characteristic of a group of individuals |
| Group | The group to which the individuals belong |
| Region | The region associated with the group |
| Age group | The age group to which the individuals belong |
| Population | The total population of the group |
| Number of people who had not received a vaccination | The count of individuals who have not received any vaccination |
| Number of people who had received one vaccination only | The count of individuals who have received one vaccination only |
| Number of people who had received two vaccinations only | The count of individuals who have received two vaccinations only |
| Number of people who had received three vaccinations only | The count of individuals who have received three vaccinations only |
| Number of people who had received at least four vaccinations | The count of individuals who have received four or more vaccinations |
| Proportion of people who had not received a vaccination (%) | The percentage of individuals who have not received any vaccination |
| Proportion of people who had not received a vaccination, 95% confidence interval - Lower bound | The lower bound of the confidence interval for the proportion of individuals who have not received any vaccination |
| Proportion of people who had not received a vaccination, 95% confidence interval - Upper bound | The upper bound of the confidence interval for the proportion of individuals who have not received any vaccination |
| Proportion of people who had received one vaccination (%) | The percentage of individuals who have received one vaccination only |
| Proportion of people who had received one vaccination, 95% confidence interval - Lower bound | The lower bound of the confidence interval for the proportion of individuals who have received one vaccination only |
| Proportion of people who had received one vaccination, 95% confidence interval - Upper bound | The upper bound of the confidence interval for the proportion of individuals who have received one vaccination only |
| Proportion of people who had received two vaccinations (%) | The percentage of individuals who have received two vaccinations only |
| Proportion of people who had received two vaccinations, 95% confidence interval - Lower bound | The lower bound of the confidence interval for the proportion of individuals who have received two vaccinations only |
| Proportion of people who had received two vaccinations, 95% confidence interval - Upper bound | The upper bound of the confidence interval for the proportion of individuals who have received two vaccinations only |
| Proportion of people who had received three vaccinations (%) | The percentage of individuals who have received three vaccinations only |
| Proportion of people who had received three vaccinations, 95% confidence interval - Lower bound | The lower bound of the confidence interval for the proportion of individuals who have received three vaccinations only |
| Proportion of people who had received three vaccinations, 95% confidence interval - Upper bound | The upper bound of the confidence interval for the proportion of individuals who have received three vaccinations only |
| Proportion of people who had received at least four vaccinations (%) | The percentage of individuals who have received four or more vaccinations |
| Proportion of people who had received at least four vaccinations, 95% confidence interval - Lower bound | The lower bound of the confidence interval for the proportion of individuals who have received four or more vaccinations |
| Proportion of people who had received at least four vaccinations, 95% confidence interval - Upper bound | The upper bound of the confidence interval for the proportion of individuals who have received four or more vaccinations |
| Age-standardised proportion of people who had not received a vaccination (%) | The age-standardized percentage of individuals who have not received any vaccination |
| Age-standardised proportion of people who had not received a vaccination, 95% confidence interval


  <a name="data-processing"/> 
### Data Processing ⚙️

- The data is in a (relatively) tall format: The Group column collapses fields that should be individual columns into one one column.

- Using the Power Query Pivot Column feature, I pivoted the column into a wider format, bring the total column count to 64.

- Before pivoting, I changed all NA and Errors to zero because the pivoting operation is confused by strings in numeric columns.

- After pivoting, I replaced zeros to nulls and reordered the columns appropriately

 

  <a name="visualization"/>
### Data Visualization 🎨

- Power BI magic!✨ The report pbix file is available in this repo to explore design decisions (The file can only be opened in PowerBI)

  <a name="insights"/>
### Deriving Insights

- The older a person is, the more likely they have received at least 4 vaccinations

- Black Africans have the lowest vaccination rates at about 60%

- Jewish people have the highest vaccination rates
 

<!-- CONTACT  ☎️ -->

  <a name="contact"/>
  
### Contact

Edun Joshua Olubori - [connect on linkedin](https://www.linkedin.com/in/joshua-edun) - joshuaolubori@gmail.com

Project Link: [Check out the dashboard](https://joshuaolubori.my.canva.site/project-00k1)

<p align="right">(<a href="#readme-top">back to top</a>)</p>



