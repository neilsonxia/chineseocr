##CPU 环境配置，支持linux\macOs
conda create -n chineseocr python=3.6 pip scipy numpy jupyter ipython ##运用conda 创建python环境
source activate chineseocr
git submodule init && git submodule update
cd darknet/ && make && cd ..
(CFLAGS='-stdlib=libc++')pip install easydict opencv-contrib-python==3.4.2.16 Cython h5py lmdb mahotas pandas requests bs4 matplotlib lxml -i https://pypi.tuna.tsinghua.edu.cn/simple/
pip install -U pillow -i https://pypi.tuna.tsinghua.edu.cn/simple/
pip install web.py==0.40.dev0
pip install keras==2.1.5 tensorflow==1.8
## mac
conda install pytorch torchvision -c pytorch
## linux
## conda install pytorch-cpu torchvision-cpu -c pytorch
pushd text/detector/utils && sh make-for-cpu.sh && popd

