# Installation Guide

## Homebrew
```bash
brew install harbor-cli
```

Otherwise, you can download the binary from the [releases page](https://github.com/goharbor/harbor-cli/releases).

### Package based Installation

You can also install Harbor CLI using platform specific packages from the releases page.

#### Debian/Ubuntu(.deb)

> Replace `<version>` with the desired release version (e.g., v0.x.x).

```bash
wget https://github.com/goharbor/harbor-cli/releases/download/<version>/harbor-cli_<version>_linux_amd64.deb
sudo dpkg -i harbor-cli_<version>_linux_amd64.deb
```

#### Fedora/CentOS(.rpm)

> Replace `<version>` with the desired release version (e.g., v0.x.x).

```bash
wget https://github.com/goharbor/harbor-cli/releases/download/<version>/harbor-cli_<version>_linux_amd64.rpm
sudo rpm -i harbor-cli_<version>_linux_amd64.rpm
```

#### Alpine(.apk)

> Replace `<version>` with the desired release version (e.g., v0.x.x).

```bash
wget https://github.com/goharbor/harbor-cli/releases/download/<version>/harbor-cli_<version>_linux_amd64.apk
sudo apk add --allow-untrusted harbor-cli_<version>_linux_amd64.apk
```

#### APT repository

APT based installation is available via the project's gh-pages branch. Refer to the repository for more details.


## Security

Harbor CLI provides security features such as SBOM (Software Bill of Materials) and Cosign support for verifying artifacts. These help ensure the integrity and authenticity of distributed binaries.
