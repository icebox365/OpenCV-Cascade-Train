### Detecting the Tree with Haar-Cascade training ###

[guide] http://www.tectute.com/2011/06/opencv-haartraining.html
[video] https://www.youtube.com/watch?v=Dg-4MoABv4I

download the zip file : utilities

* step for training the detector with the Haar-Cascade

    step 1: prepare the positive images as bmp files
        copy and paste them to the folder [./positive/rawdata]
    
    step 2: prepare the negative images as jpg or bmp
        copy and paste them to the folder [./negative]
    
    step 3: create the negative info file[./negative/bg.txt]
        run the	[./negative/create_list.bat] file (open and detect the file format jpg or bmp)
    
    step 4: create the positive info file
        run the [./positive/objectmarker.exe] and draw the rectangle with mouse drag
        hotkey: [space] and [enter]
    
    step 5: creating samples
        run [./01 samples_creation.bat] the [./vector/vector.vec]
    
    step 6: haar training
        delete all folders in [./cascade/ ]
        open [./02 haar training.bat] and replace the [-npos XX] and [-nneg XX] as number of positive and negative images
        run this bat

	step 7: generate the .xml file run[./03 conver.bat]



OpenCV 3.2.0
Haar-Cascade training

number of positive images = 485
number of negative images = 950
nstage = 0.995^14 = 0.932

(485-100)/(1+13*(1-0.932)) = 385 * 1.8847 = 204

### Trained model

3 pretrained models were saved on /model folder
/model/ 

    myhaar_20_40_20.xml    TreeHaar_1st.xml    TreeHaar_2nd.xml
    
    
The poor detector for real-time video processing
myhaar_20_40_20.xml 

Enough trained models for image processing
TreeHaar_1st.xml
TreeHaar_2nd.xml

### Draw line instead of rects
Calculate the line coefficients with its direction.

    Y = AX + B
Calculate the coefficients A, B with the coordinats of detected rects.

