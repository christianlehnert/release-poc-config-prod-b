# release-poc-config-prod-b

Configuration of the environment **prod-b** for the release PoC.

- `terraform/versions.tfvars`: one line per application. The pipeline reads the versions from here, there is no version field in the pipeline form.
- Every change goes through a pull request. `CODEOWNERS` makes the lead's approval mandatory, also when the release bot opened the pull request.
- After the merge, the workflow **Tag and deploy** creates the next tag (`release/x.y.z`, this is the `config_tag`) and starts the deployment.

Standby site: same versions as prod-a, the health check is skipped because it gets no traffic. The deployment waits for the approval of the environment prod-b.

The whole flow: [release-poc-deployment](https://github.com/christianlehnert/release-poc-deployment#readme).
