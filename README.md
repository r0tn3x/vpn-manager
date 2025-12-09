# VPN Manager

**Author:** `r0nt3x`

A beautiful and powerful OpenVPN manager for CTF platforms (HackTheBox, TryHackMe, etc.) with colored output, detailed status information, and easy configuration management.

![License](https://img.shields.io/badge/license-MIT-blue.svg)
![Shell](https://img.shields.io/badge/shell-bash-green.svg)
![Platform](https://img.shields.io/badge/platform-linux-lightgrey.svg)

## ✨ Features

- 🎨 **Beautiful colored output** with icons and formatting
- 🔌 **Easy VPN connection** with simple commands
- 📊 **Detailed status information** including:
  - Connection uptime
  - Network interfaces (tun0/tap0)
  - IP addresses
  - Traffic statistics (upload/download)
  - External IP detection
  - Routing information
- 📂 **Automatic config detection** from `~/VPN/` directory
- 🔄 **Smart connection switching** with confirmation prompts
- ⚠️ **Error handling** with helpful messages
- 🔍 **Case-insensitive** config name matching
- 🚀 **Fast and lightweight** - pure bash script

## 📋 Requirements

- Linux OS (Debian/Ubuntu/Arch/etc.)
- Bash shell
- OpenVPN
- bc (for calculations)
- curl (for IP detection)
- sudo privileges

## 🚀 Installation

### Quick Install

```bash
git clone https://github.com/r0nt3x/vpn-manager.git
cd vpn-manager
chmod +x install.sh
./install.sh
```

The installation script will:
1. Check and install dependencies (OpenVPN, bc, curl)
2. Create the VPN directory (`~/VPN/`)
3. Install the `vpn` command globally
4. Set up proper permissions

### Manual Install

```bash
# Copy the script
sudo cp vpn /usr/local/bin/vpn
sudo chmod +x /usr/local/bin/vpn

# Create VPN directory
mkdir -p ~/VPN

# Install dependencies
sudo apt install openvpn bc curl  # Debian/Ubuntu
```

## 📖 Usage

### Setup

1. Place your `.ovpn` configuration files in `~/VPN/`
   ```bash
   cp ~/Downloads/myconfig.ovpn ~/VPN/
   ```

2. Verify your configs are detected
   ```bash
   vpn --available
   ```

### Commands

#### Connect to VPN
```bash
vpn --dante-prolab    # Connect to dante-prolab.ovpn
vpn --thm             # Connect to thm.ovpn
vpn --htb             # Connect to htb.ovpn
```

#### Check Status
```bash
vpn --status          # Show detailed connection status
```

#### List Available Configs
```bash
vpn --available       # Show all .ovpn files in ~/VPN/
```

#### Disconnect
```bash
vpn --terminate       # Disconnect all VPN connections
```

#### Help
```bash
vpn --help           # Show usage information
```

## 🎯 Examples

<img width="595" height="536" alt="image" src="https://github.com/user-attachments/assets/b70e6286-b299-4122-a587-e8ce7dcf5003" />

<img width="593" height="341" alt="image" src="https://github.com/user-attachments/assets/d22ce1d8-f68d-4352-8ebe-0ebf56188e46" />

<img width="987" height="634" alt="image" src="https://github.com/user-attachments/assets/e02a1f9c-360a-485b-b7e8-8c15cbf05fda" />

<img width="566" height="214" alt="image" src="https://github.com/user-attachments/assets/0c43cae8-e44d-411b-8226-670d96500b2c" />


## 🔧 Configuration

### VPN Directory
- **Location:** `~/VPN/`
- **File format:** `<name>.ovpn`
- **Example:** `~/VPN/dante-prolab.ovpn`

### Logs and Files
- **Connection log:** `/tmp/vpn_manager.log`
- **PID file:** `/tmp/vpn_manager.pid`
- **Connection info:** `/tmp/vpn_connection.info`

## 💡 Pro Tips

1. **Add aliases to your shell** (~/.bashrc or ~/.zshrc):
   ```bash
   alias vstat='vpn --status'
   alias vlist='vpn --available'
   alias vkill='vpn --terminate'
   ```

2. **Monitor connection in real-time:**
   ```bash
   watch -n 2 vpn --status
   ```

3. **Quick check before work:**
   ```bash
   vpn --status && echo "Ready to hack!" || echo "Not connected"
   ```

## 🐛 Troubleshooting

### VPN not connecting?
- Verify OpenVPN is installed: `which openvpn`
- Check config file exists: `ls ~/VPN/*.ovpn`
- View logs: `cat /tmp/vpn_manager.log`

### No configs showing?
- Check directory: `ls -la ~/VPN/`
- Verify file extension: Files must end with `.ovpn`

### Permission denied?
- OpenVPN requires sudo privileges
- Make sure you can run: `sudo openvpn --version`


## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 👤 Author

**r0nt3x**

- GitHub: [@r0nt3x](https://github.com/r0nt3x)

## ⭐ Show Your Support

Give a ⭐️ if this project helped you!

## 📮 Feedback

If you have any feedback or suggestions, please open an issue on GitHub.

---

**Made with ❤️ by `r0nt3x`**
