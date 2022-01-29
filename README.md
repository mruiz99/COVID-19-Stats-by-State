# COVID-19 Stats by State

This Python script allows the user to construct objects which depict probable and confirmed COVID-19 case and death rates from each US state using visualization tools provided by Python modules Seaborn and Matplotlib.

Each object also provides statistics in the form of printed text once successfully constructed and executed.

Two classes Stats and Graph are used to extract, transform, and organize data to display graphs for COVID-19 data.

User must first create a Stats object with the following required parameters: 'state', 'currmo', 'lastmo'
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
'state' represents a US state which will need to be entered using abbreviation (capitalized)

'currmo' represents current month

'lastmo' represents last month
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Default values for 'curryear' and 'lastyear' are 22, which represent the year 2022
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
'curryear' represents current year

'lastyear' represents last year
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Values for months and years are whole integers.

In order to create a functioning Stats object, please keep in mind the following pseudocode:
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
  if current year is equal to last year:

    if current month is equal to last month:
    
      parameters will pass!
      
    else if current month is greater than last month:
    
      parameter will pass!
      
    else
    
      parameters will fail - last month cannot be greater than current month!

  else if current year is greater than last year:

    if current month is equal to last month:
    
      parameters will pass!
      
    else if current month is less than last month:
    
      parameters will pass!
      
    else
    
      parameters will pass!
      
      
  else
  
    parameters will fail - last year cannot be greater than current year
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

# Creating a proper Stats object

Stats object for the state of Maryland from June 2020 to January 2022
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
MD = Stats(state = "MD", currmo = 6, lastmo = 1, lastyear = 20)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Stats object for the state of New York for September 2021
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
NY = Stats(state = "NY", currmo = 9, lastmo = 9, curryear = 21, lastyear = 21)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Stats object for the state of Florida for January 2022
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
FL = Stats(state = "FL", currmo = 1, lastmo = 1)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Stats object for the state of California from October 2020 to February 2021
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
CA = Stats(state = "CA", currmo = 2, lastmo = 10, curryear = 21, lastyear = 20)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

After a successful creation of a Stats object, it can now be used to depict various graphs.  User must first create a Graph object using a Stats object attribute named 'allstats' as the parameter.

# Creating a proper Graph object
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
mdGraph = Graph(MD.allstats)

nyGraph = Graph(NY.allstats)

flGraph = Graph(FL.allstats)

caGraph = Graph(CA.allstats)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

After creating the Graph object, user must call the getGraph() method and provide a valid parameter to depict a specific graph.  A list of graph options are printed to the console after successful execution of the graphing method.  
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
"info":  depicts statistics, number of cases and deaths per day as a line graph

"monthly":  depicts statistics, number of cases and deaths per month as a line graph

"averages":  depicts all US states, average number of cases and deaths per day as a bar chart**

"totals":  depicts all US states, total number of cases and deaths within the date range as a bar chart**

"cfrir":  depicts all US states, case fatality ratio and incidence rates within the date range as a bar chart**

"vax":  depicts all US states, full vaccination rates for each state and a number for the entire country as of the present day**
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
**  All charts are shown in descending order

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
mdGraph.getGraph("monthly")

nyGraph.getGraph("info")

flGraph.getGraph("vax")

caGraph.getGraph("averages")
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

# Requirements

Python 3.X

Jupyter Notebook

https://jupyter.org/install

See Jupyter Notebook or Python files for the required imports, may need to install

All COVID-19 data obtained from the following repository: https://github.com/nytimes/covid-19-data

To receive the most up to date COVID data, clone repository, pull latest data, copy and paste 'us-states.csv' into this repository

# Sources

COVID-19 data provided by The New York Times, based on reports from state and local health agencies.

Estimated population density per state obtained from https://www.statista.com/statistics/183588/population-density-in-the-federal-states-of-the-us/

Estimated total square miles per state obtained from https://www.census.gov/geographies/reference-files/2010/geo/state-area.html

Estimated population for US states in 2020 obtained from https://www.census.gov/programs-surveys/popest/technical-documentation/research/evaluation-estimates/2020-evaluation-estimates/2010s-totals-national.html

Estimated vaccination rates per state obtained from API https://data.cdc.gov/resource/unsk-b7fc.json

# License

BSD 3-Clause License

Copyright (c) 2022, Miguel Ruiz

All rights reserved.

Redistribution and use in source and binary forms, with or without
modification, are permitted provided that the following conditions are met:

1. Redistributions of source code must retain the above copyright notice, this
   list of conditions and the following disclaimer.

2. Redistributions in binary form must reproduce the above copyright notice,
   this list of conditions and the following disclaimer in the documentation
   and/or other materials provided with the distribution.

3. Neither the name of the copyright holder nor the names of its
   contributors may be used to endorse or promote products derived from
   this software without specific prior written permission.

THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS "AS IS"
AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE
IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE
DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT HOLDER OR CONTRIBUTORS BE LIABLE
FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL
DAMAGES (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR
SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER
CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY,
OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE
OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.
