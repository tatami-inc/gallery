# Gallery of `tatami` examples

![Gallery](https://github.com/tatami-inc/gallery/actions/workflows/run-gallery.yaml/badge.svg)

This repository contains a gallery of demonstrations for using [**tatami**](https://github.com/tatami-inc/tatami).
All of the examples can be compiled with CMake using the commands below:

```sh
cmake -S . -B build
cmake --build build
```

This generates executables in the `build` subdirectory:

- `colsums`: use various extraction methods for a typical `tatami::numeric_matrix` to compute the column sums.
- `parallel`: compute row sums in parallel with OpenMP.
- `char2double`: store integers as `char` to save memory, but return them as `double`s for downstream use.
- `sparse_extractor`: compare sparse matrix access speeds with and without a workspace.

Each executable is named after the C++ source file from which they were generated.
Each file contains some commentary explaining the rationale behind each example.
