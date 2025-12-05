# 🧹 NormCleaner  
### The CCleaner for your mental norms (AI-LGN Module)

---

## Overview

**NormCleaner** is a core module of the **AI-LGN** project.  
It analyzes natural language input and tries to identify **implicit norms** – the "I must", "I should", "I can't" rules that shape how people think and act.

Many of these norms are:

- outdated  
- internalized from family or culture  
- never explicitly agreed upon  
- imaginary constraints that still consume mental energy  

NormCleaner aims to:

- extract implicit norms from text  
- estimate whether a norm is **real** (externally enforced) or **imagined**  
- estimate the **cognitive load** associated with the norm  
- provide a first, lightweight recommendation for reflection  

This module is currently a **prototype** and is intended as a starting point for experimentation, not as a clinical or diagnostic tool.

---

## Goals

- 🧠 Make hidden mental rules visible  
- ⚖ Distinguish between real and imagined constraints  
- 🔋 Reduce unnecessary cognitive load  
- 🧭 Support inner clarity and decision-making  

---

## Project Status

- **Stage:** Early prototype / skeleton  
- **Language:** Python  
- **Focus:** Clear structure, extendable design, simple examples  

At the moment, NormCleaner does not use any heavy ML models.  
It provides a clear Python interface (`NormCleaner.analyze`) that can later be connected to NLP models, classifiers, or external APIs.

---

## Folder Structure

This module is located inside the main AI-LGN repository:

```text
AI-LGN/
└── modules/
    └── NormCleaner/
        ├── README.md
        ├── __init__.py
        └── norm_cleaner.py

Python Interface

The central entry point of this module is the NormCleaner class.

from modules.NormCleaner.norm_cleaner import NormCleaner

cleaner = NormCleaner()

text = "I feel like I must not disappoint anyone."
result = cleaner.analyze(text, context="work")

print(result)

The analyze method returns a dictionary with keys like:

{
    "norm_detected": "I must not disappoint anyone",
    "realness_score": 0.2,
    "origin": "internalized family rule (heuristic)",
    "cognitive_load": 70,
    "risk_level": "high",
    "recommendation": "It may be safe to disappoint others sometimes. Start with small, honest boundaries."
}

In the current prototype, these values are placeholder logic and simple heuristics.
They exist to demonstrate the shape of the data and to make experimentation easier.

⸻

Current Prototype Behaviour

The prototype implementation:
	•	scans for simple patterns like must, should, have to, can't
	•	extracts the clause around these patterns as a possible norm_detected
	•	assigns very rough, hardcoded values for realness_score, cognitive_load and risk_level
	•	returns a dictionary with a consistent structure

This is not meant to be smart yet – it is a scaffold that you can extend.

⸻

Roadmap

Planned future improvements:
	•	more robust norm extraction using NLP libraries (e.g. spaCy)
	•	support for German and multilingual inputs
	•	better realness classification using context information
	•	models for origin detection (family, culture, work, trauma patterns, etc.)
	•	more nuanced cognitive load estimation
	•	integration with other AI-LGN modules (NeedScanner, ConflictResolver, etc.)

⸻

Disclaimer

NormCleaner is an experimental tool for reflection, learning and research.
It is not a medical, therapeutic or diagnostic instrument and should not be used as such.


