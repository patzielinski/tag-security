# tj-actions/changed-files: Compromised GitHub action leaks secrets

A malicious actor compromised the `tj-actions/changed-files` GitHub action to leak CI/CD secrets from repositories using
the action. The attacker utilized a compromised Personal Access Token (PAT) to update the action's version tags to point
to a malicious commit from outside the repository. Whenever run, the compromised action leaked secrets in actions
logs, which are often publicly accessible.

## Impact

The `tj-actions/changed-files` action is used by over 23,000 repositories and is used to identify the changed files and
directories compared to a certain branch. Repositories with public workflow logs were impacted the most, as their
secrets were made available to anyone who viewed the logs.

## References

- [StepSecurity Blog](https://www.stepsecurity.io/blog/harden-runner-detection-tj-actions-changed-files-action-is-compromised#recovery-steps)
- [GitHub Advisory](https://github.com/advisories/GHSA-mrrh-fwg8-r2c3)
