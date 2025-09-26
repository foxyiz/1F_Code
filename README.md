# FoXYiZ - Automated Testing Framework

FoXYiZ is a Python-based automated testing framework that supports multiple testing scenarios including web UI testing, API testing, and mathematical operations. The framework uses Selenium for web automation and provides a flexible configuration system for different test scenarios.

## Features

- **Multi-scenario Testing**: Supports web UI, API, and mathematical testing
- **Parallel Execution**: Multi-threaded test execution for faster results
- **Flexible Configuration**: JSON-based configuration system
- **Comprehensive Reporting**: HTML dashboards and CSV result files
- **Cross-platform**: Works on Windows, Linux, and macOS
- **Executable Build**: Can be compiled to standalone executable

## Project Structure

```
FoXYiZ/
├── fEngine.py          # Main engine for test execution
├── fStart.json         # Main configuration file
├── fRun.bat            # Windows batch script for setup and execution
├── requirements.txt    # Python dependencies
├── x/                  # Core action modules
│   ├── xActions.py     # Action definitions and implementations
│   └── xCapa.csv       # Capability definitions
├── y/                  # Test configurations (ignored by git)
│   ├── yPAD_NAME/      
│   │   ├── yPlans.csv  
│   │   ├── yActions.csv
│   │   ├── yDesigns.csv
│   └── yPAD.json

└── z/                  # Test results and reports (ignored by git)
    └── [timestamped folders with results]
```

## Prerequisites

- Python 3.8 or higher
- pip (Python package installer)
- Git (for version control)

## Installation

### 1. Clone the Repository

```bash
git clone https://github.com/foxyiz/1F_Code.git
cd FoXYiZ
```

### 2. Create Virtual Environment

**Windows:**
```bash
python -m venv venv
venv\Scripts\activate
```

**Linux/macOS:**
```bash
python3 -m venv venv
source venv/bin/activate
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

### 4. Verify Installation

```bash
python fEngine.py --help
```

## Usage

### Quick Start

1. **Activate virtual environment:**
   ```bash
   # Windows
   venv\Scripts\activate
   
   # Linux/macOS
   source venv/bin/activate
   ```

2. **Run tests using batch script (Windows):**
   ```bash
   fRun.bat
   ```

3. **Or run directly with Python:**
   ```bash
   python fEngine.py
   ```

### Configuration

The framework uses JSON configuration files located in the `y/` directory:

- **fStart.json**: Main configuration with thread count and timeout settings


### Test Execution

Tests are executed based on the configuration files and generate results in timestamped folders under the `z/` directory. Each execution creates:

- HTML dashboard reports
- CSV result files
- Screenshots (for UI tests)
- Error logs

## Development

### Adding New Test Scenarios

1. Create a new JSON configuration file in the `y/` directory
2. Define your test plans, actions, and designs in CSV format
3. Update `fStart.json` to include your new configuration
4. Run the tests to verify

## Dependencies

- **pandas**: Data manipulation and analysis
- **requests**: HTTP library for API testing
- **selenium**: Web browser automation
- **pyinstaller**: Creating standalone executables

## Configuration Examples

### Main Configuration (fStart.json)
```json
{
  "configs": ["y/FoXYiZ.json", "y/Math.json", "y/Mix.json"],
  "thread_count": 4,
  "timeout": 5
}
```

### Test Scenario Configuration
```json
{
  "input_files": {
    "yPlans": ["y/FoXYiZ/y1Plans.csv"],
    "yActions": ["y/FoXYiZ/y2Actions.csv"],
    "yDesigns": ["y/FoXYiZ/y3Designs.csv"]
  }
}
```

## Troubleshooting

### Common Issues

1. **Import Errors**: Ensure virtual environment is activated
2. **Selenium Issues**: Check if ChromeDriver is in PATH or update WebDriver
3. **Permission Errors**: Run as administrator on Windows if needed
4. **Memory Issues**: Reduce thread_count in configuration for large test suites

### Logs and Debugging

- Check `z/zLog.txt` for execution logs
- Review error files in result directories
- Use `--verbose` flag for detailed output

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test thoroughly
5. Submit a pull request


## Support

For issues and questions:
- Check the troubleshooting section
- Review log files in the `z/` directory
- Create an issue in the repository

---

**Note**: The `y/` and `z/` directories are ignored by git to keep the repository clean, but the folder structure is preserved with `.gitkeep` files.
