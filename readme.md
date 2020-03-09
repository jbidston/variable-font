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
pyftsubset ttf/Poppins-Regular-VF.ttf \
    --text-file="characterset.txt" \
    --flavor="woff2" \
    --output-file="woff2/poppins.woff2"
```
