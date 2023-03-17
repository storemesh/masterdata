# masterdata

This python libary help data team to get standard masterdata and also validate input with master data. Our vision is to help integration between digital commerce applications.

## Setup

```bash
pip install git+https://github.com/storemesh/masterdata

```

## Get master data
```python
import masterdata as md
df=md.master.area.read()
print(df)
```
| code  | subdivision | th_subdivision | 
| ------------- | ------------- | ------------- |
| TH-13  | Pathum Thani | ปทุมธานี  |
| TH-52	| Lampang | ลำปาง |
| TH-S	| Phatthaya | พัทยา |
 , 



## Validate data
```python
import masterdata as md
import pandas as pd
data = {
  "date": ['2022-12-31', '2023-01-31', '02/30/65'],
  "province": ['ปทุมธานี', 'ลำบาง', 'พัทยp'],
  "pm.5": [120, 200, 60],
}

#load data into a DataFrame object:
df1 = pd.DataFrame(data)
result=md.validate(query=df1['province'], key=md.master.area)

df2=md.readmaster(table='area', fields=['code','province'])
result=md.validate(query=df1['province'], key=df2['province'])

#1.input
#2.completeness check
#3.format check
#4.consistency check
#5.result 

len(result.input)
```


