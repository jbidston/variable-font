# Instructions for variable font optimisation

## Tool setup

### Install FontTools to convert font to Woff2 & Woff format and subset font.

- Install Python (https://www.python.org/downloads/) 3.8.2 at time of writing
- Install Brotli `pip3 install brotli`
- Install Zopfli `pip3 install zopfli`
- Install FontTools `pip3 install fonttools`

## Download font

### Download original font from Indian Type Foundry

https://github.com/itfoundry/Poppins

Note the `variable` directory containing beta variable font.

## Optimise font

```bash
# Create variable woff2 font file
pyftsubset ttf/Poppins-Regular-VF.ttf \
    --text-file="characterset.txt" \
    --flavor="woff2" \
    --output-file="woff2/poppins.variable.woff2"

# Create fallback regular woff2 font file
pyftsubset ttf/Poppins-Regular.ttf \
    --text-file="characterset.txt" \
    --flavor="woff2" \
    --output-file="woff2/poppins.regular.woff2"

# Create fallback regular woff font file
pyftsubset ttf/Poppins-Regular.ttf \
    --text-file="characterset.txt" \
    --flavor="woff" \
    --output-file="woff/poppins.regular.woff"

# Create fallback semibold woff2 font file
pyftsubset ttf/Poppins-SemiBold.ttf \
    --text-file="characterset.txt" \
    --flavor="woff2" \
    --output-file="woff2/poppins.semibold.woff2"

# Create fallback semibold woff font file
pyftsubset ttf/Poppins-SemiBold.ttf \
    --text-file="characterset.txt" \
    --flavor="woff" \
    --output-file="woff/poppins.semibold.woff"
```
