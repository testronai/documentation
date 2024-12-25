# Troubleshooting Guide

## Common Issues and Solutions

### Extension Issues

#### Extension Not Loading
**Symptoms:**
- Extension icon is grayed out
- Extension not appearing in Chrome
- "Error loading extension" message

**Solutions:**
1. Verify Chrome version (88+ required)
2. Check extension installation:
   ```bash
   1. Open chrome://extensions/
   2. Locate Testron
   3. Verify "Enabled" is checked
   4. Click "Reload" if needed
   ```
3. Reinstall extension if problems persist

#### Element Inspector Not Working
**Symptoms:**
- Inspector not highlighting elements
- Cannot select page elements
- Inspector freezes

**Solutions:**
1. Refresh the page
2. Check console for errors:
   ```bash
   1. Open DevTools (F12)
   2. Check Console tab
   3. Look for inspector-related errors
   ```
3. Ensure page is fully loaded
4. Disable other similar extensions temporarily

### AI Provider Issues

#### API Connection Failures
**Symptoms:**
- "Cannot connect to AI provider" error
- Timeout errors
- Authentication failures
- 529 "Overloaded" error (Claude specific)

**Solutions:**
1. Verify API key:
   ```javascript
   // Check API key format
   Claude: "sk-ant-xxx..."
   OpenAI: "sk-xxx..."
   Groq: "gsk_xxx..."
   ```
2. Check provider status pages
3. Verify internet connection
4. Try alternative provider

#### Claude API Overload Error
**Symptoms:**
- 529 error with message "Overloaded"
- Request timeouts
- Slow response times

**Solutions:**
1. Immediate Actions:
   - Wait a few minutes and retry
   - Switch to another provider temporarily:
     ```bash
     # Alternative providers:
     - Groq (Free tier available)
     - OpenAI
     - Ollama (Local, completely free)
     ```
2. Long-term Solutions:
   - Use Ollama as fallback for development/testing
   - Implement automatic provider failover
   - Schedule high-volume testing during off-peak hours

#### Ollama Connection Issues
**Symptoms:**
- Cannot connect to Ollama
- Model loading failures
- CORS errors
- localhost:11434 not accessible

**Solutions:**
1. Check Ollama service:
   ```bash
   # Mac/Linux
   ps aux | grep ollama
   
   # Windows
   tasklist | findstr ollama
   ```
2. Verify CORS settings:
   ```bash
   # Mac/Linux
   OLLAMA_ORIGINS='chrome-extension://*' ollama serve
   
   # Windows
   set OLLAMA_ORIGINS=chrome-extension://*
   ollama serve
   ```
3. Check model installation:
   ```bash
   ollama list
   ```
4. Verify localhost access:
   ```bash
   # Test Ollama API
   curl http://localhost:11434/api/tags
   ```

#### Cost Management Issues
**Symptoms:**
- Incorrect cost calculations
- Missing usage data
- Reset failures
- Unexpected token usage

**Solutions:**
1. Review usage logs
2. Reset counters if needed
3. Verify provider pricing
4. Check token calculations
5. Cost optimization strategies:
   ```bash
   # Free alternatives:
   1. Use Groq's free tier
   2. Switch to Ollama for testing
   3. Enable token usage warnings
   4. Set conservative thresholds
   ```

#### Token Usage Warnings
**Symptoms:**
- Frequent token limit warnings
- Cost threshold alerts
- Generation failures

**Solutions:**
1. Adjust token limits in settings
2. Monitor usage patterns
3. Consider upgrading plan
4. Use local Ollama option

### Framework Generation Issues

#### Playwright Generation Errors
**Symptoms:**
- Invalid TypeScript code
- Missing dependencies
- Selector errors

**Solutions:**
1. Update Playwright installation:
   ```bash
   npm install -g @playwright/test
   npx playwright install
   ```
2. Verify TypeScript configuration
3. Check element selectors
4. Review generated code structure

#### Cypress Generation Issues
**Symptoms:**
- Syntax errors
- Command failures
- Configuration problems

**Solutions:**
1. Update Cypress:
   ```bash
   npm install cypress@latest
   npx cypress verify
   ```
2. Check Cypress configuration
3. Verify test structure
4. Review selector strategy

#### Selenium Java Issues
**Symptoms:**
- Java compilation errors
- WebDriver connection issues
- Page Object errors

**Solutions:**
1. Update dependencies:
   ```bash
   # Update WebDriver
   brew upgrade chromedriver
   
   # Update Selenium
   brew upgrade selenium-server
   ```
2. Check Java version compatibility
3. Verify WebDriver setup
4. Review Page Object structure

### Local LLM Issues

#### Ollama Connection Problems
**Symptoms:**
- Cannot connect to Ollama
- Model loading failures
- CORS errors

**Solutions:**
1. Check Ollama service:
   ```bash
   # Mac/Linux
   ps aux | grep ollama
   
   # Windows
   tasklist | findstr ollama
   ```
2. Verify CORS settings:
   ```bash
   # Mac/Linux
   OLLAMA_ORIGINS='chrome-extension://*' ollama serve
   
   # Windows
   set OLLAMA_ORIGINS=chrome-extension://*
   ollama serve
   ```
3. Check model installation:
   ```bash
   ollama list
   ```

#### Performance Issues
**Symptoms:**
- Slow response times
- High CPU usage
- Memory warnings

**Solutions:**
1. Check system resources
2. Optimize model settings
3. Clear cache if needed
4. Consider hardware requirements

### Cost Management Issues

#### Usage Tracking Problems
**Symptoms:**
- Incorrect cost calculations
- Missing usage data
- Reset failures

**Solutions:**
1. Review usage logs
2. Reset counters if needed
3. Verify provider pricing
4. Check token calculations

## Diagnostic Tools

### Built-in Diagnostics
1. Extension health check
2. API connection test
3. Framework compatibility check
4. Resource usage monitor

### Logging Levels
```javascript
// Available log levels
DEBUG   // Detailed debugging information
INFO    // General operational information
WARN    // Warning messages for potential issues
ERROR   // Error messages for serious problems
FATAL   // Critical errors requiring immediate attention
```

### Debug Mode
```bash
# Enable debug mode
1. Open extension settings
2. Enable "Debug Mode"
3. Check DevTools console
4. Review debug logs
```

## Error Messages Reference

### Common Error Codes
| Code | Description | Solution |
|------|-------------|----------|
| E001 | API Connection Failed | Check API key and internet connection |
| E002 | Token Limit Exceeded | Adjust usage settings or upgrade plan |
| E003 | Model Loading Error | Verify model installation and requirements |
| E004 | Generation Failed | Check input parameters and try again |
| E005 | Framework Error | Update framework installation |

### Error Categories
1. Connection Errors
2. Authentication Errors
3. Generation Errors
4. Framework Errors
5. Resource Errors

## Performance Optimization

### Memory Management
- Clear extension cache
- Monitor memory usage
- Close unused tabs
- Restart browser if needed

### Response Time Optimization
- Use appropriate models
- Optimize selectors
- Cache common operations
- Monitor network latency

## Getting Additional Help

1. Check [Documentation](README.md)
2. Contact (Via Email:`testronai.com@gmail.com`)