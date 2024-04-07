# Bazel issue with pip libraries and local folder

## Local benchmark
Use python with requirements.in/lock dependencies installed in environment - in this case Pyenv + Python 3.12.2 + virtualenv

`python -m unittest utils.lib_test` passes test

However bazel gets confused...

`bazel test //utils/lib_test` fails, mixing up utils/grpc folder for a nested dependency of the `google-cloud-...` package.