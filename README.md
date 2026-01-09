# Graph Convolution Network for fMRI Analysis Based on Connectivity Neighborhood

## Reference to Original Code

This implementation is based on the original cGCN work by Lebo Wang et al.

**Original Repository:** [https://github.com/Lebo-Wang/cGCN_fMRI](https://github.com/Lebo-Wang/cGCN_fMRI)

**Paper:** [Functional brain network classification with compact representation of SICE matrices](https://www.mitpressjournals.org/doi/pdf/10.1162/netn_a_00171)

For questions about the original work, please contact: lebo.wang@email.ucr.edu

## Data Files

The data files are not included in this repository due to size limitations. Please download them from the original repository:

### HCP Dataset
- [HCP Data (100 unrelated subjects)](https://drive.google.com/file/d/1l029ZuOIUY5gehBZCAyHaJqMNuxRHTFc/view?usp=sharing) - Save as `HCP_rfMRI_100s4s_236_MGTR_matlab_train_val_test.h5`
- [FC matrix](https://drive.google.com/file/d/1WP4_9bps-NbX6GNBnhFu8itV3y1jriJL/view?usp=sharing) - Save as `FC.npy`

### ABIDE Dataset
- [Leave-one-site-out dataset](https://drive.google.com/file/d/1xer4TMU1fqbwDO2wBOGrnIFuQ4v4Y3-o/view?usp=sharing) - Save as `ABIDE_I_leave_one_site_out.h5`
- [10-fold dataset](https://drive.google.com/file/d/1RhMRzDRT2vAkXDiW4t55Wbt8XRi6f9_x/view?usp=sharing) - Save as `ABIDE_I_10_fold.h5`

Place all downloaded data files in the repository root directory.

## Running on Kaggle

This code is optimized to run on Kaggle with GPU/TPU support.

### Quick Start on Kaggle

1. **Upload data to Kaggle Dataset**
   - Download the data files from the links above (HCP_rfMRI_100s4s_236_MGTR_matlab_train_val_test.h5 and FC.npy)
   - Create a new Kaggle dataset and upload these files
   - Name your dataset (e.g., "fmri-data")

2. **Create a new Kaggle Notebook**
   - Enable GPU: Settings → Accelerator → Select "GPU T4 x2"
   - Enable Internet: Settings → Internet → Turn ON
   - Add your fMRI dataset: Click "Add Data" → Search for your dataset → Add it

3. **Use the provided notebook**
   - Upload [kaggle_run_HCP.ipynb](kaggle_run_HCP.ipynb) or create a new notebook
   - The notebook expects data at `/kaggle/input/fmri-data/`
   - Run all cells to start training

### Features of the Kaggle Notebook

The provided `kaggle_run_HCP.ipynb` includes:
- **Direct GitHub integration** - Code loaded directly from this repository
- **Kaggle dataset integration** - Reads data from `/kaggle/input/fmri-data/`
- **GPU/TPU optimization** - Configured with mixed precision training and XLA compilation
- **Increased batch size** - Optimized for GPU memory (batch_size=16)
- **Training visualization** - Real-time plots and TensorBoard integration
- **Model checkpointing** - Automatic saving of best models

### Performance Optimizations

The Kaggle notebook includes several GPU optimizations:
- Mixed precision training (FP16) for faster computation
- XLA (Accelerated Linear Algebra) compilation
- Memory growth configuration to prevent OOM errors
- Larger batch sizes for better GPU utilization

### Dataset Path

The notebook expects your Kaggle dataset at: `/kaggle/input/fmri-data/`

Make sure your dataset contains:
- `HCP_rfMRI_100s4s_236_MGTR_matlab_train_val_test.h5` - Human Connectome Project data
- `FC.npy` - Functional connectivity matrix
