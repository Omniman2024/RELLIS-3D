# Terminal Commands (local use only)

### Run the HRNet+OCR model on the {IMAGE, LABEL} pairs mentioned in test.lst   
Input : {Image, Label/Mask(Ground Truth)}  
Output : {Error Metrics(b/w Ground Truth and Prediction), Color-Coded HeatMap-type Segmented Image(Prediction)}:-
```
	python3 -m venv .hrnet_env # if new environment is required to be created

	source .hrnet_env/bin/activate # source the newly-created / existing environment

	cd /home/jarvis/RELLIS-3D/RELLIS-3D/benchmarks # skip if using existing environment

	pip3 install -r requirement.txt # skip if using existing environment

	pip install torch torchvision # skip if using existing environment

	cd /home/jarvis/RELLIS-3D/RELLIS-3D/benchmarks/HRNet-Semantic-Segmentation-HRNet-OCR

	export PYTHONPATH=/home/jarvis/RELLIS-3D/RELLIS-3D/benchmarks/HRNet-Semantic-Segmentation-HRNet-OCR:$PYTHONPATH
	
	python tools/test.py --cfg experiments/rellis/seg_hrnet_ocr_w48_train_512x1024_sgd_lr1e-3_wd5e-4_bs_12_epoch484.yaml --save DATASET.TEST_SET val.lst OUTPUT_DIR /mnt/c/Users/anubh/OneDrive/Desktop/RELLIS-output TEST.MODEL_FILE /mnt/c/Users/anubh/Downloads/seg_hrnet_ocr_w48_train_512x1024_sgd_lr1e-2_wd5e-4_bs_12_epoch484/best.pth
```
