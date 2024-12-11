# MQTT Inspector

A desktop application for real-time monitoring and inspection of MQTT messages with automatic device-based grouping.

![MQTT Inspector Screenshot](/assets/MainWindowScreenshot.png)

## Features

- 🔌 Support for MQTT and WebSocket protocols
- 📊 Automatic device-based grouping
- 🔄 Real-time data updates
- 📝 Message counter
- 🔐 Username/password authentication support
- 💻 Cross-platform support (Windows, macOS, Linux)
- 🎨 Modern and user-friendly interface
- 📈 Message history tracking
- 🔍 Real-time message inspection
- 🌐 Multi-broker support

## Installation

### For Users

1. Download the appropriate version for your operating system from [Releases](https://github.com/ysfsmet/mqtt-inspector/releases):
   - Windows: `MQTT Inspector Setup.exe`
   - macOS: `MQTT Inspector.dmg`
   - Linux: `mqtt-inspector.AppImage` or `mqtt-inspector.deb`

2. Run the downloaded file:
   - Windows: Run the setup file and follow installation steps
   - macOS: Open the DMG file and drag the application to Applications folder
   - Linux: Make the AppImage executable and run it, or install the .deb package

### For Developers

To develop the project locally:

1. Install requirements:
   - Node.js (v14 or higher)
   - npm (v6 or higher)
   - Git

2. Clone the project:
```bash
git clone https://github.com/ysfsmet/mqtt-inspector.git
cd mqtt-inspector
```

3. Install dependencies:
```bash
npm install
```

4. Start the application:
```bash
npm start
```

## Usage

### Connection Settings

1. Enter broker connection details:
   - Protocol: MQTT (1883) or WebSocket (9001)
   - Broker Address: IP address or hostname
   - Port: Automatically filled based on protocol
   - Username/Password (optional)

2. Click "Connect" button

### Topic Structure

The application supports the following topic structure:
```
sysmanager/[Device Name]/[Variable Name]
```

Example:
```
sysmanager/Device1/Temperature
sysmanager/Device1/Pressure
sysmanager/Device2/Speed
```

### Interface Features

- **Connection Status**: Displayed in the top right corner
- **Device Groups**: Separate panel for each device
- **Variable List**: For each variable:
  - Message counter (left)
  - Variable name (center)
  - Latest value (right)

## Development

### Project Structure

```
mqtt-inspector/
├── assets/              # Icons and visual assets
│   ├── icon.ico        # Windows icon
│   ├── icon.icns       # macOS icon
│   └── icon.png        # Linux icon
├── src/                # Source files
│   ├── main.js        # Electron main process
│   └── index.html     # Main application window
├── package.json       # Project configuration
└── README.md         # Documentation
```

### Building

For Windows:
```bash
npm run build:win
```

For macOS:
```bash
npm run build:mac
```

For Linux:
```bash
npm run build:linux
```

For all platforms:
```bash
npm run build
```

### Testing

You can use Mosquitto for testing MQTT broker connections:

1. Install Mosquitto:
   - Windows: [Mosquitto Download Page](https://mosquitto.org/download/)
   - macOS: `brew install mosquitto`
   - Linux: `sudo apt-get install mosquitto`

2. Send test message:
```bash
mosquitto_pub -t "sysmanager/TestDevice/Temperature" -m "25.5"
```

## Troubleshooting

1. **Connection Error**
   - Verify broker address and port
   - Check firewall settings
   - Confirm broker is running

2. **WebSocket Connection Error**
   - Verify WebSocket support is enabled in broker
   - Check correct port usage

3. **Application Launch Issues**
   - Verify Node.js version
   - Delete node_modules folder and run `npm install`

## Contributing

1. Fork the project
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

### Development Guidelines

- Follow the existing code style
- Add comments for complex logic
- Update documentation for new features
- Add appropriate error handling
- Test on all supported platforms

## Security

- Always use secure connections in production
- Regularly update dependencies
- Use strong passwords for MQTT authentication
- Enable SSL/TLS when possible
- Be cautious with topic permissions

## Roadmap

- [ ] Add SSL/TLS support
- [ ] Implement message filtering
- [ ] Add data visualization
- [ ] Support for custom topic patterns
- [ ] Message payload formatting
- [ ] Export data functionality
- [ ] Dark mode support
- [ ] Configurable refresh rates

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments

- [Electron](https://www.electronjs.org/)
- [MQTT.js](https://github.com/mqttjs/MQTT.js)
- [electron-builder](https://www.electron.build/)

## Contact

Project Maintainer - [@ysfsmet](https://x.com/ysfsmet)

Project Link: [https://github.com/ysfsmet/mqtt-inspector](https://github.com/ysfsmet/mqtt-inspector)

## Changelog

### Version 1.0.0 (2024-12-11)
- Initial release
- Basic MQTT monitoring functionality
- Cross-platform support
- Real-time message inspection
- Automatic device grouping

## Support

For support, email mqtt-inspector@example.com or open an issue on GitHub.