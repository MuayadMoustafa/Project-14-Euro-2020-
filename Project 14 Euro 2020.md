```python
import pandas as pd 
import numpy as np 
```


```python
er = pd.read_csv("D:/Courses/Projects/eurocup_2020_results.csv")
er 
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>stage</th>
      <th>date</th>
      <th>pens</th>
      <th>pens_home_score</th>
      <th>pens_away_score</th>
      <th>team_name_home</th>
      <th>team_name_away</th>
      <th>team_home_score</th>
      <th>team_away_score</th>
      <th>possession_home</th>
      <th>possession_away</th>
      <th>total_shots_home</th>
      <th>total_shots_away</th>
      <th>shots_on_target_home</th>
      <th>shots_on_target_away</th>
      <th>duels_won_home</th>
      <th>duels_won_away</th>
      <th>events_list</th>
      <th>lineup_home</th>
      <th>lineup_away</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Final</td>
      <td>11.07.2021</td>
      <td>True</td>
      <td>3</td>
      <td>2</td>
      <td>Italy</td>
      <td>England</td>
      <td>1</td>
      <td>1</td>
      <td>66%</td>
      <td>34%</td>
      <td>19</td>
      <td>6</td>
      <td>6</td>
      <td>2</td>
      <td>53%</td>
      <td>47%</td>
      <td>[{'event_team': 'away', 'event_time': " 2' ", ...</td>
      <td>[{'Player_Name': 'Insigne', 'Player_Number': '...</td>
      <td>[{'Player_Name': 'Kane', 'Player_Number': '9'}...</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Semi-finals</td>
      <td>07.07.2021</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>England</td>
      <td>Denmark</td>
      <td>2</td>
      <td>1</td>
      <td>59%</td>
      <td>41%</td>
      <td>20</td>
      <td>6</td>
      <td>10</td>
      <td>3</td>
      <td>50%</td>
      <td>50%</td>
      <td>[{'event_team': 'away', 'event_time': " 30' ",...</td>
      <td>[{'Player_Name': 'Kane', 'Player_Number': '9'}...</td>
      <td>[{'Player_Name': 'Krogh Damsgaard', 'Player_Nu...</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Semi-finals</td>
      <td>06.07.2021</td>
      <td>True</td>
      <td>4</td>
      <td>2</td>
      <td>Italy</td>
      <td>Spain</td>
      <td>1</td>
      <td>1</td>
      <td>29%</td>
      <td>71%</td>
      <td>7</td>
      <td>16</td>
      <td>4</td>
      <td>5</td>
      <td>49%</td>
      <td>51%</td>
      <td>[{'event_team': 'away', 'event_time': " 51' ",...</td>
      <td>[{'Player_Name': 'Insigne', 'Player_Number': '...</td>
      <td>[{'Player_Name': 'Torres', 'Player_Number': '1...</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Quarter-finals</td>
      <td>03.07.2021</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>Ukraine</td>
      <td>England</td>
      <td>0</td>
      <td>4</td>
      <td>48%</td>
      <td>52%</td>
      <td>7</td>
      <td>10</td>
      <td>2</td>
      <td>6</td>
      <td>42%</td>
      <td>59%</td>
      <td>[{'event_team': 'away', 'event_time': " 4' ", ...</td>
      <td>[{'Player_Name': 'Yaremchuk', 'Player_Number':...</td>
      <td>[{'Player_Name': 'Kane', 'Player_Number': '9'}...</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Quarter-finals</td>
      <td>03.07.2021</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>Czech Republic</td>
      <td>Denmark</td>
      <td>1</td>
      <td>2</td>
      <td>56%</td>
      <td>44%</td>
      <td>16</td>
      <td>11</td>
      <td>5</td>
      <td>7</td>
      <td>48%</td>
      <td>52%</td>
      <td>[{'event_team': 'away', 'event_time': " 5' ", ...</td>
      <td>[{'Player_Name': 'Schick', 'Player_Number': '1...</td>
      <td>[{'Player_Name': 'Dolberg', 'Player_Number': '...</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Quarter-finals</td>
      <td>02.07.2021</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>Belgium</td>
      <td>Italy</td>
      <td>1</td>
      <td>2</td>
      <td>46%</td>
      <td>54%</td>
      <td>10</td>
      <td>14</td>
      <td>4</td>
      <td>3</td>
      <td>58%</td>
      <td>42%</td>
      <td>[{'event_team': 'away', 'event_time': " 13' ",...</td>
      <td>[{'Player_Name': 'Lukaku', 'Player_Number': '9...</td>
      <td>[{'Player_Name': 'Insigne', 'Player_Number': '...</td>
    </tr>
    <tr>
      <th>6</th>
      <td>Quarter-finals</td>
      <td>02.07.2021</td>
      <td>True</td>
      <td>1</td>
      <td>3</td>
      <td>Switzerland</td>
      <td>Spain</td>
      <td>1</td>
      <td>1</td>
      <td>27%</td>
      <td>73%</td>
      <td>8</td>
      <td>28</td>
      <td>2</td>
      <td>10</td>
      <td>58%</td>
      <td>42%</td>
      <td>[{'event_team': 'away', 'event_time': " 8' ", ...</td>
      <td>[{'Player_Name': 'Seferovic', 'Player_Number':...</td>
      <td>[{'Player_Name': 'Sarabia', 'Player_Number': '...</td>
    </tr>
    <tr>
      <th>7</th>
      <td>Round of 16</td>
      <td>29.06.2021</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>Sweden</td>
      <td>Ukraine</td>
      <td>1</td>
      <td>2</td>
      <td>45%</td>
      <td>55%</td>
      <td>13</td>
      <td>15</td>
      <td>3</td>
      <td>4</td>
      <td>48%</td>
      <td>52%</td>
      <td>[{'event_team': 'away', 'event_time': " 27' ",...</td>
      <td>[{'Player_Name': 'Isak', 'Player_Number': '11'...</td>
      <td>[{'Player_Name': 'Yaremchuk', 'Player_Number':...</td>
    </tr>
    <tr>
      <th>8</th>
      <td>Round of 16</td>
      <td>29.06.2021</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>England</td>
      <td>Germany</td>
      <td>2</td>
      <td>0</td>
      <td>45%</td>
      <td>55%</td>
      <td>5</td>
      <td>9</td>
      <td>4</td>
      <td>3</td>
      <td>55%</td>
      <td>45%</td>
      <td>[{'event_team': 'home', 'event_time': " 8' ", ...</td>
      <td>[{'Player_Name': 'Sterling', 'Player_Number': ...</td>
      <td>[{'Player_Name': 'Werner', 'Player_Number': '1...</td>
    </tr>
    <tr>
      <th>9</th>
      <td>Round of 16</td>
      <td>28.06.2021</td>
      <td>True</td>
      <td>4</td>
      <td>5</td>
      <td>France</td>
      <td>Switzerland</td>
      <td>3</td>
      <td>3</td>
      <td>55%</td>
      <td>45%</td>
      <td>26</td>
      <td>12</td>
      <td>8</td>
      <td>5</td>
      <td>55%</td>
      <td>45%</td>
      <td>[{'event_team': 'away', 'event_time': " 15' ",...</td>
      <td>[{'Player_Name': 'Mbappe', 'Player_Number': '1...</td>
      <td>[{'Player_Name': 'Seferovic', 'Player_Number':...</td>
    </tr>
    <tr>
      <th>10</th>
      <td>Round of 16</td>
      <td>28.06.2021</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>Croatia</td>
      <td>Spain</td>
      <td>3</td>
      <td>5</td>
      <td>32%</td>
      <td>68%</td>
      <td>12</td>
      <td>23</td>
      <td>7</td>
      <td>10</td>
      <td>42%</td>
      <td>58%</td>
      <td>[{'event_team': 'home', 'event_time': " 20' ",...</td>
      <td>[{'Player_Name': 'Rebic', 'Player_Number': '17...</td>
      <td>[{'Player_Name': 'Sarabia', 'Player_Number': '...</td>
    </tr>
    <tr>
      <th>11</th>
      <td>Round of 16</td>
      <td>27.06.2021</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>Belgium</td>
      <td>Portugal</td>
      <td>1</td>
      <td>0</td>
      <td>42%</td>
      <td>58%</td>
      <td>6</td>
      <td>23</td>
      <td>1</td>
      <td>4</td>
      <td>48%</td>
      <td>52%</td>
      <td>[{'event_team': 'home', 'event_time': " 42' ",...</td>
      <td>[{'Player_Name': 'Lukaku', 'Player_Number': '9...</td>
      <td>[{'Player_Name': 'Jota', 'Player_Number': '21'...</td>
    </tr>
    <tr>
      <th>12</th>
      <td>Round of 16</td>
      <td>27.06.2021</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>Netherlands</td>
      <td>Czech Republic</td>
      <td>0</td>
      <td>2</td>
      <td>52%</td>
      <td>48%</td>
      <td>6</td>
      <td>12</td>
      <td>0</td>
      <td>5</td>
      <td>53%</td>
      <td>48%</td>
      <td>[{'event_team': 'home', 'event_time': " 46' ",...</td>
      <td>[{'Player_Name': 'Malen', 'Player_Number': '18...</td>
      <td>[{'Player_Name': 'Schick', 'Player_Number': '1...</td>
    </tr>
    <tr>
      <th>13</th>
      <td>Round of 16</td>
      <td>26.06.2021</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>Italy</td>
      <td>Austria</td>
      <td>2</td>
      <td>1</td>
      <td>52%</td>
      <td>48%</td>
      <td>27</td>
      <td>16</td>
      <td>6</td>
      <td>3</td>
      <td>50%</td>
      <td>50%</td>
      <td>[{'event_team': 'away', 'event_time': " 2' ", ...</td>
      <td>[{'Player_Name': 'Insigne', 'Player_Number': '...</td>
      <td>[{'Player_Name': 'Arnautovic', 'Player_Number'...</td>
    </tr>
    <tr>
      <th>14</th>
      <td>Round of 16</td>
      <td>26.06.2021</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>Wales</td>
      <td>Denmark</td>
      <td>0</td>
      <td>4</td>
      <td>47%</td>
      <td>53%</td>
      <td>11</td>
      <td>16</td>
      <td>1</td>
      <td>8</td>
      <td>39%</td>
      <td>61%</td>
      <td>[{'event_team': 'home', 'event_time': " 26' ",...</td>
      <td>[{'Player_Name': 'Moore', 'Player_Number': '13...</td>
      <td>[{'Player_Name': 'Dolberg', 'Player_Number': '...</td>
    </tr>
    <tr>
      <th>15</th>
      <td>Group stage: Matchday 3</td>
      <td>23.06.2021</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>Portugal</td>
      <td>France</td>
      <td>2</td>
      <td>2</td>
      <td>47%</td>
      <td>53%</td>
      <td>10</td>
      <td>11</td>
      <td>5</td>
      <td>5</td>
      <td>60%</td>
      <td>41%</td>
      <td>[{'event_team': 'away', 'event_time': " 27' ",...</td>
      <td>[{'Player_Name': 'Ronaldo', 'Player_Number': '...</td>
      <td>[{'Player_Name': 'Benzema', 'Player_Number': '...</td>
    </tr>
    <tr>
      <th>16</th>
      <td>Group stage: Matchday 3</td>
      <td>23.06.2021</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>Germany</td>
      <td>Hungary</td>
      <td>2</td>
      <td>2</td>
      <td>76%</td>
      <td>24%</td>
      <td>18</td>
      <td>9</td>
      <td>7</td>
      <td>4</td>
      <td>56%</td>
      <td>44%</td>
      <td>[{'event_team': 'away', 'event_time': " 11' ",...</td>
      <td>[{'Player_Name': 'Gnabry', 'Player_Number': '1...</td>
      <td>[{'Player_Name': 'Szalai', 'Player_Number': '9...</td>
    </tr>
    <tr>
      <th>17</th>
      <td>Group stage: Matchday 3</td>
      <td>23.06.2021</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>Sweden</td>
      <td>Poland</td>
      <td>3</td>
      <td>2</td>
      <td>33%</td>
      <td>67%</td>
      <td>11</td>
      <td>18</td>
      <td>4</td>
      <td>6</td>
      <td>47%</td>
      <td>53%</td>
      <td>[{'event_team': 'home', 'event_time': " 2' ", ...</td>
      <td>[{'Player_Name': 'Isak', 'Player_Number': '11'...</td>
      <td>[{'Player_Name': 'Lewandowski', 'Player_Number...</td>
    </tr>
    <tr>
      <th>18</th>
      <td>Group stage: Matchday 3</td>
      <td>23.06.2021</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>Slovakia</td>
      <td>Spain</td>
      <td>0</td>
      <td>5</td>
      <td>34%</td>
      <td>66%</td>
      <td>3</td>
      <td>19</td>
      <td>0</td>
      <td>9</td>
      <td>44%</td>
      <td>56%</td>
      <td>[{'event_team': 'home', 'event_time': " 11' ",...</td>
      <td>[{'Player_Name': 'Duda', 'Player_Number': '8'}...</td>
      <td>[{'Player_Name': 'Moreno', 'Player_Number': '9...</td>
    </tr>
    <tr>
      <th>19</th>
      <td>Group stage: Matchday 3</td>
      <td>22.06.2021</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>Croatia</td>
      <td>Scotland</td>
      <td>3</td>
      <td>1</td>
      <td>67%</td>
      <td>33%</td>
      <td>11</td>
      <td>11</td>
      <td>6</td>
      <td>3</td>
      <td>53%</td>
      <td>47%</td>
      <td>[{'event_team': 'home', 'event_time': " 17' ",...</td>
      <td>[{'Player_Name': 'Perisic', 'Player_Number': '...</td>
      <td>[{'Player_Name': 'Adams', 'Player_Number': '10...</td>
    </tr>
    <tr>
      <th>20</th>
      <td>Group stage: Matchday 3</td>
      <td>22.06.2021</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>Czech Republic</td>
      <td>England</td>
      <td>0</td>
      <td>1</td>
      <td>43%</td>
      <td>57%</td>
      <td>7</td>
      <td>5</td>
      <td>1</td>
      <td>3</td>
      <td>47%</td>
      <td>53%</td>
      <td>[{'event_team': 'away', 'event_time': " 12' ",...</td>
      <td>[{'Player_Name': 'Schick', 'Player_Number': '1...</td>
      <td>[{'Player_Name': 'Kane', 'Player_Number': '9'}...</td>
    </tr>
    <tr>
      <th>21</th>
      <td>Group stage: Matchday 3</td>
      <td>21.06.2021</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>Finland</td>
      <td>Belgium</td>
      <td>0</td>
      <td>2</td>
      <td>39%</td>
      <td>61%</td>
      <td>7</td>
      <td>17</td>
      <td>1</td>
      <td>7</td>
      <td>40%</td>
      <td>61%</td>
      <td>[{'event_team': 'home', 'event_time': " 59' ",...</td>
      <td>[{'Player_Name': 'Pohjanpalo', 'Player_Number'...</td>
      <td>[{'Player_Name': 'Lukaku', 'Player_Number': '9...</td>
    </tr>
    <tr>
      <th>22</th>
      <td>Group stage: Matchday 3</td>
      <td>21.06.2021</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>Russia</td>
      <td>Denmark</td>
      <td>1</td>
      <td>4</td>
      <td>35%</td>
      <td>65%</td>
      <td>6</td>
      <td>16</td>
      <td>2</td>
      <td>10</td>
      <td>59%</td>
      <td>41%</td>
      <td>[{'event_team': 'home', 'event_time': " 28' ",...</td>
      <td>[{'Player_Name': 'Dzyuba', 'Player_Number': '2...</td>
      <td>[{'Player_Name': 'Poulsen', 'Player_Number': '...</td>
    </tr>
    <tr>
      <th>23</th>
      <td>Group stage: Matchday 3</td>
      <td>21.06.2021</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>Ukraine</td>
      <td>Austria</td>
      <td>0</td>
      <td>1</td>
      <td>51%</td>
      <td>49%</td>
      <td>5</td>
      <td>18</td>
      <td>1</td>
      <td>4</td>
      <td>43%</td>
      <td>57%</td>
      <td>[{'event_team': 'away', 'event_time': " 21' ",...</td>
      <td>[{'Player_Name': 'Malinovskyi', 'Player_Number...</td>
      <td>[{'Player_Name': 'Arnautovic', 'Player_Number'...</td>
    </tr>
    <tr>
      <th>24</th>
      <td>Group stage: Matchday 3</td>
      <td>21.06.2021</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>North Macedonia</td>
      <td>Netherlands</td>
      <td>0</td>
      <td>3</td>
      <td>41%</td>
      <td>59%</td>
      <td>13</td>
      <td>17</td>
      <td>1</td>
      <td>7</td>
      <td>39%</td>
      <td>61%</td>
      <td>[{'event_team': 'home', 'event_time': " 18' ",...</td>
      <td>[{'Player_Name': 'Pandev', 'Player_Number': '1...</td>
      <td>[{'Player_Name': 'Malen', 'Player_Number': '18...</td>
    </tr>
    <tr>
      <th>25</th>
      <td>Group stage: Matchday 3</td>
      <td>20.06.2021</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>Italy</td>
      <td>Wales</td>
      <td>1</td>
      <td>0</td>
      <td>70%</td>
      <td>30%</td>
      <td>23</td>
      <td>3</td>
      <td>6</td>
      <td>1</td>
      <td>56%</td>
      <td>44%</td>
      <td>[{'event_team': 'home', 'event_time': " 39' ",...</td>
      <td>[{'Player_Name': 'Chiesa', 'Player_Number': '1...</td>
      <td>[{'Player_Name': 'James', 'Player_Number': '20...</td>
    </tr>
    <tr>
      <th>26</th>
      <td>Group stage: Matchday 3</td>
      <td>20.06.2021</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>Switzerland</td>
      <td>Turkey</td>
      <td>3</td>
      <td>1</td>
      <td>51%</td>
      <td>49%</td>
      <td>23</td>
      <td>19</td>
      <td>10</td>
      <td>6</td>
      <td>53%</td>
      <td>47%</td>
      <td>[{'event_team': 'home', 'event_time': " 6' ", ...</td>
      <td>[{'Player_Name': 'Embolo', 'Player_Number': '7...</td>
      <td>[{'Player_Name': 'Yilmaz', 'Player_Number': '1...</td>
    </tr>
    <tr>
      <th>27</th>
      <td>Group stage: Matchday 2</td>
      <td>19.06.2021</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>Spain</td>
      <td>Poland</td>
      <td>1</td>
      <td>1</td>
      <td>77%</td>
      <td>23%</td>
      <td>12</td>
      <td>5</td>
      <td>5</td>
      <td>2</td>
      <td>42%</td>
      <td>58%</td>
      <td>[{'event_team': 'home', 'event_time': " 25' ",...</td>
      <td>[{'Player_Name': 'Olmo Carvajal', 'Player_Numb...</td>
      <td>[{'Player_Name': 'Lewandowski', 'Player_Number...</td>
    </tr>
    <tr>
      <th>28</th>
      <td>Group stage: Matchday 2</td>
      <td>19.06.2021</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>Portugal</td>
      <td>Germany</td>
      <td>2</td>
      <td>4</td>
      <td>42%</td>
      <td>58%</td>
      <td>7</td>
      <td>12</td>
      <td>2</td>
      <td>7</td>
      <td>55%</td>
      <td>45%</td>
      <td>[{'event_team': 'home', 'event_time': " 15' ",...</td>
      <td>[{'Player_Name': 'Ronaldo', 'Player_Number': '...</td>
      <td>[{'Player_Name': 'Gnabry', 'Player_Number': '1...</td>
    </tr>
    <tr>
      <th>29</th>
      <td>Group stage: Matchday 2</td>
      <td>19.06.2021</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>Hungary</td>
      <td>France</td>
      <td>1</td>
      <td>1</td>
      <td>33%</td>
      <td>67%</td>
      <td>5</td>
      <td>15</td>
      <td>3</td>
      <td>4</td>
      <td>40%</td>
      <td>60%</td>
      <td>[{'event_team': 'away', 'event_time': " 10' ",...</td>
      <td>[{'Player_Name': 'Szalai', 'Player_Number': '9...</td>
      <td>[{'Player_Name': 'Mbappe', 'Player_Number': '1...</td>
    </tr>
    <tr>
      <th>30</th>
      <td>Group stage: Matchday 2</td>
      <td>18.06.2021</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>England</td>
      <td>Scotland</td>
      <td>0</td>
      <td>0</td>
      <td>61%</td>
      <td>39%</td>
      <td>9</td>
      <td>11</td>
      <td>1</td>
      <td>2</td>
      <td>54%</td>
      <td>46%</td>
      <td>[{'event_team': 'away', 'event_time': " 15' ",...</td>
      <td>[{'Player_Name': 'Sterling', 'Player_Number': ...</td>
      <td>[{'Player_Name': 'Dykes', 'Player_Number': '9'...</td>
    </tr>
    <tr>
      <th>31</th>
      <td>Group stage: Matchday 2</td>
      <td>18.06.2021</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>Croatia</td>
      <td>Czech Republic</td>
      <td>1</td>
      <td>1</td>
      <td>48%</td>
      <td>52%</td>
      <td>11</td>
      <td>11</td>
      <td>2</td>
      <td>1</td>
      <td>51%</td>
      <td>49%</td>
      <td>[{'event_team': 'home', 'event_time': " 35' ",...</td>
      <td>[{'Player_Name': 'Rebic', 'Player_Number': '17...</td>
      <td>[{'Player_Name': 'Schick', 'Player_Number': '1...</td>
    </tr>
    <tr>
      <th>32</th>
      <td>Group stage: Matchday 2</td>
      <td>18.06.2021</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>Sweden</td>
      <td>Slovakia</td>
      <td>1</td>
      <td>0</td>
      <td>41%</td>
      <td>59%</td>
      <td>13</td>
      <td>10</td>
      <td>4</td>
      <td>0</td>
      <td>44%</td>
      <td>56%</td>
      <td>[{'event_team': 'home', 'event_time': " 23' ",...</td>
      <td>[{'Player_Name': 'Berg', 'Player_Number': '9'}...</td>
      <td>[{'Player_Name': 'Duda', 'Player_Number': '8'}...</td>
    </tr>
    <tr>
      <th>33</th>
      <td>Group stage: Matchday 2</td>
      <td>17.06.2021</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>Netherlands</td>
      <td>Austria</td>
      <td>2</td>
      <td>0</td>
      <td>46%</td>
      <td>54%</td>
      <td>14</td>
      <td>9</td>
      <td>4</td>
      <td>1</td>
      <td>52%</td>
      <td>48%</td>
      <td>[{'event_team': 'away', 'event_time': " 10' ",...</td>
      <td>[{'Player_Name': 'Depay', 'Player_Number': '10...</td>
      <td>[{'Player_Name': 'Gregoritsch', 'Player_Number...</td>
    </tr>
    <tr>
      <th>34</th>
      <td>Group stage: Matchday 2</td>
      <td>17.06.2021</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>Denmark</td>
      <td>Belgium</td>
      <td>1</td>
      <td>2</td>
      <td>47%</td>
      <td>53%</td>
      <td>21</td>
      <td>6</td>
      <td>5</td>
      <td>5</td>
      <td>56%</td>
      <td>44%</td>
      <td>[{'event_team': 'home', 'event_time': " 2' ", ...</td>
      <td>[{'Player_Name': 'Poulsen', 'Player_Number': '...</td>
      <td>[{'Player_Name': 'Lukaku', 'Player_Number': '9...</td>
    </tr>
    <tr>
      <th>35</th>
      <td>Group stage: Matchday 2</td>
      <td>17.06.2021</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>Ukraine</td>
      <td>North Macedonia</td>
      <td>2</td>
      <td>1</td>
      <td>53%</td>
      <td>47%</td>
      <td>17</td>
      <td>13</td>
      <td>8</td>
      <td>5</td>
      <td>46%</td>
      <td>54%</td>
      <td>[{'event_team': 'home', 'event_time': " 29' ",...</td>
      <td>[{'Player_Name': 'Malinovskyi', 'Player_Number...</td>
      <td>[{'Player_Name': 'Elmas', 'Player_Number': '21...</td>
    </tr>
    <tr>
      <th>36</th>
      <td>Group stage: Matchday 2</td>
      <td>16.06.2021</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>Italy</td>
      <td>Switzerland</td>
      <td>3</td>
      <td>0</td>
      <td>49%</td>
      <td>51%</td>
      <td>13</td>
      <td>6</td>
      <td>3</td>
      <td>1</td>
      <td>43%</td>
      <td>57%</td>
      <td>[{'event_team': 'home', 'event_time': " 19' ",...</td>
      <td>[{'Player_Name': 'Insigne', 'Player_Number': '...</td>
      <td>[{'Player_Name': 'Embolo', 'Player_Number': '7...</td>
    </tr>
    <tr>
      <th>37</th>
      <td>Group stage: Matchday 2</td>
      <td>16.06.2021</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>Turkey</td>
      <td>Wales</td>
      <td>0</td>
      <td>2</td>
      <td>64%</td>
      <td>36%</td>
      <td>18</td>
      <td>16</td>
      <td>6</td>
      <td>7</td>
      <td>40%</td>
      <td>60%</td>
      <td>[{'event_team': 'away', 'event_time': " 42' ",...</td>
      <td>[{'Player_Name': 'Yilmaz', 'Player_Number': '1...</td>
      <td>[{'Player_Name': 'Moore', 'Player_Number': '13...</td>
    </tr>
    <tr>
      <th>38</th>
      <td>Group stage: Matchday 2</td>
      <td>16.06.2021</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>Finland</td>
      <td>Russia</td>
      <td>0</td>
      <td>1</td>
      <td>41%</td>
      <td>59%</td>
      <td>11</td>
      <td>14</td>
      <td>1</td>
      <td>3</td>
      <td>53%</td>
      <td>47%</td>
      <td>[{'event_team': 'home', 'event_time': " 4' ", ...</td>
      <td>[{'Player_Name': 'Pohjanpalo', 'Player_Number'...</td>
      <td>[{'Player_Name': 'Dzyuba', 'Player_Number': '2...</td>
    </tr>
    <tr>
      <th>39</th>
      <td>Group stage: Matchday 1</td>
      <td>15.06.2021</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>France</td>
      <td>Germany</td>
      <td>1</td>
      <td>0</td>
      <td>38%</td>
      <td>62%</td>
      <td>4</td>
      <td>10</td>
      <td>1</td>
      <td>1</td>
      <td>60%</td>
      <td>40%</td>
      <td>[{'event_team': 'away', 'event_time': " 7' ", ...</td>
      <td>[{'Player_Name': 'Mbappe', 'Player_Number': '1...</td>
      <td>[{'Player_Name': 'Gnabry', 'Player_Number': '1...</td>
    </tr>
    <tr>
      <th>40</th>
      <td>Group stage: Matchday 1</td>
      <td>15.06.2021</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>Hungary</td>
      <td>Portugal</td>
      <td>0</td>
      <td>3</td>
      <td>30%</td>
      <td>70%</td>
      <td>5</td>
      <td>11</td>
      <td>3</td>
      <td>7</td>
      <td>48%</td>
      <td>52%</td>
      <td>[{'event_team': 'away', 'event_time': " 38' ",...</td>
      <td>[{'Player_Name': 'Szalai', 'Player_Number': '9...</td>
      <td>[{'Player_Name': 'Ronaldo', 'Player_Number': '...</td>
    </tr>
    <tr>
      <th>41</th>
      <td>Group stage: Matchday 1</td>
      <td>14.06.2021</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>Spain</td>
      <td>Sweden</td>
      <td>0</td>
      <td>0</td>
      <td>86%</td>
      <td>14%</td>
      <td>17</td>
      <td>4</td>
      <td>5</td>
      <td>1</td>
      <td>63%</td>
      <td>38%</td>
      <td>[{'event_team': 'away', 'event_time': " 55' ",...</td>
      <td>[{'Player_Name': 'Olmo Carvajal', 'Player_Numb...</td>
      <td>[{'Player_Name': 'Isak', 'Player_Number': '11'...</td>
    </tr>
    <tr>
      <th>42</th>
      <td>Group stage: Matchday 1</td>
      <td>14.06.2021</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>Poland</td>
      <td>Slovakia</td>
      <td>1</td>
      <td>2</td>
      <td>58%</td>
      <td>42%</td>
      <td>17</td>
      <td>11</td>
      <td>3</td>
      <td>2</td>
      <td>51%</td>
      <td>49%</td>
      <td>[{'event_team': 'away', 'event_time': " 18' ",...</td>
      <td>[{'Player_Name': 'Zielinski', 'Player_Number':...</td>
      <td>[{'Player_Name': 'Duda', 'Player_Number': '8'}...</td>
    </tr>
    <tr>
      <th>43</th>
      <td>Group stage: Matchday 1</td>
      <td>14.06.2021</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>Scotland</td>
      <td>Czech Republic</td>
      <td>0</td>
      <td>2</td>
      <td>58%</td>
      <td>42%</td>
      <td>19</td>
      <td>10</td>
      <td>4</td>
      <td>7</td>
      <td>54%</td>
      <td>46%</td>
      <td>[{'event_team': 'away', 'event_time': " 42' ",...</td>
      <td>[{'Player_Name': 'Christie', 'Player_Number': ...</td>
      <td>[{'Player_Name': 'Schick', 'Player_Number': '1...</td>
    </tr>
    <tr>
      <th>44</th>
      <td>Group stage: Matchday 1</td>
      <td>13.06.2021</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>Netherlands</td>
      <td>Ukraine</td>
      <td>3</td>
      <td>2</td>
      <td>62%</td>
      <td>38%</td>
      <td>15</td>
      <td>7</td>
      <td>7</td>
      <td>5</td>
      <td>45%</td>
      <td>55%</td>
      <td>[{'event_team': 'away', 'event_time': " 13' ",...</td>
      <td>[{'Player_Name': 'Depay', 'Player_Number': '10...</td>
      <td>[{'Player_Name': 'Zubkov', 'Player_Number': '2...</td>
    </tr>
    <tr>
      <th>45</th>
      <td>Group stage: Matchday 1</td>
      <td>13.06.2021</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>Austria</td>
      <td>North Macedonia</td>
      <td>3</td>
      <td>1</td>
      <td>63%</td>
      <td>37%</td>
      <td>10</td>
      <td>7</td>
      <td>6</td>
      <td>2</td>
      <td>50%</td>
      <td>50%</td>
      <td>[{'event_team': 'home', 'event_time': " 18' ",...</td>
      <td>[{'Player_Name': 'Baumgartner', 'Player_Number...</td>
      <td>[{'Player_Name': 'Trajkovski', 'Player_Number'...</td>
    </tr>
    <tr>
      <th>46</th>
      <td>Group stage: Matchday 1</td>
      <td>13.06.2021</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>England</td>
      <td>Croatia</td>
      <td>1</td>
      <td>0</td>
      <td>49%</td>
      <td>51%</td>
      <td>8</td>
      <td>8</td>
      <td>2</td>
      <td>2</td>
      <td>46%</td>
      <td>54%</td>
      <td>[{'event_team': 'away', 'event_time': " 42' ",...</td>
      <td>[{'Player_Name': 'Sterling', 'Player_Number': ...</td>
      <td>[{'Player_Name': 'Perisic', 'Player_Number': '...</td>
    </tr>
    <tr>
      <th>47</th>
      <td>Group stage: Matchday 1</td>
      <td>12.06.2021</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>Belgium</td>
      <td>Russia</td>
      <td>3</td>
      <td>0</td>
      <td>67%</td>
      <td>33%</td>
      <td>9</td>
      <td>5</td>
      <td>4</td>
      <td>1</td>
      <td>52%</td>
      <td>48%</td>
      <td>[{'event_team': 'home', 'event_time': " 10' ",...</td>
      <td>[{'Player_Name': 'Carrasco', 'Player_Number': ...</td>
      <td>[{'Player_Name': 'Dzyuba', 'Player_Number': '2...</td>
    </tr>
    <tr>
      <th>48</th>
      <td>Group stage: Matchday 1</td>
      <td>12.06.2021</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>Denmark</td>
      <td>Finland</td>
      <td>0</td>
      <td>1</td>
      <td>70%</td>
      <td>30%</td>
      <td>22</td>
      <td>1</td>
      <td>6</td>
      <td>1</td>
      <td>53%</td>
      <td>47%</td>
      <td>[{'event_team': 'away', 'event_time': " 4' ", ...</td>
      <td>[{'Player_Name': 'Braithwaite', 'Player_Number...</td>
      <td>[{'Player_Name': 'Pukki', 'Player_Number': '10...</td>
    </tr>
    <tr>
      <th>49</th>
      <td>Group stage: Matchday 1</td>
      <td>12.06.2021</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>Wales</td>
      <td>Switzerland</td>
      <td>1</td>
      <td>1</td>
      <td>35%</td>
      <td>65%</td>
      <td>9</td>
      <td>18</td>
      <td>2</td>
      <td>4</td>
      <td>46%</td>
      <td>55%</td>
      <td>[{'event_team': 'away', 'event_time': " 30' ",...</td>
      <td>[{'Player_Name': 'Moore', 'Player_Number': '13...</td>
      <td>[{'Player_Name': 'Embolo', 'Player_Number': '7...</td>
    </tr>
    <tr>
      <th>50</th>
      <td>Group stage: Matchday 1</td>
      <td>11.06.2021</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>Turkey</td>
      <td>Italy</td>
      <td>0</td>
      <td>3</td>
      <td>36%</td>
      <td>64%</td>
      <td>3</td>
      <td>24</td>
      <td>0</td>
      <td>8</td>
      <td>51%</td>
      <td>49%</td>
      <td>[{'event_team': 'home', 'event_time': " 45' ",...</td>
      <td>[{'Player_Name': 'Yilmaz', 'Player_Number': '1...</td>
      <td>[{'Player_Name': 'Insigne', 'Player_Number': '...</td>
    </tr>
  </tbody>
</table>
</div>




```python
er.describe()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>team_home_score</th>
      <th>team_away_score</th>
      <th>total_shots_home</th>
      <th>total_shots_away</th>
      <th>shots_on_target_home</th>
      <th>shots_on_target_away</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>count</th>
      <td>51.000000</td>
      <td>51.000000</td>
      <td>51.000000</td>
      <td>51.000000</td>
      <td>51.000000</td>
      <td>51.000000</td>
    </tr>
    <tr>
      <th>mean</th>
      <td>1.196078</td>
      <td>1.588235</td>
      <td>12.137255</td>
      <td>12.235294</td>
      <td>3.803922</td>
      <td>4.352941</td>
    </tr>
    <tr>
      <th>std</th>
      <td>1.077397</td>
      <td>1.344269</td>
      <td>6.190378</td>
      <td>5.788223</td>
      <td>2.545738</td>
      <td>2.681966</td>
    </tr>
    <tr>
      <th>min</th>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>3.000000</td>
      <td>1.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
    </tr>
    <tr>
      <th>25%</th>
      <td>0.000000</td>
      <td>1.000000</td>
      <td>7.000000</td>
      <td>8.500000</td>
      <td>2.000000</td>
      <td>2.000000</td>
    </tr>
    <tr>
      <th>50%</th>
      <td>1.000000</td>
      <td>1.000000</td>
      <td>11.000000</td>
      <td>11.000000</td>
      <td>4.000000</td>
      <td>4.000000</td>
    </tr>
    <tr>
      <th>75%</th>
      <td>2.000000</td>
      <td>2.000000</td>
      <td>17.000000</td>
      <td>16.000000</td>
      <td>6.000000</td>
      <td>6.500000</td>
    </tr>
    <tr>
      <th>max</th>
      <td>3.000000</td>
      <td>5.000000</td>
      <td>27.000000</td>
      <td>28.000000</td>
      <td>10.000000</td>
      <td>10.000000</td>
    </tr>
  </tbody>
