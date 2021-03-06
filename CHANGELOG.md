# Changelog

## v0.14.0 (2020-09-14)

### Features

* Run notebooks written in R or other languages. See the newly added [R example][example] for information.
* When using the CLI or Library, you can supply extra arguments to the SageMaker Processing Job used to execute the notebook. For example to allow your notebook to run for up to a full day, invoke your notebook with `run-notebook run foo.ipynb --extra '{"StoppingCondition":{"MaxRuntimeInSeconds":86400}}'`. Using this mechanism, you can add extra inputs and outputs, connect to a VPC, add environment variables, expand disk space, add the run to a specific experiment, etc. See the [documentation for SageMaker Processing Jobs][processing-jobs] for more.
  
[example]: https://github.com/aws-samples/sagemaker-run-notebook/tree/master/examples/R
[processing-jobs]: https://docs.aws.amazon.com/cli/latest/reference/sagemaker/create-processing-job.html

### Running Notebooks

* Add an option to pass extra parameters to SageMaker Processing jobs from the CLI/Library (not yet supported in the JupyterLab extension).
* Add the ability to use the CLI to run the notebook using local Docker containers (`run-notebook local`).

### Container building (`run-notebook create-container`)

* Support base containers from ECR repos in other AWS accounts (to enable using [AWS Deep Learning Containers][dlc]).
* Add the `-k` option to allow alternate Jupyter kernels
* Add the `--script` option for running arbitrary shell scripts as part of building the container.
* Tail the build logs when running the build so you can see any errors that happen inline.
* Automatically install Python if the base image doesn't already have it.

[dlc]: https://docs.aws.amazon.com/deep-learning-containers/latest/devguide/deep-learning-containers-images.html

### JupyterLab Extension

* Fixes for running in Safari

## v0.13.0 (2020-06-15)

Initial release.
