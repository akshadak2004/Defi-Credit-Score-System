# Defi-Credit-Score-System
Overview :

This project uses historical Aave V2 transaction data to group wallets by behavior and assign each wallet a credit score between 0 and 1000, using unsupervised learning (clustering)
What’s Inside :
user-wallet-transactions.json – raw Aave V2 transaction data
clean_json.py – fixes malformed JSON
score_System.py – aggregates transaction history per wallet and clusters wallets 
wallet_scores.json - assigns credit scores

 How It Works
1. Data Preparation
Clean the JSON file.

Extract and aggregate each wallet's transaction behavior:

Number of deposits, borrows, repayments, etc.

Total amount deposited, borrowed (in USD)

Total transaction count

2. Clustering
Use KMeans to group similar wallets.

Wallets with similar transaction patterns end up in the same cluster.

3. Credit Score Assignment
Each cluster is analyzed (good, risky, inactive, etc.).

A fixed score is assigned to each cluster.

Example:

Cluster	Behavior	Score :

0	: Inactive or low usage	200
1	: Large responsible users	850
2 :	Risky, high borrow, low repay	400
3 :	Very active, reliable users	950

Output
Each wallet is tagged with:

A cluster (e.g., 0, 1, 2, 3)

A credit_score (0–1000)
