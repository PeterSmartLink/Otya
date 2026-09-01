# Otya public automation policy

GitHub currently provides free use of standard GitHub-hosted runners for public repositories. Otya may use this repository for public automation, but public visibility must never be used as a reason to weaken security or expose private source code.

## Allowed public workflows

- availability/smoke checks against public Otya URLs;
- public documentation validation;
- public API contract examples and schema linting;
- link, spelling and brand-consistency checks;
- checksum/signature verification using public release artifacts and public certificates/fingerprints;
- public release metadata generation from already-approved public inputs.

## Not allowed

- checking out a private Otya repository with a broadly scoped personal access token simply to avoid private Actions billing;
- printing secrets or sensitive environment variables to public logs;
- uploading private APK signing keys, service-account files, production database dumps or private source as artifacts;
- accepting untrusted pull-request code and then giving that job privileged secrets;
- using a public workflow as an undocumented production administration backdoor.

## If source repositories become private

Keep this repository public only for genuinely public automation. Builds/tests that require private source should run in the private repository or on a separately controlled runner. Public workflows can consume approved public release metadata or trigger a narrowly scoped authenticated endpoint after security review, but they should not become a proxy for unrestricted access to private source.

## Evidence rule

A green public workflow proves only what that workflow actually checked. It does not prove physical-device behavior, production deployment, account-provider configuration or end-to-end release acceptance unless those checks are explicitly part of the workflow and produce verifiable evidence.
