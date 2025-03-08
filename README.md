# Ex.No: 01A PLOT A TIME SERIES DATA
###  Date: 08.03.2025
### Reg No:212224220001

# AIM:
To Develop a python program to Plot a time series data (population/ market price of a commodity
/temperature.
# ALGORITHM:
1. Import the required packages like pandas and matplot
2. Read the dataset using the pandas
3. Calculate the mean for the respective column.
4. Plot the data according to need and can be altered monthly, or yearly.
5. Display the graph.
# PROGRAM:
```PYTHON
import pandas as pd
import matplotlib.pyplot as plt
import numpy as np
import seaborn as sns
import warnings
warnings.filterwarnings('ignore')
file_path = 'ODI Cricket Data new.csv' 
df = pd.read_csv(file_path)
df
df.count
df.describe()
df.duplicated()
sns.set_style("darkgrid")
plt.rcParams["figure.figsize"] = (10, 5)
plt.figure()
plt.hist(df['total_runs'], bins=30, color='darkblue', edgecolor='black')
plt.xlabel("Total Runs")
plt.ylabel("Number of Players")
plt.title("Distribution of Total Runs")
plt.show()
plt.figure()
sns.scatterplot(x='strike_rate', y='total_runs', hue='role', data=df, palette="coolwarm")
plt.xlabel("Strike Rate")
plt.ylabel("Total Runs")
plt.title("Strike Rate vs. Total Runs")
plt.show()
top_scorers = df.nlargest(10, 'total_runs')
plt.figure()
sns.barplot(x='total_runs', y='player_name', data=top_scorers, palette="Greens_r")
plt.xlabel("Total Runs")
plt.ylabel("Player Name")
plt.title("Top 10 Run Scorers")
plt.show()
plt.figure()
sns.boxplot(x='matches_played_as_batter', y='total_runs', data=df)
plt.xlabel("Matches Played as Batter")
plt.ylabel("Total Runs")
plt.title("Matches as Batter vs. Total Runs")
plt.show()
plt.figure()
plt.hist(df['total_wickets_taken'], bins=20, color='darkred', edgecolor='black')
plt.xlabel("Total Wickets Taken")
plt.ylabel("Number of Players")
plt.title("Distribution of Total Wickets Taken")
plt.show()
plt.figure()
sns.scatterplot(x='total_runs_conceded', y='total_wickets_taken', hue='role', data=df, palette="coolwarm")
plt.xlabel("Total Runs Conceded")
plt.ylabel("Total Wickets Taken")
plt.title("Wickets Taken vs. Runs Conceded")
plt.show()
top_wicket_takers = df.nlargest(10, 'total_wickets_taken')
plt.figure()
sns.barplot(x='total_wickets_taken', y='player_name', data=top_wicket_takers, palette="Blues_r")
plt.xlabel("Total Wickets Taken")
plt.ylabel("Player Name")
plt.title("Top 10 Wicket-Takers")
plt.show()
plt.figure()
df.groupby('team')[['matches_won', 'matches_lost']].sum().plot(kind='bar', stacked=True, color=['darkblue', 'darkred'])
plt.xlabel("Team")
plt.ylabel("Matches Won/Lost")
plt.title("Team Matches Won vs. Lost")
plt.legend(["Won", "Lost"])
plt.show()
top_award_players = df.nlargest(10, 'player_of_match_awards')
sns.barplot(x='player_of_match_awards', y='player_name', data=top_award_players, palette="flare")
```










# OUTPUT:
![image](https://github.com/user-attachments/assets/a064416b-39a6-47af-a94f-dcc6f2b092c0)
![image](https://github.com/user-attachments/assets/4e812bdf-83d8-4ccc-9ac5-4009095dfde3)
![image](https://github.com/user-attachments/assets/d223ec23-c5eb-49d4-997f-8b3cd38f2332)








# RESULT:
Thus we have created the python code for plotting the time series of given data.
