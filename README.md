# Test Release App

A Next.js application set up to test automated release scripts with GitHub integration.

## Setup

1. Install dependencies:
   ```bash
   npm install
   ```

2. Set up environment variables:
   ```bash
   cp env.example .env
   ```
   Then edit `.env` and add your OpenAI API key.

3. Install GitHub CLI (if not already installed):
   ```bash
   # macOS
   brew install gh
   
   # Or download from: https://cli.github.com/
   ```

4. Authenticate with GitHub:
   ```bash
   gh auth login
   ```

## Branches

- `main`: Production branch
- `staging`: Development branch for testing releases

## Release Process

The release script automatically:
1. Analyzes commits since the last release
2. Prompts for version bump type (major/minor/patch)
3. Generates release notes using OpenAI
4. Creates and pushes a git tag
5. Creates a GitHub release with the generated notes

### Usage

```bash
# Run from staging branch
npm run release
```

The script will prompt you to choose the version bump type and then handle the rest automatically.

## Testing the Release Script

1. Make some commits on the staging branch
2. Run `npm run release`
3. Choose your version bump type
4. The script will create a tag and GitHub release

## Requirements

- Node.js 18+
- Git
- GitHub CLI (`gh`)
- OpenAI API key
- GitHub repository with proper permissions