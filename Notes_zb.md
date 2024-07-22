# Install python environment
conda create --name facefusion python=3.10
conda activate facefusion

# Install dependencies for project
conda install conda-forge::cuda-runtime=12.4.1 cudnn=8.9.2.26 conda-forge::gputil=1.4.0
conda install conda-forge::zlib-wapi

python install.py --onnxruntime cuda-12.2

# Run app with gpu backend
python run.py --execution-provider cuda --skip-download
