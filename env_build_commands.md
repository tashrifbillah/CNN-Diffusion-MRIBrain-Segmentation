# Instructions for building the CNN_MASKING environment that works on modern GPUs

```bash
conda create -y -n dmri-seg python=3.9
conda activate dmri-seg
pip install tensorflow==2.11
conda install -y -c anaconda::cudnn conda-forge::gputil
pip install nibabel scikit-image git+https://github.com/pnlbwh/conversion.git
```

After build the environment you need to set the LD_LIBRARY_PATH to the lib of your cuda installation:

```bash
export LD_LIBRARY_PATH=${CONDA_PREFIX}/lib/
```

Additionally you will need to source a compiled ANTs environment:

```bash
source /rfanfs/pnl-zorro/software/pnlpipe3/pnlpipe/soft_dir/ANTs-bin-ca32228/env.sh
```
