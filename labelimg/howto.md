# How to use labelImg

## Setup

1. Download the latest release binaries `.zip` file: https://github.com/tzutalin/labelImg/releases ([windows_v1.8.1.zip](https://github.com/tzutalin/labelImg/files/2638199/windows_v1.8.1.zip) as of 2020-01-13)
2. Open the `.zip` file and extract the all contents to a place of your choice
3. ⚠ **IMPORTANT** ⚠: Open the `predefined_classes.txt` file in the `data` folder next to the `labelImg.exe` and replace the contents of the file with:

```text
elephant
tiger
star
cat
frog
```

## Claim an image set

1. Open the `Wer-Macht-Was` file in the shared GDrive folder and insert yourself as an owner of an image set and set the status to `wip`.
2. Download the folder you just took ownership of and start labeling ☺ 

## Labeling

1. Open `labelImg.exe`
2. ⚠ **IMPORTANT** ⚠: Switch the label style by clicking on the `Pascal/VOC` button on the left toolbar so that it is set to `YOLO`
3. Click on `View` (top toolbar) and enable auto mode by clicking on `Auto Save Mode`
4. Open the folder which contains the images to be labeled by pressing the `Open Dir` button
5. Click on `Change Save Dir` (left toolbar) and select the `labels` folder as destination for label files.
6. Draw a rectangle around each pet in the picture using the `Create \nRectBox` button and label it with on of the labels (`elephant`, `tiger`, `star`, `cat`, `frog`). It is important to use **exactly** those labels!
7. If you labeled every animal in a picture press the `Next image` button
8. `labelImg` will create a `.txt` file for each image. Happy labeling! 😀

FYI: labelImg has some useful [hotkeys](https://github.com/tzutalin/labelImg#hotkeys)!

## ⚠ **IMPORTANT RULES FOR LABELING** ⚠

* **DO NOT** label an animal if it is not 100% visible (e.g. one half is cut off the image)
* **DO NOT** label animals which are very far away and hard to detect
* If there is an image without an animal on it just skip it. We'll delete useless `.png` files from GDrive when you submit your labels
* If an image is blurry label it nevertheless!
* If an image is very **VERY** blurry and you have a hard time detecting the animals **DON'T** label it.

## Submitting labels

1. Upload the `labels` folder containing your labels to the folder you claimed earlier.
2. Update the status of the folder in the `Wer-Macht-Was` file
3. Thank you 🙂