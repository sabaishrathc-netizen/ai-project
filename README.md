# ai-project
<!-- This is the markdown template for the final project of the Building AI course, 
created by Reaktor Innovations and University of Helsinki. 
Copy the template, paste it to your GitHub README and edit! -->

# AuraStyle: AI Personal Color Palette & Event Outfit Recommender

Final project for the Building AI course

## Summary

AuraStyle is an intelligent recommendation system designed to help users select optimal party wear and formal garments. By evaluating personal color contrasts and body frame attributes, the AI systematically matches user profiles with clothing items that maximize visual harmony.


## Background

Shopping for formal events, galas, or freshers' parties often involves a tedious cycle of trial and error. 

* **The Problem:** Many individuals struggle to identify which jewel tones, fabric structures, and silhouette styles (such as waist definitions and structured shoulders) best complement their natural physical profile and contrast level.
* **Severity:** Uninformed wardrobe choices lead to consumer return waste, lost time, and unnecessary stress during milestone social events.
* **Motivation:** Personal styling advice is typically costly and inaccessible. An AI-driven approach democratizes style recommendations by providing systematic, data-backed guidance.


## How is it used?

The solution is used by individuals preparing for formal events or social gatherings who need fast, personalized garment recommendations.

1. The user provides input regarding their color contrast preferences (e.g., Deep Winter jewel tone palette) and desired garment features (e.g., waist definition, structured shoulders).
2. The user selects the event context (e.g., freshers' party, formal dinner).
3. The system processes the input features against a catalog of apparel items and outputs a ranked selection of recommended outfits.


## Data sources and AI methods

* **Data Sources:** A curated database of formal apparel annotated with numerical and categorical attributes:
  * Color hue and saturation values mapped to seasonal color analysis models.
  * Silhouette structural metrics (e.g., waist definition index, shoulder structure score).
* **AI Methods:**
  * **$k$-Nearest Neighbors ($k$-NN):** Computes Euclidean distances between the user's target profile vector and the clothing item vector to find nearest matching options.
  * **Logistic Regression:** Classifies whether a specific garment's color scheme aligns with the user's contrast tier, returning a match probability score.

```python
import numpy as np

# Sample feature vector: [waist_definition, shoulder_structure, jewel_tone_match]
user_profile = np.array([0.9, 0.8, 1.0])
garment_features = np.array([0.85, 0.75, 0.95])

# Calculate similarity using Euclidean distance
distance = np.sqrt(np.sum((user_profile - garment_features) ** 2))
print("Match Distance:", distance)
