mport pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import os

df = pd.read_csv('novakid_test.csv', delimiter=',')

df.tail()

len(df['date_start'].unique())

df.agg({'date_start':['min', 'max']})

len(df['user_id'].unique())

unique_count = df.loc[:, ['user_id', 'date_start'] ].groupby(['date_start']).nunique()

unique_count

unique_count.to_excel(r'export - test.xlsx', index = True)

 df.loc[:, ['user_id']].drop_duplicates()

df.loc[:, ['session_id']].drop_duplicates()

df.duplicated('session_id')

df.loc[df['session_id'] == 1575442547, ['user_id', 'session_id', 'date_start']]

