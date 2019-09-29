# tfutils-orb
A CircleCI orb for utilities to set up and run tools for Terraform. e.g. terraform cli, tflint and so on.

# Example
```
version: 2.1

orbs:
    tfutils: ukslee/tfutils@x.y.z

jobs:
    build:
        docker:
        - image: your-image
        steps:
        - checkout
        - tfutils/install
        - tfutils/terraform:
            arguments: init
        - tfutils/terraform:
            arguments: plan -var-file=foo
        - tfutils/terraform:
            arguments: apply -var-file=foo

workflows:
    your-workflow:
        jobs:
        - build
```
