<h1> POLI 198 WI'21-SPR'21 - Data Cleaning Project: <br>
  2000-2016 Votes and Candidate Datasets, Brazilian Municipalities <h2>
<h2> Introduction </h2>
  <p> This purpose of this project is to use data cleaning to create a novel dataset that merges votes and candidate datasets of Brazilian mayoral elections from 2000-2016, pulled from the <a href="https://cepespdata.io/">CEPESP website</a>. As part of our data cleaning process, we used R to conduct exploratory data analysis, generate new variables, and replace missing data.
  <br><br>
The datasets on Candidates’ profiles can be downloaded from <a href="https://cepespdata.io/consulta/candidatos">here</a>. (I also call it candidate data).
  <br><br>
The datasets on Electoral Results can be downloaded from <a href="https://cepespdata.io/consulta/tse">here</a>. (I also call it votes data).
  </p>
  
<h2> Description of Files </h2>
  <h3>5.26.21 poli198 – Code.Rmd</h3>
  This R Markdown file contains all the code written as part of this data cleaning project.
  <h3>5.26.21 poli198 - Code.html</h3>
  This is an HTML document converted from the R Markdown file.
  <h3>pseudo_CPF.xlsx</h3>
    This Excel spreadsheet contains documentation of data that I manually updated for the “CPF_CANDIDATO” variable.
    <br><br>
The raw data downloaded from the CEPESP website contained “#NULO”, or null, observations for the “CPF_CANDIDATO” variable. By cross referencing the votes and candidate datasets, I was able to match observations with null CPF’s. To deal with the problem of null observations, I created eleven-digit pseudo CPF numbers that started with 999999999xx and manually updated the null observations.
    <br><br>
Data only from years 2000 and 2004 has this problem of null observations.
    <br><br>
I generated and updated the data with 40 pseudo CPF numbers.
  <h3>mergedData.csv</h3>
    This file is the final deliverable, a merged dataset of the votes and candidate datasets.




