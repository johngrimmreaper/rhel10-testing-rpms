# rhel10-testing-rpms

Public generated **testing RHEL 10 RPM repository**.

Paired private build-control repository: `johngrimmreaper/rhel10-testing-rpm-packaging`.

The `main` branch contains only repository documentation. Published RPMs,
SRPMs, signed `repodata/`, repository descriptors, the public signing key,
generated provenance and the static package browser are generated onto the
`gh-pages` deployment branch by `rpm-builder`.

Packages in this channel are testing/preview artifacts and are not the stable
RHEL 10 channel. Stable and testing publication are physically separated and
protected by the controller/destination pairing guard.

Legacy RPM binaries from `johngrimmreaper/rpm-packages` are intentionally not
copied into this repository.

Expected Pages URL after first publication:

`https://johngrimmreaper.github.io/rhel10-testing-rpms/`
