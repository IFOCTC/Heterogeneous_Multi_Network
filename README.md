# Patient–Region Heterogeneous Graph Neural Network (HGNN)

<p align="center">
  <img src="model.png" alt="Patient–Region HGNN Architecture" width="900">
</p>

This repository presents a two-layer heterogeneous graph framework for joint
patient-level and region-level prediction using a Heterogeneous Graph Neural Network (HGNN).

# Overview

The model represents medical data as a hierarchical graph with two interconnected layers:

> Layer 01 – Patients (Hyper-Edges)

Each node corresponds to a patient

Patients act as hyper-edges connecting their associated regions

Patient-to-patient relationships are modeled using cosine similarity

> Layer 02 – Regions

Nodes represent regions associated with patients

Intra- and inter-patient region connections are defined via cosine similarity

Each region belongs to exactly one patient

> Graph Construction

Patient–Region links define the hierarchical structure

Cosine similarity edges:

Between patients

Between regions (within and across patients)

Clustering is performed independently per layer, allowing overlapping computational labels

> Learning & Prediction

A Heterogeneous Graph Neural Network (HGNN) is applied to the full graph to jointly learn representations and produce:

Patient-level predictions

Region-level predictions

Both tasks are optimized simultaneously within a unified framework.

Key Notes

c denotes the class to predict

Region IDs encode patient membership (e.g., R01A → Region A of Patient 01)

The framework supports scalable extension to N patients

> Use Case

This architecture is well-suited for hierarchical biomedical data where:

Local (region-level) patterns inform global (patient-level) outcomes

Similarity-based relationships enhance representation learning
