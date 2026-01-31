# Swift Translator Test Automation

## Student Information
- **Registration Number:** IT23432734
- **Course:** IT3040 - ITPM
- **Assignment:** Assignment 1 - Semester 2

## Project Overview
Automated testing suite for [Swift Translator](https://www.swifttranslator.com/) - a Singlish to Sinhala text converter. 

- **Node.js** (v14 or higher)
- **npm** (Node Package Manager)

## Installation

### 1. Clone the Repository
```bash
git clone https://github.com/SuchinthaHettiarachchi/itpm-assignment-1-swift-translator-automation.git
cd itpm-assignment-1-swift-translator-automation
```

### 2. Install Dependencies
```bash
npm install
```

This will install:
- Playwright Test framework
- Chromium browser binaries
- All required dependencies

### 3. Install Playwright Browsers (if needed)
```bash
npx playwright install
```

## Running Tests

### Run All Tests
```bash
npx playwright test
```

### Run Tests with Specific Browser
```bash
npx playwright test --project=chromium
```

### Run Tests in Parallel (2 workers)
```bash
npx playwright test --workers=2
```

### Run Tests in Headed Mode (visible browser)
```bash
npx playwright test --headed
```

### Run Specific Test File
```bash
npx playwright test tests/swifttranslator.spec.js
```

### Run with All Options Combined
```bash
npx playwright test tests/swifttranslator.spec.js --project=chromium --headed --workers=2
```

## View Test Results

### HTML Report
After test execution, view the HTML report:
```bash
npx playwright show-report
```

The report will open automatically in your browser at `http://localhost:9323`

## Project Structure
```
playwright-tests/
├── tests/
│   ├── swifttranslator.spec.js     # Main test specification file
│   └── test-data.json              # Test case data and expected outputs
├── test-results/                   # Test execution results (auto-generated)
├── playwright-report/              # HTML reports (auto-generated)
├── node_modules/                   # Dependencies (auto-generated)
├── package.json                    # Project dependencies and scripts
├── package-lock.json               # Locked dependency versions
├── playwright.config.js            # Playwright configuration
├── .gitignore                      # Git ignore rules
└── README.md                       # This file
```

## Test Execution Details

## Test Data Format
Test cases are defined in `tests/test-data.json` with the following structure:
```json
{
  "id": "Pos_Fun_0001",
  "type": "pos",
  "input": "mama haemadhaama bath kanavaa",
  "expected": "මම හැමදාම බත් කනවා",
  "keywords": ["මම", "හැමදාම", "බත්", "කනවා"]
}
```

## Test Validation Strategy
- ## Positive Tests: Validate correct translation with keyword matching (60% threshold for partial matches)
- ## Negative Tests: Verify system handles invalid/edge-case inputs appropriately
- ## UI Tests: Validate real-time translation behavior and interface responsiveness

## Test Results
## All 36 tests passing successfully

Execution time: ~4.4 minutes with 2 parallel workers

## Troubleshooting

## Tests Failing Due to Timeout
Increase timeout in `playwright.config.js`:
```javascript
timeout: 180000  // 3 minutes
```

## Browser Not Launching
Reinstall Playwright browsers:
```bash
npx playwright install --force
```

## Network Issues
Ensure stable internet connection as tests interact with live website.

## Additional Commands

## Run in Debug Mode
```bash
npx playwright test --debug
```

## Run Specific Test by ID
Edit `test-data.json` to include only desired test cases, or modify the test file.

## Generate Test Code
```bash
npx playwright codegen https://www.swifttranslator.com/
```

## Notes/Issues
- Tests interact with the live Swift Translator website
- Some tests may fail if the website is down or experiencing issues
- Translation accuracy depends on the current state of the Swift Translator system
- Test data includes Unicode Sinhala characters - ensure proper encoding support

## Repository
GitHub: [https://github.com/SuchinthaHettiarachchi/itpm-assignment-1-swift-translator-automation](https://github.com/SuchinthaHettiarachchi/itpm-assignment-1-swift-translator-automation)

## License
This project is created for academic purposes as part of ITPM coursework/SLIIT.

## Created by:IT23432734  

