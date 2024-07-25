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

### Creating a GitHub issue

To submit a benchmark, users should create a GitHub issue in this repository using
the `Benchmark submission` issue template and attach the result(s) with the
extension `.json.gz` to the issue by dragging and dropping the file into the
issue body.

### Automated with AWS lambda workflow

The submission of benchmark has been automated using [AWS lambda workflow](https://github.com/facebookexperimental/resctl-demo/blob/main/resctl-bench/doc/lambda.md) which uploads the benchmark directly from the `resctl-bench` software. An AWS lambda function submits the issue with link to `.json.gz`. This allows users to upload benchmarks without a GitHub account.
To upload a benchmark result  using the AWS Lambda function, `resctl-bench` can be ran like:
resctl-bench -r <RESULT_JSON> upload --upload-url  <AWS lambda function URL>
e.g  
`$resctl-bench --result resctl-bench-result_2022_07_01-00_26_40.json.gz upload --upload-url https://ygvr6jnjckwamfao5xztg6idiu0ukjeb.lambda-url.eu-west-1.on.aws`


## CI workflow

### Importing result

Once a GitHub issue is created or updated the GitHub action `import-result` is triggered, which downloads the benchmark result and creates a GitHub pull request for merging it to the `main` branch along with additional metadata information.

### Merging results together with resctl-bench

The Pull request created by importing steps should be approved and merged manually to `main` branch. Once merged, github action `Merge results` merges the benchmarks data and generates the final hwdb file.  

The following artifcats are uploaded to the CI workflow for each trigger:
  - Final hwdb file
  - Merged results
  - PDFs
  - hwdb input Files


## Contributing

The code which handles user-submissions behind-the-scenes is available under the
[iocost-benchmarks-ci](https://github.com/iocost-benchmark/iocost-benchmarks-ci/)
repository. Please see the contents of that repository to contribute to the
benchmark processing scripts.

Otherwise, please open an issue to report bugs or suggest features.
Pull-requests are very welcome!
