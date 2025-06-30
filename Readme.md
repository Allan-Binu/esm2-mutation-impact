Protein Mutation Impact via Embedding Geometry

🚀 Project Overview

This project leverages Meta AI's ESM-2 protein language model to assess the functional impact of protein mutations based on changes in embedding space. Instead of structural prediction, this tool analyzes how amino acid substitutions shift a protein's embedding and uses geometric reasoning to estimate whether the mutation is likely benign or disruptive.

🔥 Key Features

Uses pretrained ESM-2 foundational models (no retraining required).

Computes embedding shift due to specific mutations.

Embedding Stability Score (ESS) via Z-score against a neutral mutation distribution.

Visualizes mutation effects relative to random neutral mutations.

Fast, interpretable, and extendable.

🧠 How It Works

1. Embedding Extraction

Converts the wild-type protein sequence into an embedding using ESM-2.

Mutates a specific amino acid (e.g., L to P at position 50).

Computes the embedding of the mutated protein.

2. Neutral Drift Distribution

Generates random neutral mutations.

Computes embedding distances (cosine) between wild-type and these random mutants.

This forms a background distribution of normal, non-disruptive embedding shifts.

3. Embedding Stability Score (ESS)

Measures how far the test mutation's embedding shifts from the wild-type relative to the neutral background.

Computes a Z-score:

Z = (mutation_distance - mean(neutral_distances)) / std(neutral_distances)

4. Inference

Z > 2: Likely disruptive mutation.

Z <= 2: Likely benign mutation.

📊 Example Output

=== Embedding Stability Analysis ===
Mutation: (5, 'P')
Embedding Distance: 0.1421
Neutral Mean Distance: 0.0789
Neutral Std Dev: 0.0195
Z-Score: 3.24
⚠️ Likely Disruptive Mutation

🧰 Installation

pip install -r requirements.txt

🚀 Running the Script


📓 Running the Notebook

Open Protein_Mutation_Impact_Analysis.ipynb to interactively explore and visualize embedding shifts.

🧪 Requirements

Python >= 3.8

transformers

torch

numpy

scipy

matplotlib

seaborn

🚀 Future Extensions

Add support for batch mutation analysis.

Build a Streamlit UI for non-technical users.

Extend to multi-mutation trajectories in embedding space.

Compare embeddings across species for evolutionary analysis.

❤️ Acknowledgements

Meta AI for ESM-2 model.

HuggingFace Transformers.

Open-source bioinformatics communities.

📜 License

MIT License.

🔗 Citation

If you use this repository, please consider citing Meta's ESM-2 foundational model.

✨ Author

Developed by Allan Binu.  

