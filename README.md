# iocost-benchmark

The iocost-benchmark repository holds user-submitted benchmarks generated from
the [resctl-bench](https://github.com/facebookexperimental/resctl-demo) tool
and overall parameter sets which have been generated from these user-submitted
benchmarks.

You can create an installable image to run the benchmark by downloading
[this image](https://nightly.link/iocost-benchmark/resctl-demo-image-recipe/workflows/ci.yaml/main/resctl-demo-flasher-efiboot.zip)
and following [this instruction](https://github.com/iocost-benchmark/resctl-demo-image-recipe/blob/main/DEPLOY.md).

## Licence

All submitted benchmarks shall be licened under the `LICENCE` file in the root
of the repository.

## Submitting a benchmark

To submit a benchmark, a user should create an issue in this repository using
the `Benchmark submission` issue template and attach the result(s) with the
extension `.json.gz` to the issue by dragging and dropping the file on to the
issue body.

## Contributing

The code which handles user-submissions behind-the-scenes is available under the
[iocost-benchmarks-ci](https://github.com/iocost-benchmark/iocost-benchmarks-ci/)
repository. Please see the contents of that repository to contribute to the
benchmark processing scripts.

Otherwise, please open an issue to report bugs or suggest features.
Pull-requests are very welcome!
