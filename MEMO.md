# How to setup（in he）
```bash
python -m venv venv
pip install --upgrade pip setuptools wheel
pip3 install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu118
pip install git+https://github.com/nerfstudio-project/gsplat.git
pip install evo
pip install open3d
cd src/croco/models/curope/
python setup.py build_ext --inplace
cd ../../../../
pip install gdown
cd ..
pip install -r requirements.txt
pip install evo
pip install torchinfo
pip install torchvista
```

# 変更点メモ
kernels.cuの中を少し変更。buildに支障が出たため。
- before  
`AT_DISPATCH_FLOATING_TYPES_AND_HALF(tokens.type(), "rope_2d_cuda", ([&] {`
- after  
`AT_DISPATCH_FLOATING_TYPES_AND_HALF(tokens.scalar_type(), "rope_2d_cuda", ([&] {`

