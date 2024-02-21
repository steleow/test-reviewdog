# SAMPLE

github action:
<https://github.com/aquasecurity/trivy-action>

Docs:

- <https://github.com/aquasecurity/trivy/blob/main/pkg/fanal/secret/builtin-rules.go>
- <https://aquasecurity.github.io/trivy/v0.49/docs/scanner/secret/#configuration>

Prerequisites:

- install pre-commit

``` bash
# pre-commit
brew install pre-commit

pip install pre-commit

# Trivy
trivy fs --scanners vuln,secret,misconfig . --exit-code 1 # default exit code is 0
trivy config . --compliance k8s-nsa --exit-code 1 # default exit code is 0

# gitleaks
gitleaks protect --config=./gitleaks.toml -v # -r report.json
gitleaks detect --config=./gitleaks.toml -v # -r report.json

# git-detect
git secrets --install
git secrets --add
git secrets --add-provider -- git secrets --aws-provider

git secrets --list

git secrets --add 'apiKey\s*=\s*.+'
git secrets --add 'secret\s*=\s*.+'
git secrets --add 'password\s*=\s*.+'

git secrets --scan
```
