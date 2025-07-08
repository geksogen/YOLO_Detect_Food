# YOLO_Detect_Food

unzip -q ./content/data.zip -d ./content/custom_data
wget -O ./content/train_val_split.py https://raw.githubusercontent.com/EdjeElectronics/Train-and-Deploy-YOLO-Models/refs/heads/main/utils/train_val_split.py
python3 ./content/train_val_split.py --datapath="./content/custom_data" --train_pct=0.9

apt-get update
apt install python3-pip
pip3 install ultralytics

python3 config_train.py 
cat ./content/data.yaml

yolo detect train data=./content/data.yaml model=yolo11s.pt epochs=60 imgsz=320
sudo yolo detect train data=./data.yaml model=yolo11s.pt epochs=60 imgsz=320