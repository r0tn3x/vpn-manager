# Contributing to VPN Manager

First off, thank you for considering contributing to VPN Manager! 🎉

## How Can I Contribute?

### Reporting Bugs

Before creating bug reports, please check existing issues. When creating a bug report, include:

- **Use a clear and descriptive title**
- **Describe the exact steps to reproduce the problem**
- **Provide specific examples**
- **Describe the behavior you observed and what you expected**
- **Include screenshots if relevant**
- **Include your environment details:**
  - OS and version
  - Bash version (`bash --version`)
  - OpenVPN version (`openvpn --version`)

### Suggesting Enhancements

Enhancement suggestions are tracked as GitHub issues. When creating an enhancement suggestion, include:

- **Use a clear and descriptive title**
- **Provide a detailed description of the proposed enhancement**
- **Explain why this enhancement would be useful**
- **List some examples of how it would be used**

### Pull Requests

1. Fork the repo and create your branch from `main`
2. Make your changes
3. Test your changes thoroughly
4. Update documentation if needed
5. Write a clear commit message
6. Submit a pull request

## Development Setup

```bash
# Clone your fork
git clone https://github.com/YOUR-USERNAME/vpn-manager.git
cd vpn-manager

# Make changes
# Test locally
./vpn --help

# Test installation
./install.sh
```

## Testing

Before submitting a pull request, test:

1. All commands work correctly:
   - `vpn --help`
   - `vpn --available`
   - `vpn --status`
   - `vpn --terminate`
   - Connection commands

2. Error handling:
   - Missing dependencies
   - Invalid config names
   - No configs in directory

3. Edge cases:
   - Empty VPN directory
   - Multiple simultaneous connections
   - Network interface detection

## Coding Conventions

- Use 4 spaces for indentation
- Keep functions focused and single-purpose
- Add comments for complex logic
- Use meaningful variable names
- Follow existing code style
- Use shellcheck for linting

## Commit Message Guidelines

- Use the present tense ("Add feature" not "Added feature")
- Use the imperative mood ("Move cursor to..." not "Moves cursor to...")
- Limit the first line to 72 characters
- Reference issues and pull requests when relevant

Examples:
```
Add support for WireGuard configs
Fix status display for multiple interfaces
Update README with troubleshooting section
```

## Code of Conduct

- Be respectful and inclusive
- Accept constructive criticism
- Focus on what's best for the community
- Show empathy towards other community members

## Questions?

Feel free to open an issue with your question!

---

**Thank you for contributing! 🚀**
