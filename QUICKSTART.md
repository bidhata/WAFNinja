# ⚡ WAFNinja Quick Start Guide

Get up and running with WAFNinja in 5 minutes!

## 🎯 What You'll Learn

- Install WAFNinja in BurpSuite
- Configure for maximum effectiveness
- Run your first WAF bypass
- View ML Database insights

---

## 📦 Installation (2 minutes)

### 1. Download Jython

```bash
wget https://repo1.maven.org/maven2/org/python/jython-standalone/2.7.3/jython-standalone-2.7.3.jar
```

### 2. Configure in BurpSuite

- `Extender` → `Options` → `Python Environment`
- Select the Jython JAR file

### 3. Install WAFNinja

```bash
git clone https://github.com/bidhata/WAFNinja.git
```

- `Extender` → `Extensions` → `Add`
- Select `WAFNinja.py`
- Click `Next`

✅ **Done!** Look for "WAFNinja v1.0" tab

---

## ⚙️ Configuration (1 minute)

### Go to WAFNinja Tab → Control Panel

Check these boxes:

- ✅ **Enable WAFNinja**
- ✅ **Auto Bypass**
- ✅ **ML Selection (Enhanced)**
- ✅ **Request Caching (90% faster)**
- ✅ **Advanced Fingerprinting**

---

## 🚀 First Bypass (2 minutes)

### 1. Set Up Proxy

- Configure browser to use Burp proxy (127.0.0.1:8080)
- Enable intercept in Burp

### 2. Browse Target Site

- Visit your authorized test target
- WAFNinja automatically detects WAF
- Watch console for activity:

```
[WAFNinja] WAF Detected: Cloudflare
[WAFNinja] Using DB recommendation: Unicode Normalization
[WAFNinja] ✓ Bypass successful! (Response: 200 OK)
```

### 3. Check Results

Go to **Statistics** tab to see:
- Total requests processed
- Success/failure rates
- Techniques used
- Response times

---

## 📊 View ML Insights

### Go to ML Database Tab

Click **"Refresh ML Stats"** to see:

```
=== ML DATABASE STATISTICS ===

Total Technique Attempts: 47
WAF Detections: 1
Success Rate: 93.6%

=== TOP TECHNIQUES ===
1. Unicode Normalization - Success: 98.5% (23 attempts)
2. Double Encoding - Success: 95.2% (12 attempts)
3. Header Injection - Success: 88.9% (9 attempts)
```

Click **"Export ML Data"** to save insights as JSON!

---

## 🎯 Pro Tips

### For Best Results

```python
# Let ML learn for 20+ requests before judging
# Check ML Database after each session
# Export data for analysis
# Adjust settings based on target
```

### Performance Modes

**🚀 Speed Mode** (Fast testing)
- ✅ Request Caching
- ✅ ML Selection
- ✅ Parallel Testing

**🥷 Stealth Mode** (Low profile)
- ✅ ML Selection only
- ❌ Parallel Testing
- Let ML learn slowly

**🎯 Maximum Bypass** (Best success rate)
- ✅ All features enabled
- ✅ Advanced Fingerprinting
- Let ML learn 50+ requests

---

## 🔥 Common Scenarios

### Scenario 1: Testing E-commerce Site

```bash
1. Enable Auto Bypass
2. Browse product pages
3. Add items to cart
4. Proceed to checkout
5. Check Statistics tab
6. Export ML data for report
```

### Scenario 2: API Testing

```bash
1. Configure Burp to intercept API calls
2. Enable ML Selection
3. Send API requests
4. Watch ML learn patterns
5. Check best techniques in ML Database
```

### Scenario 3: Bug Bounty Hunting

```bash
1. Enable all features
2. Let ML learn target patterns (20+ requests)
3. Check ML Database for best techniques
4. Focus on high-success techniques
5. Export data for submission
```

---

## 📈 Monitoring Progress

### Real-Time Monitoring

Watch the console for live updates:

```
[WAFNinja] Cache HIT - using Unicode Normalization
[WAFNinja] Applying technique: Double Encoding
[WAFNinja] ✓ Bypass successful!
```

### Statistics Dashboard

**Statistics Tab** shows:
- 📊 Total: 156 requests
- ✅ Passed: 148 (94.9%)
- ❌ Blocked: 8 (5.1%)
- ⚡ Avg Response: 1.2ms

### ML Database Insights

**ML Database Tab** shows:
- 🤖 Learning progress
- 🎯 Best techniques
- 📈 Success trends
- 💾 Exportable data

---

## 🛠️ Troubleshooting

### Extension Won't Load?

```bash
# Check Jython configuration
Extender → Options → Python Environment
# Should show: "Jython version: 2.7.3"

# Check console for errors
Extender → Extensions → Errors tab
```

### No Bypass Success?

```bash
# Let ML learn more (20+ requests)
# Enable Advanced Fingerprinting
# Check WAF was detected correctly
# Try different techniques manually
```

### Database Not Recording?

```bash
# Check write permissions
# Verify wafninja_ml.db file exists
# Check console for database errors
# Click "Refresh ML Stats" button
```

---

## 🎓 Next Steps

### Learn More

- 📚 Read full [README.md](README.md)
- 🔧 Check [INSTALLATION.md](INSTALLATION.md) for advanced setup
- 🤝 Read [CONTRIBUTING.md](CONTRIBUTING.md) to contribute
- 🔒 Review [SECURITY.md](SECURITY.md) for best practices

### Advanced Features

- Explore all 53 bypass techniques
- Customize ML learning parameters
- Create custom bypass techniques
- Integrate with automation tools

### Community

- ⭐ Star the repo on GitHub
- 🐛 Report bugs and issues
- 💡 Suggest new features
- 🤝 Contribute code

---

## 📞 Need Help?

- 📧 Email: me@krishnendu.com
- 🐛 Issues: [GitHub Issues](https://github.com/bidhata/WAFNinja/issues)
- 💬 Discuss: [GitHub Discussions](https://github.com/bidhata/WAFNinja/discussions)

---

## 🎉 Success Checklist

- [ ] Extension loaded successfully
- [ ] WAF detected automatically
- [ ] First bypass successful
- [ ] ML Database recording data
- [ ] Statistics showing results
- [ ] Exported ML data

**Congratulations! You're now a WAF Ninja! 🥷**

---

<div align="center">

### 🚀 Ready to Master WAF Bypass?

**[⬆ Back to Main README](README.md)**

**Made with 🔥 by [Krishnendu Paul](https://github.com/bidhata)**

[![GitHub stars](https://img.shields.io/github/stars/bidhata/WAFNinja?style=social)](https://github.com/bidhata/WAFNinja/stargazers)

</div>
