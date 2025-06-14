# PigmentML
PigmentML is a machine learning-based system that predicts optimal paint mixing ratios to match any target color using a fixed set of base pigments. Instead of relying on traditional physics models like Kubelka-Munk, this project uses data-driven learning to map pigment combinations to their resulting colors.

However, achieving this data-driven learning presents unique challenges. Simple linear RGB averaging doesn't accurately capture how paints mix, and creating a large, comprehensive physical dataset is impractical. Therefore, the most effective approach is to combine a small,  high-quality real dataset with a larger, calibrated synthetic dataset.

## Project Phases (Progress So Far)

1.  **Small, High-Quality Real Dataset (Calibration Data):** Collecting physical paint swatches and accurately measuring their RGB values to formaulate how the specific paints behave. *(Current status: Dataset collected, initial analysis performed, ready for preprocessing.)*
2.  **Forward Mixing Model:** Training a machine learning model (e.g., a neural network) on the real calibration data to learn how given pigment ratios result in a specific RGB color.
3.  **Calibrated Synthetic Dataset Generation:** Using the trained forward model to generate a much larger dataset of pigment mixes and their predicted RGB values. This will greatly expand the range of colors the AI can learn from.
4.  **Inverse Mixing Model:** Training a second model on the synthetic dataset to perform the core task: taking a target RGB color and predicting the pigment ratios needed to achieve it.
5.  **User Interface:** Developing a user-friendly application to interact with the inverse model.
