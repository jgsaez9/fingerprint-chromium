# Building Chromium macOS x64

## Automatic Build via GitHub Actions

This repository includes a GitHub Actions workflow to build Chromium for macOS x64 architecture.

### Steps:

1. **Fork this repository** to your GitHub account
2. **Enable GitHub Actions** in your fork (if not already enabled)
3. **Trigger the build**:
   - Go to Actions tab in your forked repository
   - Select "Build Chromium macOS x64" workflow
   - Click "Run workflow"
   - Enter the Chromium version (default: 136.0.7103.113)
   - Click "Run workflow" button

### Build Process:

- **Runner**: Uses `macos-13` (Intel x64) instead of Apple Silicon
- **Duration**: ~2-4 hours depending on queue and compilation time
- **Output**: DMG file with Chromium.app built for x64 architecture

### Download Results:

After the build completes:
1. Go to the completed workflow run
2. Download the artifact named `chromium-macos-x64-[run-number]`
3. Extract the DMG file
4. Mount and install Chromium.app

### Features:

- ✅ Built for Intel x64 architecture
- ✅ All fingerprint modifications included
- ✅ ungoogled-chromium patches applied
- ✅ Version 136.0.7103.113 (or specified version)

### Usage:

```bash
# Run with fingerprint features
./Chromium.app/Contents/MacOS/Chromium --fingerprint=12345 --user-data-dir=/tmp/chromium-profile
```

### Troubleshooting:

- If build fails, check the Actions logs for specific error messages
- Large Chromium builds may occasionally timeout (6 hour limit)
- You can retry failed builds by re-running the workflow

### Manual Build (Alternative):

If you prefer to build locally, refer to the original ungoogled-chromium documentation and ensure you have all dependencies installed.