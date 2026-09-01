# Reaper RHEL 10 Testing RPM Repository

Public, signed RPM package repository. Package signatures and repository metadata are cryptographically verified by the published repository configuration.

## Browse the repository

**[https://johngrimmreaper.github.io/rhel10-testing-rpms/](https://johngrimmreaper.github.io/rhel10-testing-rpms/)**

## Configure the repository

Repository signing-key fingerprint:

```text
E4C3D7CD300357A507C2B237FF303241B8B8606D
```

### Reaper RHEL 10 Testing RPM Repository - rhel-10 - testing

Repository ID: `reaper-rhel10-testing-rhel-10-testing`

```bash
sudo rpm --import https://johngrimmreaper.github.io/rhel10-testing-rpms/RPM-GPG-KEY
sudo curl -fsSL https://johngrimmreaper.github.io/rhel10-testing-rpms/repo/reaper-rhel10-testing-rhel-10-testing.repo -o /etc/yum.repos.d/reaper-rhel10-testing-rhel-10-testing.repo
sudo dnf makecache --refresh
```

RPM signatures: on; repository metadata signatures: on.

---

This README is generated automatically from the published repository snapshot.
