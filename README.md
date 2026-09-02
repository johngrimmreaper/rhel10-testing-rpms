# Reaper RHEL 10 Testing RPM Repository

Public, signed **testing RPM repository for RHEL 10**, containing preview and pre-release packages built and validated for Enterprise Linux 10.

# ⚠️ Stable repository required

Packages in this testing repository may depend on packages from the corresponding stable repository. Enable the stable repository together with this testing repository.

Stable repository:

## **[https://johngrimmreaper.github.io/rhel10-rpms/](https://johngrimmreaper.github.io/rhel10-rpms/)**

# 🌐 Browse the testing repository

## **[https://johngrimmreaper.github.io/rhel10-testing-rpms/](https://johngrimmreaper.github.io/rhel10-testing-rpms/)**

The published site provides the complete package inventory, RPM metadata, repository descriptors, signing key, package browser, and current repository usage information.

## Configure the repositories

RPM package signatures and repository metadata signatures are enabled.

Repository signing-key fingerprint:

```text
E4C3 D7CD 3003 57A5 07C2 B237 FF30 3241 B8B8 606D
```

Install the signing key, enable both stable and testing repository descriptors, then refresh DNF metadata:

```bash
sudo rpm --import https://johngrimmreaper.github.io/rhel10-testing-rpms/RPM-GPG-KEY
sudo curl -fsSL https://johngrimmreaper.github.io/rhel10-rpms/repo/reaper-rhel-10-stable.repo -o /etc/yum.repos.d/reaper-rhel-10-stable.repo
sudo curl -fsSL https://johngrimmreaper.github.io/rhel10-testing-rpms/repo/reaper-rhel10-testing-rhel-10-testing.repo -o /etc/yum.repos.d/reaper-rhel10-testing-rhel-10-testing.repo
sudo dnf makecache --refresh
```

Both repository descriptors enable `gpgcheck=1` for RPM package signatures and `repo_gpgcheck=1` for signed repository metadata.

## Repository architecture

The `main` branch contains repository documentation. Published RPMs, signed `repodata/`, repository descriptors, the public signing key, and the generated static package browser are deployed to the `gh-pages` branch by `rpm-builder`.

Paired private build-control repository: `johngrimmreaper/rhel10-testing-rpm-packaging`.

Stable and testing publication are physically separated. The testing channel may consume packages from the stable channel, while its generated deployment remains independently replaceable and rebuildable from the private controller.
