Dog-Breeds Classification
This project is meant to be installed on and run on a Nvidia Jetson Orin Nano

How it works
This project uses a YOLOv5 object detection model trained to detect different dogs. The model looks at an input image and checks if the dog matches any breeds in the data.

It runs the image through the model.

The model returns a picture showing if the dog breeds are present.

The script then labels the image.

Instructions
1. Download Model and Config Files

Download the following files and extract them into a new folder:

best.pt

data.yaml
2. Install Dependencies

git clone https://github.com/ultralytics/yolov5.git
cd yolov5
pip install -r requirements.txt
pip install torch
pip install torchvision
3. Prepare the Project Folder

Create a folder called Dog-Breeds-Classification in your home directory:

mkdir ~/Dog-Breeds-Classification
Drag your model and config files into that folder

Create a folder to hold your input images:

cd Dog-Breeds-Classification
mkdir ~/Dog-Breeds-Classification/images
Place the images you want to run the model on into the images/ folder.

Your file structure should look like this:

image

4. Run the Model

python detect.py --weights ~/Dog-Breeds-Classification/best.pt --data ~/Dog-Breeds-Classification/data.yaml --source ~/Dog-Breeds-Classification/images/ --img 640 --conf 0.2 --project ~/Dog-Breeds-Classification --name detected
The output images will be saved in ~/Dog-Breeds-Classification/detected/.

If too many objects are being falsely detected, increase the confidence to a higher percentage (ex: --conf 0.4)

If too few objects are being detected, decrease the confidence level to a lower percentage (ex --conf 0.1)
