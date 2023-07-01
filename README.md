## Generate Reports:
After activating the venv and installing the requirements:

### Cucumber:
```bash
behave --format=json.pretty -o report.json
```
Then, use behave2cucumber to generate cucumber.json:
```bash
python -m behave2cucumber -i report.json -o cucumber.json
```
Download npm to use cucumber-html-reporter:
```bash
npm install cucumber-html-reporter
```
Generate the HTML:
```bash
node -e "var reporter = require('cucumber-html-reporter');reporter.generate({theme: 'bootstrap', jsonFile: 'cucumber.json', output: 'cucumber_report.html', reportSuiteAsScenarios: true, scenarioTimestamp: true, launchReport: true});"
```
## Unittests:
For unittest:
```bash
pytest --cov=./ --cov-config=.coveragerc --cov-report=html --html=report.html
```
