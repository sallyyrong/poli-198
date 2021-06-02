<h1> POLI 198 WI'21-SPR'21 - Data Cleaning Project: <br>
  2000-2016 Votes and Candidate Datasets, Brazilian Municipalities <h2>
<h2> INTRO </h2>
  <p> This purpose of this project is to use data cleaning to create a novel dataset that merges votes and candidate datasets of Brazilian mayoral elections from 2000-2016, pulled from the <a href="https://cepespdata.io/">CEPESP website</a>. As part of our data cleaning process, we used R to conduct exploratory data analysis, generate new variables, and replace missing data.
  <br><br>
The datasets on Candidates’ profiles can be downloaded from <a href="https://cepespdata.io/consulta/candidatos">here</a>. (I also call it candidate data).
  <br><br>
The datasets on Electoral Results can be downloaded from <a href="https://cepespdata.io/consulta/tse">here</a>. (I also call it votes data).
  </p>
  
<h2> DESCRIPTION OF FILES </h2>
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

  <h2> DESCRIPTION OF GENERATED VARIABLES </h2>
 Note, there will be NA or missing data in a few of our new generated variables for some of the years (mostly 2000 and 2004), because we also have votes and candidate datasets from 1996 that has not yet been included as part of the code and data wrangling process.
  <h3>total_mun_votes</h3>
  This variable sums total votes per municipality-election.
  <h3>PROP_VOTES</h3>
  This variable calculates the proportion of votes that each candidate received. It is QTDE_VOTOS/total_mun_votes.
  <h3>INCUMBENT</h3>
  This is a dummy variable. It is 1 if the candidate is an incumbent running for reelection, and 0 otherwise.
  <h3>INCUMBENT_WINS</h3>
  Also a dummy variable, it is 1 if the incumbent who ran for reelection won and 0 if not.
  <h3>TERM_LIMITED</h3>
  A dummy variable, it is equal to 1 if a candidate has served two consecutive terms (won two elections in a row), and 0 otherwise.
  <h3>NUM_CAND</h3>
  This variable indicates how many candidates are running for election in a municipality for a certain year. (These observations are typically 2-3 candidates).
  <h3>PROP_VOTES_WINNER</h3>
  This variable calculates the proportion of the votes for the winner in the election. (All rows within a same municipality will display the same number for the winner’s proportion of votes).
  <h3>PROP_VOTES_RUNNERUP</h3>
  This variable calculates the proportion of the votes for the runner-up in the election. (Similar to PROP_VOTES_WINNER, all rows within a same municipality will display the same number for the runner-up’s proportion of votes).
  <h3>WINNER_PARTY</h3>
  This variable lists the party of the winner for that election.
  <h3>runoff</h3>
  This is a dummy variable. It is equal to 1 if candidates running in a certain municipality proceeded to a second election, and equal to 0 otherwise.

















