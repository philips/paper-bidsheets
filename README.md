# paper-bidsheets

This is a system to create paper auction bidsheets with Google Sheets and scan
them using Ollama.

## Data Preparation

1. Scan the bidsheets. Using a mobile device works fine.
  - [iOS](https://support.apple.com/en-us/108963)
  - [Android](https://support.google.com/drive/answer/3145835?hl=en&co=GENIE.Platform%3DDesktop)

2. Convert PDF to individual images with ImageMagick. Using 76px/in seems to be more than sufficient. 

```
convert -density 76 input.pdf output-%d.png
```

3. Run the script over the files

```
for i in `seq 1 5`; do go run main.go prompt.xt output-$i.png ; done
```

# TODO

- Experiment with lower density
- Experiment with llava
- Link to bidsheet template
- Add sample PDF and PNGs
