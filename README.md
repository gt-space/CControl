# CControl
- CControl is a library written in 100% ANSI C (C89) code and is forked from this [project](https://github.com/DanielMartensson/CControl.git) that is used by the RECO project running on a STM32.  

- While the original library has many components ranging from image processing and machine learning, the current library has been trimmed down to solely contain the linear algebra components.  
	- To add back the old functionality, just add the folder from the original project is `Sources` back into the `Sources` of this repo and update the `sources.h`  

- The current implementation of the linear algebra library uses CLAPACK and has modified the original project to calculate the eigenvalues and eigenvectors (`eig()`) using double-precision instead of the native single-precision  

- The library comes with a limited set of LAPACK routines and therefore if the routines you want are not implemented, you must add them yourself which can be done by:  
	1. Searching up the routine you want implemented and finding its documentation online (typically stored in a NetLib site)  
	2. Downloading the dependencies in the documentation site as a `.zip` or `.tar`
	3. Downloading CLAPACK v3.2.1 from the Netlib  
	4. Look at the dependencies for your routine (from Step 2) and copy them from the CLAPACK v3.2.1 from Step 3 into the `Sources/LinearAlgebra/CLapack/Routines` folder  
	5. Adding the function header of the routine you wanted to use to the `routines.h` file in `Sources/LinearAlgebra/CLapack/Routines`  

- After doing all those steps, you should be able to call your routine by including the `ccontrol.h` header  

- For more information about the library, please go to the original projects README [here](https://github.com/DanielMartensson/CControl/blob/master/README.md)  