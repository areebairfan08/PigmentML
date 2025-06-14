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

So, let's break down the palette used for this project:
1. **Cadmium Red Medium Hue**: This is our _**Warm Red**_. It leans slightly orange and is great for strong earthy mixes and is essential for mixing vibrant oranges and warm browns. 
2. **Medium Magenta**: This is our **Cool Red**. When mixed with a true primary blue, it's crucial for mixing clean, vibrant purples. Without a cool red like magenta, purples usually end up looking dull or brownish.
3. **Cadmium Yellow Medium Hue**: This is our _**Warm Yellow**_. It's great for bright greens when mixed with blue, and fiery oranges with warm reds.
4. **Primary Yellow**: This is our _**Cool Yellow**_. This yellow leans slightly green. When mixed with a cool blue, it helps you get brilliant, clear greens that aren't muddy or olive-toned. This broadens our green range.
5. **Ultramarine Blue**: This is our _**Warm Blue**_. This is a rich, slightly purple-leaning blue. It's fantastic for deep, moody purples when mixed with red/magenta, and subdued greens.
6. **Phthalocyanine Blue**: This is our _**Cool Blue**_. This blue is  very intense and leans towards green. It's our true primary blue/cyan. When mixed with a cool yellow, it's essential for making those bright, vibrant electric greens.
7. **Burnt Umber**: This is our _**Brown**_. This is an earthy, warm brown that's great for desaturating colors, creating natural shadows, or mixing custom browns.
8. **Mars Black**: This is our _**Black**_. Compared to other black paints, this is neutral and doesn’t shift colours too much when mixed.
9. **Titanium White**: This is our _**White**_. It is extremely opaque, meaning it covers and lightens colours quickly. It has strong tinting power, which is imporant as discussed earlier. 
