# Data

## Source

UCI Machine Learning Repository: **Default of Credit Card Clients**

Dataset page:
https://archive.ics.uci.edu/dataset/350/default%2Bof%2Bcredit%2Bcard%2Bclients_dataset

Citation:

Yeh, I.-C. (2009). *Default of Credit Card Clients* [Dataset]. UCI Machine Learning Repository. DOI: 10.24432/C55S3H.

## Local copy

This repository includes a local CSV copy at:

```text
dataset/default_of_credit_card_clients_dataset.csv
```

It contains 30,000 customers and 25 columns (ID, 23 original input variables, and the target `default.payment.next.month`). The file is included so the notebook can be reviewed and rerun without an additional download.

## Re-downloading

If the copy needs to be replaced, download the dataset from the UCI page above and keep the same filename and location so that `notebooks/Credit_Default_Project2.ipynb` can load it.
