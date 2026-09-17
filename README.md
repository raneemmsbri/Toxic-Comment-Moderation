# Toxic-Comment-Moderation 

I fine-tuned distilbert-base-uncased to flag toxic comments across 7 categories at once — toxicity, severe toxicity, obscenity, threats, insults, identity attacks, and sexually explicit content — using Google's Civil Comments dataset.

The pipeline
Prep the data — sample from Civil Comments, clean it up, turn the continuous toxicity scores into binary labels
Fine-tune — train DistilBERT as a multi-label classifier
Evaluate — check precision/recall/F1 per category on a held-out test set
Export to ONNX — convert the model for faster, more portable inference
Quantize — shrink it down to INT8 so it runs lighter and faster
