# Exercises from Natural Language Processing with Transformers

@saffrydaffry

This repo contains my personal implementation of code and explanations of concepts described in the book Natural Language Processing with Transformers by Tunstall, von Werra, and Wolf.  My implementation is simply modified from the notebooks from the book's official repo [https://github.com/nlp-with-transformers/notebooks](https://github.com/nlp-with-transformers/notebooks).

## Setup
The code was written and developmentally completed on local jupyter notebooks using the python dependencies pinned in the requirements.txt file under the `notebooks` directory.  However, because of the performance advantages of CUDA GPUs, the model training actually takes place in Google Colab notebooks.

```{bash}
# Install C++ dependencies
brew install liblo libsndfile

# To permanently define these variables, put into ~/.zprofile
export CPATH=/opt/homebrew/include
export LIBRARY_PATH=/opt/homebrew/lib

# Create a virtual env within the repo root
# cd <relative-path>/nlp_with_transformers
python3 -m venv nlp
source nlp/bin/activate
cd notebooks

# Install dependencies into venv from book's requirements.txt
pip install --upgrade pip
pip install -r requirements.txt

# install other dependencies
pip install notebook git-lfs pysndfile

# for mac, ${CUDA} = "cpu"
# note, cudatoolkit is not support on Apple Silicon :(
CUDA=cpu
pip install torch-scatter -f https://data.pyg.org/whl/torch-2.1.0+${CUDA}.html

#launch jupyter
jupter notebook
```