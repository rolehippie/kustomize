# kustomize

[![Source Code](https://img.shields.io/badge/github-source%20code-blue?logo=github&logoColor=white)](https://github.com/rolehippie/kustomize)
[![General Workflow](https://github.com/rolehippie/kustomize/actions/workflows/general.yml/badge.svg)](https://github.com/rolehippie/kustomize/actions/workflows/general.yml)
[![Readme Workflow](https://github.com/rolehippie/kustomize/actions/workflows/docs.yml/badge.svg)](https://github.com/rolehippie/kustomize/actions/workflows/docs.yml)
[![Galaxy Workflow](https://github.com/rolehippie/kustomize/actions/workflows/galaxy.yml/badge.svg)](https://github.com/rolehippie/kustomize/actions/workflows/galaxy.yml)
[![License: Apache-2.0](https://img.shields.io/github/license/rolehippie/kustomize)](https://github.com/rolehippie/kustomize/blob/master/LICENSE)
[![Ansible Role](https://img.shields.io/badge/role-rolehippie.kustomize-blue)](https://galaxy.ansible.com/rolehippie/kustomize)

Ansible role to install kustomize kubernetes manifest processor.

## Sponsor

Building and improving this Ansible role have been sponsored by my current and previous employers like **[Cloudpunks GmbH](https://cloudpunks.de)** and **[Proact Deutschland GmbH](https://www.proact.eu)**.

## Table of content

- [Requirements](#requirements)
- [Default Variables](#default-variables)
  - [kustomize_core_arch](#kustomize_core_arch)
  - [kustomize_core_download](#kustomize_core_download)
  - [kustomize_core_version](#kustomize_core_version)
  - [kustomize_install_path](#kustomize_install_path)
  - [kustomize_khelm_arch](#kustomize_khelm_arch)
  - [kustomize_khelm_download](#kustomize_khelm_download)
  - [kustomize_khelm_enabled](#kustomize_khelm_enabled)
  - [kustomize_khelm_version](#kustomize_khelm_version)
  - [kustomize_ksops_arch](#kustomize_ksops_arch)
  - [kustomize_ksops_download](#kustomize_ksops_download)
  - [kustomize_ksops_enabled](#kustomize_ksops_enabled)
  - [kustomize_ksops_version](#kustomize_ksops_version)
- [Discovered Tags](#discovered-tags)
- [Dependencies](#dependencies)
- [License](#license)
- [Author](#author)

---

## Requirements

- Minimum Ansible version: `2.10`

## Default Variables

### kustomize_core_arch

Architecture for kustomize

#### Default value

```YAML
kustomize_core_arch: "{{ 'arm64' if ansible_architecture == 'aarch64' else 'amd64'
  }}"
```

### kustomize_core_download

URL to download kustomize from

#### Default value

```YAML
kustomize_core_download: https://github.com/kubernetes-sigs/kustomize/releases/download/kustomize%2Fv{{
  kustomize_core_version }}/kustomize_v{{ kustomize_core_version }}_linux_{{ kustomize_core_arch
  }}.tar.gz
```

### kustomize_core_version

Version of kustomize to install

#### Default value

```YAML
kustomize_core_version: 5.1.1
```

### kustomize_install_path

Path to install the binaries

#### Default value

```YAML
kustomize_install_path: /usr/bin
```

### kustomize_khelm_arch

Architecture for khelm

#### Default value

```YAML
kustomize_khelm_arch: "{{ 'arm64' if ansible_architecture == 'aarch64' else 'amd64'
  }}"
```

### kustomize_khelm_download

URL to download khelm from

#### Default value

```YAML
kustomize_khelm_download: https://github.com/mgoltzsche/khelm/releases/download/v{{
  kustomize_khelm_version }}/khelm-linux-{{ kustomize_khelm_arch }}
```

### kustomize_khelm_enabled

Enable installation of khelm

#### Default value

```YAML
kustomize_khelm_enabled: true
```

### kustomize_khelm_version

Version of khelm to install

#### Default value

```YAML
kustomize_khelm_version: 2.3.1
```

### kustomize_ksops_arch

Architecture for ksops

#### Default value

```YAML
kustomize_ksops_arch: "{{ 'arm64' if ansible_architecture == 'aarch64' else 'x86_64'
  }}"
```

### kustomize_ksops_download

URL to download ksops from

#### Default value

```YAML
kustomize_ksops_download: https://github.com/viaduct-ai/kustomize-sops/releases/download/v{{
  kustomize_ksops_version }}/ksops_{{ kustomize_ksops_version }}_Linux_{{ kustomize_ksops_arch
  }}.tar.gz
```

### kustomize_ksops_enabled

Enable installation of ksops

#### Default value

```YAML
kustomize_ksops_enabled: true
```

### kustomize_ksops_version

Version of ksops to install

#### Default value

```YAML
kustomize_ksops_version: 4.2.2
```

## Discovered Tags

**_kustomize_**


## Dependencies

- None

## License

Apache-2.0

## Author

[Thomas Boerger](https://github.com/tboerger)
