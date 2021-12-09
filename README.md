### [Quick_Okada.ipynb](https://colab.research.google.com/github/jiangyuinsar/okada_wrapper/blob/master/Quick_Okada.ipynb): Quick view of surface deformation caused by earthquakes in 3D or satellite line-of-sight directions (InSAR). The script is run in Google Colab platform & free of charge!


------------------------------------------------
The following text partially refers to [Okada_Wrapper](https://github.com/tbenthompson/okada_wrapper) repository. 

#### Okada wrapper (Python)

Okada dislocations in Python! 

These files are MATLAB and Python wrappers for the Okada DC3D0 point source
and the DC3D rectangular dislocation surface fortran subroutines. The Matlab 
wrappers are written using the MEX functions. The original subroutine was 
written by Y. Okada as part of the paper:

**Okada, Y., 1992, Internal deformation due to shear and tensile faults in a half-space, Bull. Seism. Soc. Am., 82, 1018-1040.**

The inputs and outputs here are slightly different from the okada implementation,
though not in any substantial way. Look at the [original documentation webpage
here](http://www.bosai.go.jp/study/application/dc3d/DC3Dhtml_E.html) for more details

A different MATLAB mex wrapper for the Okada dislocation sources is available on [Paul Segall's website](https://pangea.stanford.edu/research/CDFM/software/index.html).

#### Python

NEW: You can install `okada_wrapper` directly from the PyPI by running::

```
pip install okada_wrapper
```

For the old, manual installation method, download the code::

```
git clone https://github.com/tbenthompson/okada_wrapper.git
```

Make sure that a Fortran compiler is installed. The wrappers are tested using gcc/gfortran, but should hopefully work with other fortran compilers.

Then, run the install script::

```
python setup.py install
```

The syntax is almost identical to the MATLAB version::

```
from okada_wrapper import dc3d0wrapper, dc3dwrapper
success, u, grad_u = dc3d0wrapper(0.6, [1.0, 1.0, -1.0], 3.0,
                                  1.0, [1.0, 0.0, 0.0, 0.0])
success, u, grad_u = dc3dwrapper(0.6, [1.0, 1.0, -1.0],
                                 3.0, 90, [-0.7, 0.7], [-0.7, 0.7],
                                 [1.0, 0.0, 0.0])                                      

