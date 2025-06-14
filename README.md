# PigmentML
PigmentML is a machine learning-based system that predicts optimal paint mixing ratios to match any target color using a fixed set of base pigments. Instead of relying on traditional physics models like Kubelka-Munk, this project uses data-driven learning to map pigment combinations to their resulting colors.



## Phase 1: Creating a Small Real Dataset (Calibration Data)
### Goal: ~50-100 physically mixed and measured data points that are expceptionally accurate. This will teach the system the non-linear behaviour of the specific paint palette

The whole idea behind this project is to teach a computer how to mix paints. But for that to happen, it first needs to see a bunch of real-world examples of what happens when different paints are mixed (This process is called supervised learning — where the model is trained on input–output pairs (paint mix → resulting color) so that it can later predict mixes for new target colors). 

### Choosing the "perfect" palette 
