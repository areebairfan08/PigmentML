# PigmentML
PigmentML is a machine learning-based system that predicts optimal paint mixing ratios to match any target color using a fixed set of base pigments. Instead of relying on traditional physics models like Kubelka-Munk, this project uses data-driven learning to map pigment combinations to their resulting colors.

## Phase 1: Creating a Small Real Dataset (Calibration Data)
### Goal: ~50-100 physically mixed and measured data points that are expceptionally accurate. This will teach the system the non-linear behaviour of the specific paint palette
The whole idea behind this project is to teach a computer how to mix paints. But for that to happen, it first needs to see a bunch of real-world examples of what happens when different paints are mixed (This process is called supervised learning — where the model is trained on input–output pairs (paint mix → resulting color) so that it can later predict mixes for new target colors). 

### Choosing the "perfect" palette 
Traditionally, your primary colours are red, yellow, and blue, and in theory, you should be able to mix most colours from just these three paints. But in reality, this is not the case, you will find that some colours you mix are very muddy and not the vibrant colours you were looking for. To mix as many colours as possible, we will have to expand our palette a bit. 

#### Warm and Cool Colours
Having both sets of red, yellow, and blue in both warm and cool colours will help us get the most variety in colours by unlocking a much wider range of secondary colours and overall flexiabilty. This approach is known as the split-primary palette, and it's widely used by artists. 
- Warm colours lean toward orange or yellow tones
- Cool colours lean toward blue or green tones

For a machine learning model, this is especially important. The model will learn better if it’s trained on examples that span the full color space. By using both warm and cool primaries, we create a more diverse and representative dataset leading to more accurate and reliable predictions when mixing paints.

#### Controlling light, dark and in-between 
In addition to hue, colours have two key properties that influence how they’re perceived and mixed:
- Value: how light or dark a colour is
- Saturation: how pure or dull a colour is
To control these properties, we need more than just the primary colours. This is where white, black, and brown become essential:
- White: Used to increase value, making colours lighter and allowing us to mix tints
- Black: Used to decrease value, making colours darker, helping to create shades and deep shadows
- Brown: Adds warmth and realism to mixes, especially skin tones, wood, and earth tones. It helps tone down overly saturated colours without turning them grey like black might.
