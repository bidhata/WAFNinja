# 🚀 WAFNinja Installation Guide

Complete step-by-step installation guide for WAFNinja.

## 📋 Table of Contents

- [Prerequisites](#prerequisites)
- [Quick Installation](#quick-installation)
- [Detailed Installation](#detailed-installation)
- [Verification](#verification)
- [Troubleshooting](#troubleshooting)
- [Uninstallation](#uninstallation)

---

## Prerequisites

### Required Software

| Software | Version | Purpose |
|----------|---------|---------|
| **BurpSuite** | Community or Pro | Extension platform |
| **Jython** | 2.7.3+ | Python runtime for Burp |
| **Python** | 2.7+ | For standalone testing |

### System Requirements

- **OS**: Windows, macOS, or Linux
- **RAM**: 2GB minimum, 4GB recommended
- **Disk**: 100MB free space
- **Java**: JRE 8+ (for BurpSuite)

---

## Quick Installation

### 🎯 5-Minute Setup

```bash
# 1. Download Jython
wget https://repo1.maven.org/maven2/org/python/jython-standalone/2.7.3/jython-standalone-2.7.3.jar

# 2. Clone WAFNinja
git clone https://github.com/bidhata/WAFNinja.git
cd WAFNinja

# 3. Configure in BurpSuite
# - Extender → Options → Python Environment
# - Select Jython JAR file
# - Extender → Extensions → Add
# - Select WAFNinja.py
# - Done! ✅
```

---

## Detailed Installation

### Step 1: Install BurpSuite

#### Option A: Download from PortSwigger

1. Visit [PortSwigger Downloads](https://portswigger.net/burp/releases)
2. Download BurpSuite Community or Professional
3. Install following the installer instructions
4. Launch BurpSuite to verify installation

#### Option B: Package Manager (Linux)

```bash
# Debian/Ubuntu
sudo apt-get update
sudo apt-get install burpsuite

# Arch Linux
yay -S burpsuite

# Fedora
sudo dnf install burpsuite
```

### Step 2: Download Jython

#### Option A: Direct Download

```bash
# Download Jython Standalone JAR
wget https://repo1.maven.org/maven2/org/python/jython-standalone/2.7.3/jython-standalone-2.7.3.jar

# Or using curl
curl -O https://repo1.maven.org/maven2/org/python/jython-standalone/2.7.3/jython-standalone-2.7.3.jar
```

#### Option B: Manual Download

1. Visit [Jython Downloads](https://www.jython.org/download)
2. Download `jython-standalone-2.7.3.jar`
3. Save to a known location (e.g., `~/jython/`)

### Step 3: Configure Jython in BurpSuite

1. **Open BurpSuite**
   ```bash
   java -jar burpsuite.jar
   # Or launch from applications menu
   ```

2. **Navigate to Extender Options**
   - Click `Extender` tab
   - Click `Options` sub-tab
   - Find `Python Environment` section

3. **Set Jython Location**
   - Click `Select file...` button
   - Navigate to downloaded `jython-standalone-2.7.3.jar`
   - Select the file
   - Click `Open`

4. **Verify Configuration**
   - You should see: "Jython version: 2.7.3"
   - Status should show: "Loaded successfully"

### Step 4: Download WAFNinja

#### Option A: Git Clone (Recommended)

```bash
# Clone repository
git clone https://github.com/bidhata/WAFNinja.git

# Navigate to directory
cd WAFNinja

# Verify files
ls -la
# Should see: WAFNinja.py, README.md, LICENSE, etc.
```

#### Option B: Download ZIP

1. Visit [WAFNinja GitHub](https://github.com/bidhata/WAFNinja)
2. Click `Code` → `Download ZIP`
3. Extract ZIP file
4. Navigate to extracted folder

### Step 5: Load Extension in BurpSuite

1. **Open Extensions Tab**
   - Click `Extender` tab
   - Click `Extensions` sub-tab

2. **Add Extension**
   - Click `Add` button
   - Extension Details dialog opens

3. **Configure Extension**
   - **Extension type**: Select `Python`
   - **Extension file**: Click `Select file...`
   - Navigate to `WAFNinja.py`
   - Select the file
   - Click `Open`

4. **Load Extension**
   - Click `Next` button
   - Extension will load (may take 5-10 seconds)
   - Watch console for loading messages

5. **Verify Loading**
   - Check for success messages in console:
     ```
     [WAFNinja] Starting v1.0 with all enhancements...
     [WAFNinja] ML Database initialized: wafninja_ml.db
     [WAFNinja] v1.0 loaded successfully!
     ```
   - Look for `WAFNinja v1.0` tab in main window

---

## Verification

### ✅ Installation Checklist

- [ ] BurpSuite launches without errors
- [ ] Jython configured and loaded
- [ ] WAFNinja extension loaded successfully
- [ ] "WAFNinja v1.0" tab visible
- [ ] Console shows success messages
- [ ] Database file created (wafninja_ml.db)

### 🧪 Test Installation

1. **Open WAFNinja Tab**
   - Click `WAFNinja v1.0` tab
   - Should see 4 sub-tabs: Control, Statistics, ML Database, Advanced

2. **Enable Extension**
   - Go to `Control` tab
   - Check ✅ `Enable WAFNinja`
   - Should see no errors

3. **Test Basic Functionality**
   - Enable `Auto Bypass`
   - Send a test request through Burp Proxy
   - Check console for activity
   - Verify ML Database records data

4. **Check ML Database**
   - Go to `ML Database` tab
   - Click `Refresh ML Stats`
   - Should see statistics (may be 0 initially)

---

## Troubleshooting

### Common Issues

#### Issue 1: Extension Won't Load

**Symptoms**: Error when loading extension, no WAFNinja tab

**Solutions**:
```bash
# Check Jython is configured
# Extender → Options → Python Environment
# Should show: "Jython version: 2.7.3"

# Check Python syntax
python -m py_compile WAFNinja.py

# Check console for error messages
# Look in Extender → Extensions → Errors tab

# Try reloading extension
# Extender → Extensions → Select WAFNinja → Remove
# Then add again
```

#### Issue 2: Jython Not Found

**Symptoms**: "Python environment not configured" error

**Solutions**:
```bash
# Re-download Jython
wget https://repo1.maven.org/maven2/org/python/jython-standalone/2.7.3/jython-standalone-2.7.3.jar

# Verify file integrity
ls -lh jython-standalone-2.7.3.jar
# Should be ~40MB

# Reconfigure in BurpSuite
# Extender → Options → Python Environment → Select file
```

#### Issue 3: Database Not Created

**Symptoms**: No wafninja_ml.db file, ML Database tab empty

**Solutions**:
```bash
# Check write permissions
ls -la
# Should have write permission in directory

# Check console for errors
# Look for database-related error messages

# Manually create database (if needed)
# Extension will auto-create on next request

# Verify SQLite available
python -c "import sqlite3; print('SQLite OK')"
```

#### Issue 4: High Memory Usage

**Symptoms**: BurpSuite using excessive memory

**Solutions**:
```python
# Reduce cache size in WAFNinja.py
# Line ~1870: TechniqueCache(max_size=500, ttl=1800)

# Clear cache regularly
# Advanced tab → Clear Cache button

# Restart BurpSuite periodically
```

#### Issue 5: Extension Crashes

**Symptoms**: Extension stops working, errors in console

**Solutions**:
```bash
# Check circuit breaker status
# Advanced tab → Reset Circuit Breaker

# Check console for stack traces
# Report issues to GitHub

# Reload extension
# Extender → Extensions → Remove → Add again
```

### Debug Mode

Enable verbose logging:

```python
# In WAFNinja.py, add at top of registerExtenderCallbacks():
import sys
sys.stderr.write("[DEBUG] Extension loading...\n")

# Add debug prints throughout code:
print("[DEBUG] Current state: " + str(self._stats))
```

### Getting Help

If issues persist:

1. **Check Console**: Look for error messages
2. **Check Logs**: Review BurpSuite logs
3. **Search Issues**: [GitHub Issues](https://github.com/bidhata/WAFNinja/issues)
4. **Ask Community**: [GitHub Discussions](https://github.com/bidhata/WAFNinja/discussions)
5. **Email Support**: me@krishnendu.com

---

## Uninstallation

### Remove Extension

1. **In BurpSuite**
   - Go to `Extender` → `Extensions`
   - Select `WAFNinja v1.0`
   - Click `Remove` button
   - Confirm removal

2. **Clean Up Files**
   ```bash
   # Remove database
   rm wafninja_ml.db
   
   # Remove exported data
   rm wafninja_ml_export.json
   
   # Remove extension files (optional)
   cd ..
   rm -rf WAFNinja/
   ```

3. **Remove Jython (Optional)**
   ```bash
   # If no longer needed
   rm jython-standalone-2.7.3.jar
   ```

---

## Advanced Configuration

### Custom Database Location

```python
# In WAFNinja.py, line ~1868:
self._ml_database = MLDatabase(db_path="/custom/path/wafninja.db")
```

### Performance Tuning

```python
# Cache settings (line ~1870)
self._technique_cache = TechniqueCache(
    max_size=2000,  # Increase for more caching
    ttl=7200        # 2 hours TTL
)

# Circuit breaker (line ~1871)
self._circuit_breaker = CircuitBreaker(
    failure_threshold=10,  # More tolerant
    timeout=120            # Longer timeout
)

# Parallel engine (line ~1880)
ParallelTechniqueEngine(max_workers=10)  # More threads
```

### Custom Techniques

```python
# Add to _load_bypass_techniques() method:
{'name': 'My Custom Technique', 'complexity': 3}

# Implement in _apply_technique_to_request():
if technique['name'] == 'My Custom Technique':
    # Your implementation
    pass
```

---

## Platform-Specific Notes

### Windows

```powershell
# Use PowerShell or Command Prompt
# Download Jython
Invoke-WebRequest -Uri "https://repo1.maven.org/maven2/org/python/jython-standalone/2.7.3/jython-standalone-2.7.3.jar" -OutFile "jython-standalone-2.7.3.jar"

# Clone WAFNinja
git clone https://github.com/bidhata/WAFNinja.git
```

### macOS

```bash
# Install BurpSuite via Homebrew
brew install --cask burp-suite

# Download Jython
curl -O https://repo1.maven.org/maven2/org/python/jython-standalone/2.7.3/jython-standalone-2.7.3.jar

# Clone WAFNinja
git clone https://github.com/bidhata/WAFNinja.git
```

### Linux

```bash
# Install dependencies
sudo apt-get update
sudo apt-get install default-jre git

# Download Jython
wget https://repo1.maven.org/maven2/org/python/jython-standalone/2.7.3/jython-standalone-2.7.3.jar

# Clone WAFNinja
git clone https://github.com/bidhata/WAFNinja.git
```

---

## Next Steps

After installation:

1. **Read Documentation**: Check [README.md](README.md)
2. **Configure Settings**: Customize in Control tab
3. **Start Testing**: Enable Auto Bypass and test
4. **Monitor ML Database**: Watch learning progress
5. **Export Data**: Analyze results

---

## 📞 Support

Need help? We're here for you!

- 📧 **Email**: me@krishnendu.com
- 🐛 **Issues**: [GitHub Issues](https://github.com/bidhata/WAFNinja/issues)
- 💬 **Discussions**: [GitHub Discussions](https://github.com/bidhata/WAFNinja/discussions)
- 📚 **Documentation**: [README.md](README.md)

---

**Installation complete! Happy bypassing! 🥷**
