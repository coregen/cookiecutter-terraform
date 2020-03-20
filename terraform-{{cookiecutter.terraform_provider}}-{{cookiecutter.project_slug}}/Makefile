clean: clean-build

clean-build: ## remove build artifacts
	rm -fr .terraform
	rm -fr terraform.tfstate*

lint: ## check style with flake8
	terraform validate

## run tests quickly with the default Python
test: lint
	terraform init
	terraform plan

bump-patch:
	bump2version patch

bump-minor:
	bump2version minor

push-tags-master:
	git push origin master --tags

release-patch: bump-patch push-tags-master release
release-minor: bump-minor push-tags-master release
