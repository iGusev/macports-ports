# MacPorts Ports Repository

Local MacPorts ports repository for [GLF](https://github.com/igusev/glf) - GitLab Fuzzy Finder.

## Usage

### Add this repository as a local port source

```bash
# Clone this repository
git clone https://github.com/igusev/macports-ports.git
cd macports-ports

# Add as a local port source (requires sudo)
sudo bash -c "echo 'file://$(pwd)' >> /opt/local/etc/macports/sources.conf"

# Update MacPorts index
sudo port sync
```

### Install GLF

```bash
sudo port install glf
```

### Update GLF

```bash
sudo port selfupdate
sudo port upgrade glf
```

### Uninstall GLF

```bash
sudo port uninstall glf
```

## Available Ports

- **glf** - Fast CLI tool for instant fuzzy search across self-hosted GitLab projects

## Repository Structure

```
macports-ports/
└── devel/
    └── glf/
        └── Portfile
```

## Requirements

- macOS with MacPorts installed
- Go 1.23 or later (automatically installed by MacPorts if needed)

## Updating the Port

When a new version of GLF is released:

1. Update the version in `devel/glf/Portfile`
2. Download the new source tarball and calculate checksums:
   ```bash
   curl -L -o glf-VERSION.tar.gz https://github.com/igusev/glf/archive/refs/tags/vVERSION.tar.gz
   openssl dgst -rmd160 glf-VERSION.tar.gz
   openssl dgst -sha256 glf-VERSION.tar.gz
   ls -l glf-VERSION.tar.gz | awk '{print $5}'
   ```
3. Update checksums in Portfile
4. Commit and push changes
5. Users run `sudo port sync && sudo port upgrade glf`

## License

MIT License - see [LICENSE](LICENSE) file for details.

## Support

For issues with:
- **GLF tool itself**: [GLF Issues](https://github.com/igusev/glf/issues)
- **MacPorts port**: [MacPorts Issues](https://github.com/igusev/macports-ports/issues)
