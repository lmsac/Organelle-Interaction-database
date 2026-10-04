# Organelle Interaction Database

A dataset of protein-pair interaction scores with organelle annotations, for exploring protein interactions across cellular compartments.

## Dataset

[organelles_protein_interactions.csv](organelles_protein_interactions.csv) contains **66,500 records** with five columns:

| Column | Description |
| --- | --- |
| `protein_1` | Identifier of the first protein. |
| `protein_2` | Identifier of the second protein. |
| `score` | Interaction score supplied in the dataset. |
| `query_organelle` | Organelle annotation associated with `protein_1`. |
| `text_organelle` | Organelle annotation associated with `protein_2`. |

Multiple organelle labels are separated by semicolons (`;`). The value `unknown` indicates an unspecified organelle. All scores in the current file are greater than 0.95.

## Quick Start

Download the CSV using the link above, or clone the repository:

```bash
git clone https://github.com/lmsac/Organelle-Interaction-database.git
cd Organelle-Interaction-database
python3 -m pip install pandas
```

Read the dataset in Python:

```python
import pandas as pd

df = pd.read_csv("organelles_protein_interactions.csv")
print(df.head())

# Select records with a score of at least 0.99.
high_score = df[df["score"] >= 0.99]
```

## License

This repository is released under the [MIT License](LICENSE.md).
