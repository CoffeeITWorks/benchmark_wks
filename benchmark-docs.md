# Workstation Benchmark Tool Documentation

## Overview
This Python-based benchmark tool performs automated performance testing of workstations, checking:
- Browser performance using Speedometer 3.0
- Network speed and latency
- Video processing capabilities

The script automatically generates a report and exits with a pass/fail status based on minimum requirements.

## Prerequisites

1. Python 3.7 or higher installed on the workstation
2. Chrome browser installed
3. Run the following command to install required packages:
   ```bash
   pip install selenium webdriver-manager speedtest-cli opencv-python
   ```

## Running the Benchmark

1. Copy the benchmark script to the workstation
2. Open a terminal/command prompt
3. Navigate to the script's directory
4. Run the script:
   ```bash
   python workstation_benchmark.py
   ```

## What to Expect

1. **Browser Test**
   - Opens Chrome browser
   - Loads Speedometer 3.0 benchmark
   - Takes approximately 3-5 minutes to complete
   - Minimum acceptable score: 10
   - Note: Keep the browser window visible during testing

2. **Network Test**
   - Tests download speed (minimum 50 Mbps)
   - Tests upload speed (minimum 10 Mbps)
   - Tests ping (maximum 50ms)
   - Takes 1-2 minutes to complete

3. **Video Performance Test**
   - Tests frame processing capability
   - Checks decode performance
   - Minimum requirements:
     - 30 FPS minimum
     - 0.1 seconds maximum decode time per frame
   - Takes about 30 seconds

## Understanding Results

- The script generates a JSON report file named `benchmark_report_YYYYMMDD_HHMMSS.json`
- Exit codes:
  - 0: All tests passed
  - 1: One or more tests failed
- Report includes detailed metrics for each test category

## Troubleshooting

1. **Browser Test Fails**
   - Verify Chrome is installed and up to date
   - Check if WebDriver is properly installed
   - Ensure the browser window remains visible

2. **Network Test Fails**
   - Verify network connection
   - Ensure no bandwidth-heavy processes are running
   - Try connecting via ethernet if on Wi-Fi

3. **Video Test Fails**
   - Check for GPU driver updates
   - Verify no resource-intensive applications are running
   - Ensure sufficient system memory is available

## Support Contacts

For issues with the benchmark tool:
1. First contact: Local IT Support
2. Escalation path: Infrastructure Team

## Maintenance

The script should be updated periodically to ensure:
- Security updates for dependencies
- Current browser versions are supported
- Performance thresholds remain appropriate

## Report Example

```json
{
  "timestamp": "2025-01-16T10:30:00",
  "tests": {
    "browser": {
      "speedometer_score": 15.2,
      "passed": true
    },
    "network": {
      "download_speed": 85.4,
      "upload_speed": 15.2,
      "ping": 25,
      "passed": true
    },
    "video": {
      "fps": 45.2,
      "decode_time": 0.05,
      "passed": true
    }
  },
  "overall_pass": true
}
```
