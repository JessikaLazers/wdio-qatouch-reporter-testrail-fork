# QA Touch
Test Together

Collaborative Test Case Management tool For Modern QA Teams

# QA Touch Reporter for Webdriver.io

Pushes test results into QA Touch system.

## Installation

```shell
$ npm i wdio-qatouch-reporter
```

## Usage
Ensure that your QA Touch API is enabled and generate your API keys. See https://doc.qatouch.com/#qa-touch-api

Add reporter to wdio.conf.js:

```Javascript
let QaTouchReporter = require('wdio-qatouch-reporter/lib/index');

...

    reporters: [
            'spec',
            [QaTouchReporter,
                {
                    qaTouchOptions: {
                        'domain' : "Your Domain",
                        'apiToken': "Your Api-Token",
                        'projectKey': 'Project Key',
                        'testRunId': 'Test Run Id',
                    }
                }
            ]
        ],
```


Mark your wdio test  names with ID of QA Touch test run cases. Ensure that your case ids are well distinct from test descriptions.
 
```Javascript
it("TR001 Authenticate with invalid user")
```

Only passed, untested and failed tests will be published in QA Touch Test Run.

## Options

**domain**: *string* domain name of your QA Touch instance (e.g. dckap)

**apiToken**: *string* API token for user which will be created in the edit profile menu in your domain login

**projectKey**: *number* project key with which the tests are associated

**testRunId**: *number* test run Id with which the tests are associated

## References
- https://www.npmjs.com/package/wdio-qatouch-reporter
- https://qatouch.com/
- https://help.qatouch.com/
- https://doc.qatouch.com/