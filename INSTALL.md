# Installation Guide

## Container Configuration

Use the `HARBOR_ENCRYPTION_KEY` container environment variable as a base64-encoded 32-byte key for AES-256 encryption. This securely stores your harbor login password.

If you intend to run the CLI as a container, it is advised
to set the following environment variables and to create an alias
and append the alias to your .zshrc or .bashrc file

```shell
echo "export HARBOR_CLI_CONFIG=\$HOME/.config/harbor-cli" >> ~/.zshrc
echo "export HARBOR_ENCRYPTION_KEY=\$(cat <path_to_32bit_private_key_file> | base64)" >> ~/.zshrc
echo "alias harbor='docker run -ti --rm -v \$HARBOR_CLI_CONFIG:/root/.config/harbor-cli -e HARBOR_ENCRYPTION_KEY=\$HARBOR_ENCRYPTION_KEY registry.goharbor.io/harbor-cli/harbor-cli'" >> ~/.zshrc 
source ~/.zshrc # or restart your terminal
```

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

The repository is generated using Dagger (see `.dagger/apt.go`). Please refer to it for the exact repository structure and usage.


## Security

Harbor CLI provides attested binaries and artifacts to ensure integrity and authenticity.

Artifacts are signed using Cosign as part of the release process enabling verification of distributed binaries and container images.

SHA256 checksums are generated for all release artifacts allowing users to validate downloads.

Additionally, SBOMs (Software Bill of Materials) are generated for each release using Syft in CycloneDX format providing transparency into dependencies and build contents.

These features help ensure the integrity and trustworthiness of Harbor CLI artifacts.