</table>
</div>




```python
er[["stage", "date"]]
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>stage</th>
      <th>date</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Final</td>
      <td>11.07.2021</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Semi-finals</td>
      <td>07.07.2021</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Semi-finals</td>
      <td>06.07.2021</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Quarter-finals</td>
      <td>03.07.2021</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Quarter-finals</td>
      <td>03.07.2021</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Quarter-finals</td>
      <td>02.07.2021</td>
    </tr>
    <tr>
      <th>6</th>
      <td>Quarter-finals</td>
      <td>02.07.2021</td>
    </tr>
    <tr>
      <th>7</th>
      <td>Round of 16</td>
      <td>29.06.2021</td>
    </tr>
    <tr>
      <th>8</th>
      <td>Round of 16</td>
      <td>29.06.2021</td>
    </tr>
    <tr>
      <th>9</th>
      <td>Round of 16</td>
      <td>28.06.2021</td>
    </tr>
    <tr>
      <th>10</th>
      <td>Round of 16</td>
      <td>28.06.2021</td>
    </tr>
    <tr>
      <th>11</th>
      <td>Round of 16</td>
      <td>27.06.2021</td>
    </tr>
    <tr>
      <th>12</th>
      <td>Round of 16</td>
      <td>27.06.2021</td>
    </tr>
    <tr>
      <th>13</th>
      <td>Round of 16</td>
      <td>26.06.2021</td>
    </tr>
    <tr>
      <th>14</th>
      <td>Round of 16</td>
      <td>26.06.2021</td>
    </tr>
    <tr>
      <th>15</th>
      <td>Group stage: Matchday 3</td>
      <td>23.06.2021</td>
    </tr>
    <tr>
      <th>16</th>
      <td>Group stage: Matchday 3</td>
      <td>23.06.2021</td>
    </tr>
    <tr>
      <th>17</th>
      <td>Group stage: Matchday 3</td>
      <td>23.06.2021</td>
    </tr>
    <tr>
      <th>18</th>
      <td>Group stage: Matchday 3</td>
      <td>23.06.2021</td>
    </tr>
    <tr>
      <th>19</th>
      <td>Group stage: Matchday 3</td>
      <td>22.06.2021</td>
    </tr>
    <tr>
      <th>20</th>
      <td>Group stage: Matchday 3</td>
      <td>22.06.2021</td>
    </tr>
    <tr>
      <th>21</th>
      <td>Group stage: Matchday 3</td>
      <td>21.06.2021</td>
    </tr>
    <tr>
      <th>22</th>
      <td>Group stage: Matchday 3</td>
      <td>21.06.2021</td>
    </tr>
    <tr>
      <th>23</th>
      <td>Group stage: Matchday 3</td>
      <td>21.06.2021</td>
    </tr>
    <tr>
      <th>24</th>
      <td>Group stage: Matchday 3</td>
      <td>21.06.2021</td>
    </tr>
    <tr>
      <th>25</th>
      <td>Group stage: Matchday 3</td>
      <td>20.06.2021</td>
    </tr>
    <tr>
      <th>26</th>
      <td>Group stage: Matchday 3</td>
      <td>20.06.2021</td>
    </tr>
    <tr>
      <th>27</th>
      <td>Group stage: Matchday 2</td>
      <td>19.06.2021</td>
    </tr>
    <tr>
      <th>28</th>
      <td>Group stage: Matchday 2</td>
      <td>19.06.2021</td>
    </tr>
    <tr>
      <th>29</th>
      <td>Group stage: Matchday 2</td>
      <td>19.06.2021</td>
    </tr>
    <tr>
      <th>30</th>
      <td>Group stage: Matchday 2</td>
      <td>18.06.2021</td>
    </tr>
    <tr>
      <th>31</th>
      <td>Group stage: Matchday 2</td>
      <td>18.06.2021</td>
    </tr>
    <tr>
      <th>32</th>
      <td>Group stage: Matchday 2</td>
      <td>18.06.2021</td>
    </tr>
    <tr>
      <th>33</th>
      <td>Group stage: Matchday 2</td>
      <td>17.06.2021</td>
    </tr>
    <tr>
      <th>34</th>
      <td>Group stage: Matchday 2</td>
      <td>17.06.2021</td>
    </tr>
    <tr>
      <th>35</th>
      <td>Group stage: Matchday 2</td>
      <td>17.06.2021</td>
    </tr>
    <tr>
      <th>36</th>
      <td>Group stage: Matchday 2</td>
      <td>16.06.2021</td>
    </tr>
    <tr>
      <th>37</th>
      <td>Group stage: Matchday 2</td>
      <td>16.06.2021</td>
    </tr>
    <tr>
      <th>38</th>
      <td>Group stage: Matchday 2</td>
      <td>16.06.2021</td>
    </tr>
    <tr>
      <th>39</th>
      <td>Group stage: Matchday 1</td>
      <td>15.06.2021</td>
    </tr>
    <tr>
      <th>40</th>
      <td>Group stage: Matchday 1</td>
      <td>15.06.2021</td>
    </tr>
    <tr>
      <th>41</th>
      <td>Group stage: Matchday 1</td>
      <td>14.06.2021</td>
    </tr>
    <tr>
      <th>42</th>
      <td>Group stage: Matchday 1</td>
      <td>14.06.2021</td>
    </tr>
    <tr>
      <th>43</th>
      <td>Group stage: Matchday 1</td>
      <td>14.06.2021</td>
    </tr>
    <tr>
      <th>44</th>
      <td>Group stage: Matchday 1</td>
      <td>13.06.2021</td>
    </tr>
    <tr>
      <th>45</th>
      <td>Group stage: Matchday 1</td>
      <td>13.06.2021</td>
    </tr>
    <tr>
      <th>46</th>
      <td>Group stage: Matchday 1</td>
      <td>13.06.2021</td>
    </tr>
    <tr>
      <th>47</th>
      <td>Group stage: Matchday 1</td>
      <td>12.06.2021</td>
    </tr>
    <tr>
      <th>48</th>
      <td>Group stage: Matchday 1</td>
      <td>12.06.2021</td>
    </tr>
    <tr>
      <th>49</th>
      <td>Group stage: Matchday 1</td>
      <td>12.06.2021</td>
    </tr>
    <tr>
      <th>50</th>
      <td>Group stage: Matchday 1</td>
      <td>11.06.2021</td>
    </tr>
  </tbody>
</table>
</div>




```python
print(len(er.stage))
```

    51
    


```python
print(len(er.columns))
```

    20
    


```python
er.dtypes
```




    stage                   object
    date                    object
    pens                      bool
    pens_home_score         object
    pens_away_score         object
    team_name_home          object
    team_name_away          object
    team_home_score          int64
    team_away_score          int64
    possession_home         object
    possession_away         object
    total_shots_home         int64
    total_shots_away         int64
    shots_on_target_home     int64
    shots_on_target_away     int64
    duels_won_home          object
    duels_won_away          object
    events_list             object
    lineup_home             object
    lineup_away             object
    dtype: object




```python
er.columns
```




    Index(['stage', 'date', 'pens', 'pens_home_score', 'pens_away_score',
           'team_name_home', 'team_name_away', 'team_home_score',
           'team_away_score', 'possession_home', 'possession_away',
           'total_shots_home', 'total_shots_away', 'shots_on_target_home',
           'shots_on_target_away', 'duels_won_home', 'duels_won_away',
           'events_list', 'lineup_home', 'lineup_away'],
          dtype='object')




```python
er.index
```




    RangeIndex(start=0, stop=51, step=1)




```python
er.abs
```




    <bound method NDFrame.abs of                         stage          date   pens pens_home_score  \
    0                      Final     11.07.2021   True               3   
    1                Semi-finals    07.07.2021   False           False   
    2                Semi-finals     06.07.2021   True               4   
    3             Quarter-finals    03.07.2021   False           False   
    4             Quarter-finals    03.07.2021   False           False   
    5             Quarter-finals    02.07.2021   False           False   
    6             Quarter-finals     02.07.2021   True               1   
    7                Round of 16    29.06.2021   False           False   
    8                Round of 16    29.06.2021   False           False   
    9                Round of 16     28.06.2021   True               4   
    10               Round of 16    28.06.2021   False           False   
    11               Round of 16    27.06.2021   False           False   
    12               Round of 16    27.06.2021   False           False   
    13               Round of 16    26.06.2021   False           False   
    14               Round of 16    26.06.2021   False           False   
    15   Group stage: Matchday 3    23.06.2021   False           False   
    16   Group stage: Matchday 3    23.06.2021   False           False   
    17   Group stage: Matchday 3    23.06.2021   False           False   
    18   Group stage: Matchday 3    23.06.2021   False           False   
    19   Group stage: Matchday 3    22.06.2021   False           False   
    20   Group stage: Matchday 3    22.06.2021   False           False   
    21   Group stage: Matchday 3    21.06.2021   False           False   
    22   Group stage: Matchday 3    21.06.2021   False           False   
    23   Group stage: Matchday 3    21.06.2021   False           False   
    24   Group stage: Matchday 3    21.06.2021   False           False   
    25   Group stage: Matchday 3    20.06.2021   False           False   
    26   Group stage: Matchday 3    20.06.2021   False           False   
    27   Group stage: Matchday 2    19.06.2021   False           False   
    28   Group stage: Matchday 2    19.06.2021   False           False   
    29   Group stage: Matchday 2    19.06.2021   False           False   
    30   Group stage: Matchday 2    18.06.2021   False           False   
    31   Group stage: Matchday 2    18.06.2021   False           False   
    32   Group stage: Matchday 2    18.06.2021   False           False   
    33   Group stage: Matchday 2    17.06.2021   False           False   
    34   Group stage: Matchday 2    17.06.2021   False           False   
    35   Group stage: Matchday 2    17.06.2021   False           False   
    36   Group stage: Matchday 2    16.06.2021   False           False   
    37   Group stage: Matchday 2    16.06.2021   False           False   
    38   Group stage: Matchday 2    16.06.2021   False           False   
    39   Group stage: Matchday 1    15.06.2021   False           False   
    40   Group stage: Matchday 1    15.06.2021   False           False   
    41   Group stage: Matchday 1    14.06.2021   False           False   
    42   Group stage: Matchday 1    14.06.2021   False           False   
    43   Group stage: Matchday 1    14.06.2021   False           False   
    44   Group stage: Matchday 1    13.06.2021   False           False   
    45   Group stage: Matchday 1    13.06.2021   False           False   
    46   Group stage: Matchday 1    13.06.2021   False           False   
    47   Group stage: Matchday 1    12.06.2021   False           False   
    48   Group stage: Matchday 1    12.06.2021   False           False   
    49   Group stage: Matchday 1    12.06.2021   False           False   
    50   Group stage: Matchday 1    11.06.2021   False           False   
    
       pens_away_score     team_name_home     team_name_away  team_home_score  \
    0                2             Italy            England                 1   
    1            False           England            Denmark                 2   
    2                2             Italy              Spain                 1   
    3            False           Ukraine            England                 0   
    4            False    Czech Republic            Denmark                 1   
    5            False           Belgium              Italy                 1   
    6                3       Switzerland              Spain                 1   
    7            False            Sweden            Ukraine                 1   
    8            False           England            Germany                 2   
    9                5            France        Switzerland                 3   
    10           False           Croatia              Spain                 3   
    11           False           Belgium           Portugal                 1   
    12           False       Netherlands     Czech Republic                 0   
    13           False             Italy            Austria                 2   
    14           False             Wales            Denmark                 0   
    15           False          Portugal             France                 2   
    16           False           Germany            Hungary                 2   
    17           False            Sweden             Poland                 3   
    18           False          Slovakia              Spain                 0   
    19           False           Croatia           Scotland                 3   
    20           False    Czech Republic            England                 0   
    21           False           Finland            Belgium                 0   
    22           False            Russia            Denmark                 1   
    23           False           Ukraine            Austria                 0   
    24           False   North Macedonia        Netherlands                 0   
    25           False             Italy              Wales                 1   
    26           False       Switzerland             Turkey                 3   
    27           False             Spain             Poland                 1   
    28           False          Portugal            Germany                 2   
    29           False           Hungary             France                 1   
    30           False           England           Scotland                 0   
    31           False           Croatia     Czech Republic                 1   
    32           False            Sweden           Slovakia                 1   
    33           False       Netherlands            Austria                 2   
    34           False           Denmark            Belgium                 1   
    35           False           Ukraine    North Macedonia                 2   
    36           False             Italy        Switzerland                 3   
    37           False            Turkey              Wales                 0   
    38           False           Finland             Russia                 0   
    39           False            France            Germany                 1   
    40           False           Hungary           Portugal                 0   
    41           False             Spain             Sweden                 0   
    42           False            Poland           Slovakia                 1   
    43           False          Scotland     Czech Republic                 0   
    44           False       Netherlands            Ukraine                 3   
    45           False           Austria    North Macedonia                 3   
    46           False           England            Croatia                 1   
    47           False           Belgium             Russia                 3   
    48           False           Denmark            Finland                 0   
    49           False             Wales        Switzerland                 1   
    50           False            Turkey              Italy                 0   
    
        team_away_score possession_home possession_away  total_shots_home  \
    0                 1             66%            34%                 19   
    1                 1             59%            41%                 20   
    2                 1             29%            71%                  7   
    3                 4             48%            52%                  7   
    4                 2             56%            44%                 16   
    5                 2             46%            54%                 10   
    6                 1             27%            73%                  8   
    7                 2             45%            55%                 13   
    8                 0             45%            55%                  5   
    9                 3             55%            45%                 26   
    10                5             32%            68%                 12   
    11                0             42%            58%                  6   
    12                2             52%            48%                  6   
    13                1             52%            48%                 27   
    14                4             47%            53%                 11   
    15                2             47%            53%                 10   
    16                2             76%            24%                 18   
    17                2             33%            67%                 11   
    18                5             34%            66%                  3   
    19                1             67%            33%                 11   
    20                1             43%            57%                  7   
    21                2             39%            61%                  7   
    22                4             35%            65%                  6   
    23                1             51%            49%                  5   
    24                3             41%            59%                 13   
    25                0             70%            30%                 23   
    26                1             51%            49%                 23   
    27                1             77%            23%                 12   
    28                4             42%            58%                  7   
    29                1             33%            67%                  5   
    30                0             61%            39%                  9   
    31                1             48%            52%                 11   
    32                0             41%            59%                 13   
    33                0             46%            54%                 14   
    34                2             47%            53%                 21   
    35                1             53%            47%                 17   
    36                0             49%            51%                 13   
    37                2             64%            36%                 18   
    38                1             41%            59%                 11   
    39                0             38%            62%                  4   
    40                3             30%            70%                  5   
    41                0             86%            14%                 17   
    42                2             58%            42%                 17   
    43                2             58%            42%                 19   
    44                2             62%            38%                 15   
    45                1             63%            37%                 10   
    46                0             49%            51%                  8   
    47                0             67%            33%                  9   
    48                1             70%            30%                 22   
    49                1             35%            65%                  9   
    50                3             36%            64%                  3   
    
        total_shots_away  shots_on_target_home  shots_on_target_away  \
    0                  6                     6                     2   
    1                  6                    10                     3   
    2                 16                     4                     5   
    3                 10                     2                     6   
    4                 11                     5                     7   
    5                 14                     4                     3   
    6                 28                     2                    10   
    7                 15                     3                     4   
    8                  9                     4                     3   
    9                 12                     8                     5   
    10                23                     7                    10   
    11                23                     1                     4   
    12                12                     0                     5   
    13                16                     6                     3   
    14                16                     1                     8   
    15                11                     5                     5   
    16                 9                     7                     4   
    17                18                     4                     6   
    18                19                     0                     9   
    19                11                     6                     3   
    20                 5                     1                     3   
    21                17                     1                     7   
    22                16                     2                    10   
    23                18                     1                     4   
    24                17                     1                     7   
    25                 3                     6                     1   
    26                19                    10                     6   
    27                 5                     5                     2   
    28                12                     2                     7   
    29                15                     3                     4   
    30                11                     1                     2   
    31                11                     2                     1   
    32                10                     4                     0   
    33                 9                     4                     1   
    34                 6                     5                     5   
    35                13                     8                     5   
    36                 6                     3                     1   
    37                16                     6                     7   
    38                14                     1                     3   
    39                10                     1                     1   
    40                11                     3                     7   
    41                 4                     5                     1   
    42                11                     3                     2   
    43                10                     4                     7   
    44                 7                     7                     5   
    45                 7                     6                     2   
    46                 8                     2                     2   
    47                 5                     4                     1   
    48                 1                     6                     1   
    49                18                     2                     4   
    50                24                     0                     8   
    
       duels_won_home duels_won_away  \
    0             53%           47%    
    1             50%           50%    
    2             49%           51%    
    3             42%           59%    
    4             48%           52%    
    5             58%           42%    
    6             58%           42%    
    7             48%           52%    
    8             55%           45%    
    9             55%           45%    
    10            42%           58%    
    11            48%           52%    
    12            53%           48%    
    13            50%           50%    
    14            39%           61%    
    15            60%           41%    
    16            56%           44%    
    17            47%           53%    
    18            44%           56%    
    19            53%           47%    
    20            47%           53%    
    21            40%           61%    
    22            59%           41%    
    23            43%           57%    
    24            39%           61%    
    25            56%           44%    
    26            53%           47%    
    27            42%           58%    
    28            55%           45%    
    29            40%           60%    
    30            54%           46%    
    31            51%           49%    
    32            44%           56%    
    33            52%           48%    
    34            56%           44%    
    35            46%           54%    
    36            43%           57%    
    37            40%           60%    
    38            53%           47%    
    39            60%           40%    
    40            48%           52%    
    41            63%           38%    
    42            51%           49%    
    43            54%           46%    
    44            45%           55%    
    45            50%           50%    
    46            46%           54%    
    47            52%           48%    
    48            53%           47%    
    49            46%           55%    
    50            51%           49%    
    
                                              events_list  \
    0   [{'event_team': 'away', 'event_time': " 2' ", ...   
    1   [{'event_team': 'away', 'event_time': " 30' ",...   
    2   [{'event_team': 'away', 'event_time': " 51' ",...   
    3   [{'event_team': 'away', 'event_time': " 4' ", ...   
    4   [{'event_team': 'away', 'event_time': " 5' ", ...   
    5   [{'event_team': 'away', 'event_time': " 13' ",...   
    6   [{'event_team': 'away', 'event_time': " 8' ", ...   
    7   [{'event_team': 'away', 'event_time': " 27' ",...   
    8   [{'event_team': 'home', 'event_time': " 8' ", ...   
    9   [{'event_team': 'away', 'event_time': " 15' ",...   
    10  [{'event_team': 'home', 'event_time': " 20' ",...   
    11  [{'event_team': 'home', 'event_time': " 42' ",...   
    12  [{'event_team': 'home', 'event_time': " 46' ",...   
    13  [{'event_team': 'away', 'event_time': " 2' ", ...   
    14  [{'event_team': 'home', 'event_time': " 26' ",...   
    15  [{'event_team': 'away', 'event_time': " 27' ",...   
    16  [{'event_team': 'away', 'event_time': " 11' ",...   
    17  [{'event_team': 'home', 'event_time': " 2' ", ...   
    18  [{'event_team': 'home', 'event_time': " 11' ",...   
    19  [{'event_team': 'home', 'event_time': " 17' ",...   
    20  [{'event_team': 'away', 'event_time': " 12' ",...   
    21  [{'event_team': 'home', 'event_time': " 59' ",...   
    22  [{'event_team': 'home', 'event_time': " 28' ",...   
    23  [{'event_team': 'away', 'event_time': " 21' ",...   
    24  [{'event_team': 'home', 'event_time': " 18' ",...   
    25  [{'event_team': 'home', 'event_time': " 39' ",...   
    26  [{'event_team': 'home', 'event_time': " 6' ", ...   
    27  [{'event_team': 'home', 'event_time': " 25' ",...   
    28  [{'event_team': 'home', 'event_time': " 15' ",...   
    29  [{'event_team': 'away', 'event_time': " 10' ",...   
    30  [{'event_team': 'away', 'event_time': " 15' ",...   
    31  [{'event_team': 'home', 'event_time': " 35' ",...   
    32  [{'event_team': 'home', 'event_time': " 23' ",...   
    33  [{'event_team': 'away', 'event_time': " 10' ",...   
    34  [{'event_team': 'home', 'event_time': " 2' ", ...   
    35  [{'event_team': 'home', 'event_time': " 29' ",...   
    36  [{'event_team': 'home', 'event_time': " 19' ",...   
    37  [{'event_team': 'away', 'event_time': " 42' ",...   
    38  [{'event_team': 'home', 'event_time': " 4' ", ...   
    39  [{'event_team': 'away', 'event_time': " 7' ", ...   
    40  [{'event_team': 'away', 'event_time': " 38' ",...   
    41  [{'event_team': 'away', 'event_time': " 55' ",...   
    42  [{'event_team': 'away', 'event_time': " 18' ",...   
    43  [{'event_team': 'away', 'event_time': " 42' ",...   
    44  [{'event_team': 'away', 'event_time': " 13' ",...   
    45  [{'event_team': 'home', 'event_time': " 18' ",...   
    46  [{'event_team': 'away', 'event_time': " 42' ",...   
    47  [{'event_team': 'home', 'event_time': " 10' ",...   
    48  [{'event_team': 'away', 'event_time': " 4' ", ...   
    49  [{'event_team': 'away', 'event_time': " 30' ",...   
    50  [{'event_team': 'home', 'event_time': " 45' ",...   
    
                                              lineup_home  \
    0   [{'Player_Name': 'Insigne', 'Player_Number': '...   
    1   [{'Player_Name': 'Kane', 'Player_Number': '9'}...   
    2   [{'Player_Name': 'Insigne', 'Player_Number': '...   
    3   [{'Player_Name': 'Yaremchuk', 'Player_Number':...   
    4   [{'Player_Name': 'Schick', 'Player_Number': '1...   
    5   [{'Player_Name': 'Lukaku', 'Player_Number': '9...   
    6   [{'Player_Name': 'Seferovic', 'Player_Number':...   
    7   [{'Player_Name': 'Isak', 'Player_Number': '11'...   
    8   [{'Player_Name': 'Sterling', 'Player_Number': ...   
    9   [{'Player_Name': 'Mbappe', 'Player_Number': '1...   
    10  [{'Player_Name': 'Rebic', 'Player_Number': '17...   
    11  [{'Player_Name': 'Lukaku', 'Player_Number': '9...   
    12  [{'Player_Name': 'Malen', 'Player_Number': '18...   
    13  [{'Player_Name': 'Insigne', 'Player_Number': '...   
    14  [{'Player_Name': 'Moore', 'Player_Number': '13...   
    15  [{'Player_Name': 'Ronaldo', 'Player_Number': '...   
    16  [{'Player_Name': 'Gnabry', 'Player_Number': '1...   
    17  [{'Player_Name': 'Isak', 'Player_Number': '11'...   
    18  [{'Player_Name': 'Duda', 'Player_Number': '8'}...   
    19  [{'Player_Name': 'Perisic', 'Player_Number': '...   
    20  [{'Player_Name': 'Schick', 'Player_Number': '1...   
    21  [{'Player_Name': 'Pohjanpalo', 'Player_Number'...   
    22  [{'Player_Name': 'Dzyuba', 'Player_Number': '2...   
    23  [{'Player_Name': 'Malinovskyi', 'Player_Number...   
    24  [{'Player_Name': 'Pandev', 'Player_Number': '1...   
    25  [{'Player_Name': 'Chiesa', 'Player_Number': '1...   
    26  [{'Player_Name': 'Embolo', 'Player_Number': '7...   
    27  [{'Player_Name': 'Olmo Carvajal', 'Player_Numb...   
    28  [{'Player_Name': 'Ronaldo', 'Player_Number': '...   
    29  [{'Player_Name': 'Szalai', 'Player_Number': '9...   
    30  [{'Player_Name': 'Sterling', 'Player_Number': ...   
    31  [{'Player_Name': 'Rebic', 'Player_Number': '17...   
    32  [{'Player_Name': 'Berg', 'Player_Number': '9'}...   
    33  [{'Player_Name': 'Depay', 'Player_Number': '10...   
    34  [{'Player_Name': 'Poulsen', 'Player_Number': '...   
    35  [{'Player_Name': 'Malinovskyi', 'Player_Number...   
    36  [{'Player_Name': 'Insigne', 'Player_Number': '...   
    37  [{'Player_Name': 'Yilmaz', 'Player_Number': '1...   
    38  [{'Player_Name': 'Pohjanpalo', 'Player_Number'...   
    39  [{'Player_Name': 'Mbappe', 'Player_Number': '1...   
    40  [{'Player_Name': 'Szalai', 'Player_Number': '9...   
    41  [{'Player_Name': 'Olmo Carvajal', 'Player_Numb...   
    42  [{'Player_Name': 'Zielinski', 'Player_Number':...   
    43  [{'Player_Name': 'Christie', 'Player_Number': ...   
    44  [{'Player_Name': 'Depay', 'Player_Number': '10...   
    45  [{'Player_Name': 'Baumgartner', 'Player_Number...   
    46  [{'Player_Name': 'Sterling', 'Player_Number': ...   
    47  [{'Player_Name': 'Carrasco', 'Player_Number': ...   
    48  [{'Player_Name': 'Braithwaite', 'Player_Number...   
    49  [{'Player_Name': 'Moore', 'Player_Number': '13...   
    50  [{'Player_Name': 'Yilmaz', 'Player_Number': '1...   
    
                                              lineup_away  
    0   [{'Player_Name': 'Kane', 'Player_Number': '9'}...  
    1   [{'Player_Name': 'Krogh Damsgaard', 'Player_Nu...  
    2   [{'Player_Name': 'Torres', 'Player_Number': '1...  
    3   [{'Player_Name': 'Kane', 'Player_Number': '9'}...  
    4   [{'Player_Name': 'Dolberg', 'Player_Number': '...  
    5   [{'Player_Name': 'Insigne', 'Player_Number': '...  
    6   [{'Player_Name': 'Sarabia', 'Player_Number': '...  
    7   [{'Player_Name': 'Yaremchuk', 'Player_Number':...  
    8   [{'Player_Name': 'Werner', 'Player_Number': '1...  
    9   [{'Player_Name': 'Seferovic', 'Player_Number':...  
    10  [{'Player_Name': 'Sarabia', 'Player_Number': '...  
    11  [{'Player_Name': 'Jota', 'Player_Number': '21'...  
    12  [{'Player_Name': 'Schick', 'Player_Number': '1...  
    13  [{'Player_Name': 'Arnautovic', 'Player_Number'...  
    14  [{'Player_Name': 'Dolberg', 'Player_Number': '...  
    15  [{'Player_Name': 'Benzema', 'Player_Number': '...  
    16  [{'Player_Name': 'Szalai', 'Player_Number': '9...  
    17  [{'Player_Name': 'Lewandowski', 'Player_Number...  
    18  [{'Player_Name': 'Moreno', 'Player_Number': '9...  
    19  [{'Player_Name': 'Adams', 'Player_Number': '10...  
    20  [{'Player_Name': 'Kane', 'Player_Number': '9'}...  
    21  [{'Player_Name': 'Lukaku', 'Player_Number': '9...  
    22  [{'Player_Name': 'Poulsen', 'Player_Number': '...  
    23  [{'Player_Name': 'Arnautovic', 'Player_Number'...  
    24  [{'Player_Name': 'Malen', 'Player_Number': '18...  
    25  [{'Player_Name': 'James', 'Player_Number': '20...  
    26  [{'Player_Name': 'Yilmaz', 'Player_Number': '1...  
    27  [{'Player_Name': 'Lewandowski', 'Player_Number...  
    28  [{'Player_Name': 'Gnabry', 'Player_Number': '1...  
    29  [{'Player_Name': 'Mbappe', 'Player_Number': '1...  
    30  [{'Player_Name': 'Dykes', 'Player_Number': '9'...  
    31  [{'Player_Name': 'Schick', 'Player_Number': '1...  
    32  [{'Player_Name': 'Duda', 'Player_Number': '8'}...  
    33  [{'Player_Name': 'Gregoritsch', 'Player_Number...  
    34  [{'Player_Name': 'Lukaku', 'Player_Number': '9...  
    35  [{'Player_Name': 'Elmas', 'Player_Number': '21...  
    36  [{'Player_Name': 'Embolo', 'Player_Number': '7...  
    37  [{'Player_Name': 'Moore', 'Player_Number': '13...  
    38  [{'Player_Name': 'Dzyuba', 'Player_Number': '2...  
    39  [{'Player_Name': 'Gnabry', 'Player_Number': '1...  
    40  [{'Player_Name': 'Ronaldo', 'Player_Number': '...  
    41  [{'Player_Name': 'Isak', 'Player_Number': '11'...  
    42  [{'Player_Name': 'Duda', 'Player_Number': '8'}...  
    43  [{'Player_Name': 'Schick', 'Player_Number': '1...  
    44  [{'Player_Name': 'Zubkov', 'Player_Number': '2...  
    45  [{'Player_Name': 'Trajkovski', 'Player_Number'...  
    46  [{'Player_Name': 'Perisic', 'Player_Number': '...  
    47  [{'Player_Name': 'Dzyuba', 'Player_Number': '2...  
    48  [{'Player_Name': 'Pukki', 'Player_Number': '10...  
    49  [{'Player_Name': 'Embolo', 'Player_Number': '7...  
    50  [{'Player_Name': 'Insigne', 'Player_Number': '...  >




```python
er["team_away_score"]>3
```




    0     False
    1     False
    2     False
    3      True
    4     False
    5     False
    6     False
    7     False
    8     False
    9     False
    10     True
    11    False
    12    False
    13    False
    14     True
    15    False
    16    False
    17    False
    18     True
    19    False
    20    False
    21    False
    22     True
    23    False
    24    False
    25    False
    26    False
    27    False
    28     True
    29    False
    30    False
    31    False
    32    False
    33    False
    34    False
    35    False
    36    False
    37    False
    38    False
    39    False
    40    False
    41    False
    42    False
    43    False
    44    False
    45    False
    46    False
    47    False
    48    False
    49    False
    50    False
    Name: team_away_score, dtype: bool




```python
er.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>stage</th>
      <th>date</th>
      <th>pens</th>
      <th>pens_home_score</th>
      <th>pens_away_score</th>
      <th>team_name_home</th>
      <th>team_name_away</th>
      <th>team_home_score</th>
      <th>team_away_score</th>
      <th>possession_home</th>
      <th>possession_away</th>
      <th>total_shots_home</th>
      <th>total_shots_away</th>
      <th>shots_on_target_home</th>
      <th>shots_on_target_away</th>
      <th>duels_won_home</th>
      <th>duels_won_away</th>
      <th>events_list</th>
      <th>lineup_home</th>
      <th>lineup_away</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Final</td>
      <td>11.07.2021</td>
      <td>True</td>
      <td>3</td>
      <td>2</td>
      <td>Italy</td>
      <td>England</td>
      <td>1</td>
      <td>1</td>
      <td>66%</td>
      <td>34%</td>
      <td>19</td>
      <td>6</td>
      <td>6</td>
      <td>2</td>
      <td>53%</td>
      <td>47%</td>
      <td>[{'event_team': 'away', 'event_time': " 2' ", ...</td>
      <td>[{'Player_Name': 'Insigne', 'Player_Number': '...</td>
      <td>[{'Player_Name': 'Kane', 'Player_Number': '9'}...</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Semi-finals</td>
      <td>07.07.2021</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>England</td>
      <td>Denmark</td>
      <td>2</td>
      <td>1</td>
      <td>59%</td>
      <td>41%</td>
      <td>20</td>
      <td>6</td>
      <td>10</td>
      <td>3</td>
      <td>50%</td>
      <td>50%</td>
      <td>[{'event_team': 'away', 'event_time': " 30' ",...</td>
      <td>[{'Player_Name': 'Kane', 'Player_Number': '9'}...</td>
      <td>[{'Player_Name': 'Krogh Damsgaard', 'Player_Nu...</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Semi-finals</td>
      <td>06.07.2021</td>
      <td>True</td>
      <td>4</td>
      <td>2</td>
      <td>Italy</td>
      <td>Spain</td>
      <td>1</td>
      <td>1</td>
      <td>29%</td>
      <td>71%</td>
      <td>7</td>
      <td>16</td>
      <td>4</td>
      <td>5</td>
      <td>49%</td>
      <td>51%</td>
      <td>[{'event_team': 'away', 'event_time': " 51' ",...</td>
      <td>[{'Player_Name': 'Insigne', 'Player_Number': '...</td>
      <td>[{'Player_Name': 'Torres', 'Player_Number': '1...</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Quarter-finals</td>
      <td>03.07.2021</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>Ukraine</td>
      <td>England</td>
      <td>0</td>
      <td>4</td>
      <td>48%</td>
      <td>52%</td>
      <td>7</td>
      <td>10</td>
      <td>2</td>
      <td>6</td>
      <td>42%</td>
      <td>59%</td>
      <td>[{'event_team': 'away', 'event_time': " 4' ", ...</td>
      <td>[{'Player_Name': 'Yaremchuk', 'Player_Number':...</td>
      <td>[{'Player_Name': 'Kane', 'Player_Number': '9'}...</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Quarter-finals</td>
      <td>03.07.2021</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>Czech Republic</td>
      <td>Denmark</td>
      <td>1</td>
      <td>2</td>
      <td>56%</td>
      <td>44%</td>
      <td>16</td>
      <td>11</td>
      <td>5</td>
      <td>7</td>
      <td>48%</td>
      <td>52%</td>
      <td>[{'event_team': 'away', 'event_time': " 5' ", ...</td>
      <td>[{'Player_Name': 'Schick', 'Player_Number': '1...</td>
      <td>[{'Player_Name': 'Dolberg', 'Player_Number': '...</td>
    </tr>
  </tbody>
</table>
</div>




```python
er.count()
```




    stage                   51
    date                    51
    pens                    51
    pens_home_score         51
    pens_away_score         51
    team_name_home          51
    team_name_away          51
    team_home_score         51
    team_away_score         51
    possession_home         51
    possession_away         51
    total_shots_home        51
    total_shots_away        51
    shots_on_target_home    51
    shots_on_target_away    51
    duels_won_home          51
    duels_won_away          51
    events_list             51
    lineup_home             51
    lineup_away             51
    dtype: int64




```python
er.groupby("possession_home").shots_on_target_home.mean() 
```




    possession_home
    27%     2.000000
    29%     4.000000
    30%     3.000000
    32%     7.000000
    33%     3.500000
    34%     0.000000
    35%     2.000000
    36%     0.000000
    38%     1.000000
    39%     1.000000
    41%     2.000000
    42%     1.500000
    43%     1.000000
    45%     3.500000
    46%     4.000000
    47%     3.666667
    48%     2.000000
    49%     2.500000
    51%     5.500000
    52%     3.000000
    53%     8.000000
    55%     8.000000
    56%     5.000000
    58%     3.500000
    59%    10.000000
    61%     1.000000
    62%     7.000000
    63%     6.000000
    64%     6.000000
    66%     6.000000
    67%     5.000000
    70%     6.000000
    76%     7.000000
    77%     5.000000
    86%     5.000000
    Name: shots_on_target_home, dtype: float64




```python
er[["stage","team_home_score", "team_away_score", "shots_on_target_home","shots_on_target_away"]]
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>stage</th>
      <th>team_home_score</th>
      <th>team_away_score</th>
      <th>shots_on_target_home</th>
      <th>shots_on_target_away</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Final</td>
      <td>1</td>
      <td>1</td>
      <td>6</td>
      <td>2</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Semi-finals</td>
      <td>2</td>
      <td>1</td>
      <td>10</td>
      <td>3</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Semi-finals</td>
      <td>1</td>
      <td>1</td>
      <td>4</td>
      <td>5</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Quarter-finals</td>
      <td>0</td>
      <td>4</td>
      <td>2</td>
      <td>6</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Quarter-finals</td>
      <td>1</td>
      <td>2</td>
      <td>5</td>
      <td>7</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Quarter-finals</td>
      <td>1</td>
      <td>2</td>
      <td>4</td>
      <td>3</td>
    </tr>
    <tr>
      <th>6</th>
      <td>Quarter-finals</td>
      <td>1</td>
      <td>1</td>
      <td>2</td>
      <td>10</td>
    </tr>
    <tr>
      <th>7</th>
      <td>Round of 16</td>
      <td>1</td>
      <td>2</td>
      <td>3</td>
      <td>4</td>
    </tr>
    <tr>
      <th>8</th>
      <td>Round of 16</td>
      <td>2</td>
      <td>0</td>
      <td>4</td>
      <td>3</td>
    </tr>
    <tr>
      <th>9</th>
      <td>Round of 16</td>
      <td>3</td>
      <td>3</td>
      <td>8</td>
      <td>5</td>
    </tr>
    <tr>
      <th>10</th>
      <td>Round of 16</td>
      <td>3</td>
      <td>5</td>
      <td>7</td>
      <td>10</td>
    </tr>
    <tr>
      <th>11</th>
      <td>Round of 16</td>
      <td>1</td>
      <td>0</td>
      <td>1</td>
      <td>4</td>
    </tr>
    <tr>
      <th>12</th>
      <td>Round of 16</td>
      <td>0</td>
      <td>2</td>
      <td>0</td>
      <td>5</td>
    </tr>
    <tr>
      <th>13</th>
      <td>Round of 16</td>
      <td>2</td>
      <td>1</td>
      <td>6</td>
      <td>3</td>
    </tr>
    <tr>
      <th>14</th>
      <td>Round of 16</td>
      <td>0</td>
      <td>4</td>
      <td>1</td>
      <td>8</td>
    </tr>
    <tr>
      <th>15</th>
      <td>Group stage: Matchday 3</td>
      <td>2</td>
      <td>2</td>
      <td>5</td>
      <td>5</td>
    </tr>
    <tr>
      <th>16</th>
      <td>Group stage: Matchday 3</td>
      <td>2</td>
      <td>2</td>
      <td>7</td>
      <td>4</td>
    </tr>
    <tr>
      <th>17</th>
      <td>Group stage: Matchday 3</td>
      <td>3</td>
      <td>2</td>
      <td>4</td>
      <td>6</td>
    </tr>
    <tr>
      <th>18</th>
      <td>Group stage: Matchday 3</td>
      <td>0</td>
      <td>5</td>
      <td>0</td>
      <td>9</td>
    </tr>
    <tr>
      <th>19</th>
      <td>Group stage: Matchday 3</td>
      <td>3</td>
      <td>1</td>
      <td>6</td>
      <td>3</td>
    </tr>
    <tr>
      <th>20</th>
      <td>Group stage: Matchday 3</td>
      <td>0</td>
      <td>1</td>
      <td>1</td>
      <td>3</td>
    </tr>
    <tr>
      <th>21</th>
      <td>Group stage: Matchday 3</td>
      <td>0</td>
      <td>2</td>
      <td>1</td>
      <td>7</td>
    </tr>
    <tr>
      <th>22</th>
      <td>Group stage: Matchday 3</td>
      <td>1</td>
      <td>4</td>
      <td>2</td>
      <td>10</td>
    </tr>
    <tr>
      <th>23</th>
      <td>Group stage: Matchday 3</td>
      <td>0</td>
      <td>1</td>
      <td>1</td>
      <td>4</td>
    </tr>
    <tr>
      <th>24</th>
      <td>Group stage: Matchday 3</td>
      <td>0</td>
      <td>3</td>
      <td>1</td>
      <td>7</td>
    </tr>
    <tr>
      <th>25</th>
      <td>Group stage: Matchday 3</td>
      <td>1</td>
      <td>0</td>
      <td>6</td>
      <td>1</td>
    </tr>
    <tr>
      <th>26</th>
      <td>Group stage: Matchday 3</td>
      <td>3</td>
      <td>1</td>
      <td>10</td>
      <td>6</td>
    </tr>
    <tr>
      <th>27</th>
      <td>Group stage: Matchday 2</td>
      <td>1</td>
      <td>1</td>
      <td>5</td>
      <td>2</td>
    </tr>
    <tr>
      <th>28</th>
      <td>Group stage: Matchday 2</td>
      <td>2</td>
      <td>4</td>
      <td>2</td>
      <td>7</td>
    </tr>
    <tr>
      <th>29</th>
      <td>Group stage: Matchday 2</td>
      <td>1</td>
      <td>1</td>
      <td>3</td>
      <td>4</td>
    </tr>
    <tr>
      <th>30</th>
      <td>Group stage: Matchday 2</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>2</td>
    </tr>
    <tr>
      <th>31</th>
      <td>Group stage: Matchday 2</td>
      <td>1</td>
      <td>1</td>
      <td>2</td>
      <td>1</td>
    </tr>
    <tr>
      <th>32</th>
      <td>Group stage: Matchday 2</td>
      <td>1</td>
      <td>0</td>
      <td>4</td>
      <td>0</td>
    </tr>
    <tr>
      <th>33</th>
      <td>Group stage: Matchday 2</td>
      <td>2</td>
      <td>0</td>
      <td>4</td>
      <td>1</td>
    </tr>
    <tr>
      <th>34</th>
      <td>Group stage: Matchday 2</td>
      <td>1</td>
      <td>2</td>
      <td>5</td>
      <td>5</td>
    </tr>
    <tr>
      <th>35</th>
      <td>Group stage: Matchday 2</td>
      <td>2</td>
      <td>1</td>
      <td>8</td>
      <td>5</td>
    </tr>
    <tr>
      <th>36</th>
      <td>Group stage: Matchday 2</td>
      <td>3</td>
      <td>0</td>
      <td>3</td>
      <td>1</td>
    </tr>
    <tr>
      <th>37</th>
      <td>Group stage: Matchday 2</td>
      <td>0</td>
      <td>2</td>
      <td>6</td>
      <td>7</td>
    </tr>
    <tr>
      <th>38</th>
      <td>Group stage: Matchday 2</td>
      <td>0</td>
      <td>1</td>
      <td>1</td>
      <td>3</td>
    </tr>
    <tr>
      <th>39</th>
      <td>Group stage: Matchday 1</td>
      <td>1</td>
      <td>0</td>
      <td>1</td>
      <td>1</td>
    </tr>
    <tr>
      <th>40</th>
      <td>Group stage: Matchday 1</td>
      <td>0</td>
      <td>3</td>
      <td>3</td>
      <td>7</td>
    </tr>
    <tr>
      <th>41</th>
      <td>Group stage: Matchday 1</td>
      <td>0</td>
      <td>0</td>
      <td>5</td>
      <td>1</td>
    </tr>
    <tr>
      <th>42</th>
      <td>Group stage: Matchday 1</td>
      <td>1</td>
      <td>2</td>
      <td>3</td>
      <td>2</td>
    </tr>
    <tr>
      <th>43</th>
      <td>Group stage: Matchday 1</td>
      <td>0</td>
      <td>2</td>
      <td>4</td>
      <td>7</td>
    </tr>
    <tr>
      <th>44</th>
      <td>Group stage: Matchday 1</td>
      <td>3</td>
      <td>2</td>
      <td>7</td>
      <td>5</td>
    </tr>
    <tr>
      <th>45</th>
      <td>Group stage: Matchday 1</td>
      <td>3</td>
      <td>1</td>
      <td>6</td>
      <td>2</td>
    </tr>
    <tr>
      <th>46</th>
      <td>Group stage: Matchday 1</td>
      <td>1</td>
      <td>0</td>
      <td>2</td>
      <td>2</td>
    </tr>
    <tr>
      <th>47</th>
      <td>Group stage: Matchday 1</td>
      <td>3</td>
      <td>0</td>
      <td>4</td>
      <td>1</td>
    </tr>
    <tr>
      <th>48</th>
      <td>Group stage: Matchday 1</td>
      <td>0</td>
      <td>1</td>
      <td>6</td>
      <td>1</td>
    </tr>
    <tr>
      <th>49</th>
      <td>Group stage: Matchday 1</td>
      <td>1</td>
      <td>1</td>
      <td>2</td>
      <td>4</td>
    </tr>
    <tr>
      <th>50</th>
      <td>Group stage: Matchday 1</td>
      <td>0</td>
      <td>3</td>
      <td>0</td>
      <td>8</td>
    </tr>
  </tbody>
</table>
</div>




```python
print(er.groupby('possession_home').possession_away.min())
```

    possession_home
    27%     73% 
    29%     71% 
    30%     70% 
    32%     68% 
    33%     67% 
    34%     66% 
    35%     65% 
    36%     64% 
    38%     62% 
    39%     61% 
    41%     59% 
    42%     58% 
    43%     57% 
    45%     55% 
    46%     54% 
    47%     53% 
    48%     52% 
    49%     51% 
    51%     49% 
    52%     48% 
    53%     47% 
    55%     45% 
    56%     44% 
    58%     42% 
    59%     41% 
    61%     39% 
    62%     38% 
    63%     37% 
    64%     36% 
    66%     34% 
    67%     33% 
    70%     30% 
    76%     24% 
    77%     23% 
    86%     14% 
    Name: possession_away, dtype: object
    


```python
from matplotlib import pyplot as plt 
from matplotlib import style
import numpy as np 

style.use("ggplot")
x,y = np.loadtxt("D:/Courses/Projects/possession_home.txt", unpack=True, delimiter=",")

plt.plot(x,y)
plt.title("EURO 2020")
plt.xlabel("team_home_score")
plt.ylabel("team_away_score")

plt.show()
```


    
![png](output_16_0.png)
    



```python

```
