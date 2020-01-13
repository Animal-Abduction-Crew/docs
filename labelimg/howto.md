# How to use labelImg

## Setup

1. Download the latest release binaries `.zip` file: https://github.com/tzutalin/labelImg/releases
2. Open the `.zip` file and extract the all contents to a place of your choice
3. ⚠ **IMPORTANT** ⚠: Open the `predefined_classes.txt` file in the `data` folder next to the `labelImg.exe` and replace the contents of the file with:

```text
elephant
tiger
star
cat
frog
```

## Labeling

1. Open `labelImg.exe`
2. ⚠ **IMPORTANT** ⚠: Switch the label style by clicking on the `Pascal/VOC` button on the left toolbar so that it is set to `YOLO`
3. Open the folder which contains the images to be labeled by pressing the `Open Dir` button
4. Draw a rectangle around each pet in the picture using the `Create \nRectBox` button and label it with on of the labels (`elephant`, `tiger`, `star`, `cat`, `frog`). It is important to use **exactly** those labels!
5. If you labeled every animal in a picture press the `Save` button and afterwards the `Next image`

have fun 😀
