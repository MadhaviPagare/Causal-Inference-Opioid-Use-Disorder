# Causal-Inference-Opioid-Use-Disorder

Abstract—Opioid Use Disorder (OUD) affects physical health,mental well-being, and socio-economic stability, underscoring the need to understand the causal effects of social determinants on OUD outcomes. Despite extensive correlation studies between social determinants of mental health (SDMHs) and OUD, specific causal determinants remain unidentified due to the lack of robust causal models. This paper proposes a two-step causal effects identification framework to detect and identify the effects of SDMHs on OUD progression. Firstly, we developed a Multitask Multilabel Clinical-Longformer(MMCL) model to detect social determinants of Mental health from clinical notes, effectively processing and identifying relevant SDMHs within unstructured text data. Secondly, we employed a novel Siamese Neural Network(SNN)-based subgroup discovery technique to ascertain the causal effects of these social determinants on OUD. This technique leverages the Siamese architecture’s capability to handle complex relationships and identify homogeneous subgroups within the data, enhancing the precision of causal inference. To support this research, we collaborated with experts to create a new dataset, SDMHOUD-Clinic, comprising social determinants of Mental healthannotated clinical notes and OUD annotations, sub-sampled from the MIMIC-IV dataset. We evaluated the proposed models using the Infant Health and Development Program (IHDP) dataset and applied them to our newly created SDMH-OUD-Clinic dataset. The results demonstrate the model’s effectiveness and provide
detailed explanations of the identified causal relationships.

Step by step guide:
1. Clinical-Longformer Implementation and Training and Testing
Developed and trained the Clinical-Longformer model on annotated discharge summaries.
Objective: Detect presence of Opioid use Disorder and associated Social Determinants of Mental Health (SDMHs).

2. Prediction on 331,000 Notes 
Used the trained Clinical-Longformer model to run predictions on discharge.csv (containing ~331k clinical notes).

3.Siamese Neural Network-Based Subgroup Discovery
i) Embedding + Subgrouping 
Generated Bio_ClinicalBERT embeddings and created predictions_with_embeddings_sampled.csv.

ii)Performed subgroup discovery and visualized population distribution.

4. Final Determinant Analysis 
Applied the Siamese Neural Network for these determinants.
Output used for the final causal effect summary table.

Baseline Without Siamese Neural Network

5. Traditional Causal Inference -Inverse Probability weight(IPW)
Performed causal effect estimation without using the Siamese Neural Network.

Used for baseline comparison against the Siamese-enhanced pipeline.
