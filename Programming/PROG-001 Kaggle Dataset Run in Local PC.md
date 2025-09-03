Step 1: Install Kaggle in Local PC
```cmd
pip install kaggle
```

Step 2:  Configurate Kaggle API token
![[Pasted image 20250825103005.png]]

Step 3:  Using Kaggle CLI download Data
```cmd
C:\Users\<你的用户名>\.kaggle\kaggle.json
```

Step 4: Unzip  .zip file
```cmd
kaggle datasets download -d lakshmi25npathi/imdb-dataset-of-50k-movie-reviews
```

Step 5: Using Python Read .csv file
```python
import pandas as pd

df = pd.read_csv("IMDB Dataset.csv")
print(df.head())
```