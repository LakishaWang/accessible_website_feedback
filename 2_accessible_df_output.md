# 2. Printing Table for Screen Reader Users

The following examples illustrate an alternative format already tested with Laras. Instead of a visually aligned table that is difficult to follow by ear, the code prints the shape and column names first, then outputs each row as a dictionary. This makes it clear how many rows and columns the dataset has, and each row is read as a self-contained set of labelled values.

## Example 1: CSV over HTTP using pandas

```python
import pandas as pd

url = "https://raw.githubusercontent.com/earth-DS-ML/summer_2026/refs/heads/main/lectures_DS/data/monthly_in_situ_co2_mlo.csv"
columns = ["year", "month", "date_excel", "date", "co2", "co2_seasonally_adjusted",
           "fit", "fit_seasonally_adjusted", "co2_filled", "co2_filled_seasonally_adjusted",
           "station"]
df = pd.read_csv(url, skiprows=64, names=columns, na_values=-99.99)

df1 = df[["year", "month", "date", "co2"]]
print(f"Shape: {df1.shape}")
print(f"Columns: {df1.columns.tolist()}")

for _, row in df1.head().iterrows():
    print(row.to_dict())
```

Output:

```
Shape: (828, 4)
Columns: ['year', 'month', 'date', 'co2']
{'year': 1958.0, 'month': 1.0, 'date': 1958.0411, 'co2': nan}
{'year': 1958.0, 'month': 2.0, 'date': 1958.126, 'co2': nan}
{'year': 1958.0, 'month': 3.0, 'date': 1958.2027, 'co2': 315.71}
{'year': 1958.0, 'month': 4.0, 'date': 1958.2877, 'co2': 317.45}
{'year': 1958.0, 'month': 5.0, 'date': 1958.3699, 'co2': 317.51}
```

## Example 2: DOI-based retrieval using pooch

```python
import pooch
import pandas as pd

doi = "doi:10.5281/zenodo.5739406"
fname = "wind_po_hrly.csv"
file_path = pooch.retrieve(
    url=f"{doi}/{fname}",
    known_hash="md5:cf059b73d6831282c5580776ac07309a",
)

df = pd.read_csv(file_path)
print(f"Shape: {df.shape}")
print(f"Columns: {df.columns.tolist()}")

for _, row in df.head().iterrows():
    print(row.to_dict())
```

Output:

```
Shape: (8760, 9)
Columns: ['date.time', 'ny_1_onshore', 'ny_2_onshore', 'newe_onshore', 'mw_onshore', 'newe_offshore', 'ny_offshore', 'rfce_offshore', 'srvc_offshore']
{'date.time': '1/1/2011 0:00', 'ny_1_onshore': 0.725240495, 'ny_2_onshore': 0.450003616, 'newe_onshore': 0.693996266, 'mw_onshore': 0.646463288, 'newe_offshore': 0.759451462, 'ny_offshore': 0.528019073, 'rfce_offshore': 0.353946234, 'srvc_offshore': 0.189322848}
{'date.time': '1/1/2011 1:00', 'ny_1_onshore': 0.702001288, 'ny_2_onshore': 0.446461542, 'newe_onshore': 0.677913327, 'mw_onshore': 0.68888967, 'newe_offshore': 0.767230863, 'ny_offshore': 0.530821811, 'rfce_offshore': 0.357297022, 'srvc_offshore': 0.21296533}
{'date.time': '1/1/2011 2:00', 'ny_1_onshore': 0.670163748, 'ny_2_onshore': 0.432219015, 'newe_onshore': 0.645566524, 'mw_onshore': 0.717634315, 'newe_offshore': 0.764236637, 'ny_offshore': 0.538844684, 'rfce_offshore': 0.374449945, 'srvc_offshore': 0.232722138}
{'date.time': '1/1/2011 3:00', 'ny_1_onshore': 0.627149343, 'ny_2_onshore': 0.436257198, 'newe_onshore': 0.608017041, 'mw_onshore': 0.745687434, 'newe_offshore': 0.760257805, 'ny_offshore': 0.541973539, 'rfce_offshore': 0.38766983, 'srvc_offshore': 0.246671993}
{'date.time': '1/1/2011 4:00', 'ny_1_onshore': 0.580881615, 'ny_2_onshore': 0.456108094, 'newe_onshore': 0.584727635, 'mw_onshore': 0.767698482, 'newe_offshore': 0.759814117, 'ny_offshore': 0.552362944, 'rfce_offshore': 0.393834754, 'srvc_offshore': 0.261140409}
```
