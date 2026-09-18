# Toxic-Comment-Moderation 

I fine-tuned distilbert-base-uncased to flag toxic comments across 7 categories at once — toxicity, severe toxicity, obscenity, threats, insults, identity attacks, and sexually explicit content — using Google's Civil Comments dataset.

The pipeline

Prep the data — sample from Civil Comments, clean it up, turn the continuous toxicity scores into binary labels
Fine-tune — train DistilBERT as a multi-label classifier
Evaluate — check precision/recall/F1 per category on a held-out test set
Export to ONNX — convert the model for faster, more portable inference
Quantize — shrink it down to INT8 so it runs lighter and faster




Results

Trained on 100K sampled comments, evaluated on a 2,396-comment held-out test set.

Metric	Score
F1 Micro	0.639
F1 Macro	0.399


Label	Precision	Recall	F1	Support
toxicity	0.71	0.64	0.67	1235
insult	0.70	0.66	0.68	908
obscene	0.58	0.64	0.61	75
identity_attack	0.58	0.28	0.38	110
sexual_explicit	0.46	0.31	0.37	35
threat	0.44	0.24	0.31	33
severe_toxicity	0.00	0.00	0.00	0




