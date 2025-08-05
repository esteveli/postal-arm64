# Postal ARM64 Docker Images

This repository provides ARM64 Docker images for [Postal](https://github.com/postalserver/postal), an open-source mail delivery platform.

## Why This Repository Exists

The original Postal project has shown little interest in providing official ARM64 support despite community requests. This repository was created to fill that gap by automatically building ARM64 images from the upstream releases.

**Important:** These images are provided as-is, without any warranty or guarantee. This is a community effort driven by the need for ARM64 compatibility.

## Available Images

All images are publicly available at:
```
ghcr.io/esteveli/postal-arm64/postal:[tag]
```

### Tags
- `latest` - Latest stable release
- Specific version tags (e.g., `v2.1.0`) - Corresponding to upstream Postal releases

## Usage

### Docker Run
```bash
docker run -d \
  --name postal \
  -p 5000:5000 \
  ghcr.io/esteveli/postal-arm64/postal:latest
```

### Docker Compose
```yaml
version: '3.8'
services:
  postal:
    image: ghcr.io/esteveli/postal-arm64/postal:latest
    ports:
      - "5000:5000"
    # Add your Postal configuration here
```

## How It Works

This repository uses GitHub Actions to:

1. **Monitor** the upstream [postalserver/postal](https://github.com/postalserver/postal) repository for new releases
2. **Automatically build** ARM64 images when new tags are detected
3. **Publish** them to GitHub Container Registry
4. **Manual builds** can be triggered for specific tags if needed

The build process runs every 6 hours to check for new releases.

## Architecture Support

- ✅ ARM64 (linux/arm64)
- ❌ AMD64 (use official images from upstream)

## Disclaimer

- **No Warranty**: These images are provided without any warranty or guarantee
- **Community Effort**: This is not affiliated with the official Postal project
- **Use at Your Own Risk**: Always test thoroughly before using in production
- **No Support**: While we try to keep images updated, we cannot provide technical support

## Contributing

Feel free to open issues or submit pull requests if you encounter problems with the ARM64 builds.

## License

This repository follows the same license as the upstream Postal project. The Docker images contain the original Postal software and are subject to its licensing terms.

## Links

- [Original Postal Repository](https://github.com/postalserver/postal)
- [Postal Documentation](https://docs.postalserver.io/)
- [Docker Images](https://github.com/esteveli/postal-arm64/pkgs/container/postal)