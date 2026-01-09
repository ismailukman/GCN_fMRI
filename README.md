# Graph Convolution Network for fMRI Analysis Based on Connectivity Neighborhood

## Reference to Original Code

This implementation is based on the original cGCN work by Lebo Wang et al.

**Original Repository:** [https://github.com/Lebo-Wang/cGCN_fMRI](https://github.com/Lebo-Wang/cGCN_fMRI)

**Paper:** [Functional brain network classification with compact representation of SICE matrices](https://www.mitpressjournals.org/doi/pdf/10.1162/netn_a_00171)

For questions about the original work, please contact: lebo.wang@email.ucr.edu

## Data Files

The data files are not included in this repository due to size limitations. Please download them from the original repository:

### HCP Dataset
- [HCP Data (100 unrelated subjects)](https://drive.google.com/file/d/1l029ZuOIUY5gehBZCAyHaJqMNuxRHTFc/view?usp=sharing) - Save as `HCP.h5`
- [FC matrix](https://drive.google.com/file/d/1WP4_9bps-NbX6GNBnhFu8itV3y1jriJL/view?usp=sharing) - Save as `FC.npy`

### ABIDE Dataset
- [Leave-one-site-out dataset](https://drive.google.com/file/d/1xer4TMU1fqbwDO2wBOGrnIFuQ4v4Y3-o/view?usp=sharing) - Save as `ABIDE_I_leave_one_site_out.h5`
- [10-fold dataset](https://drive.google.com/file/d/1RhMRzDRT2vAkXDiW4t55Wbt8XRi6f9_x/view?usp=sharing) - Save as `ABIDE_I_10_fold.h5`

Place all downloaded data files in the repository root directory.
