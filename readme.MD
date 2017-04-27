# Profiler

1. Checks site features via header and body heuristics
2. Checks Security using [SSL Labs API](https://www.ssllabs.com/projects/ssllabs-apis/)
3. Checks performance using [sitespeed.io](https://github.com/sitespeedio/sitespeed.io/)

## Feature Checks
Feature checks may be added to the JSON files.
### Header Checks
The JSON format for header checks is as follows:
```javascript
  "Drupal": {
    "x-generator": "Drupal",
    "x-drupal-cache": ""
  }
```
If you only need to check for the existence of the header key then leave the value blank
If you need to check both header and value, the script will check for the the entire header value for the substring that you put in the value

### Body Checks
```javascript
  "Google Tag Manager": [
    "googletagmanager.com",
    "googletagservices.com"
  ]
  ```
  The script will check for the string(s) in the entire HTML body. Try to be as explicit as possible

## Security Checks
 SSL Labs PHP library via [Björn Roland](https://github.com/bjoernr-de/php-ssllabs-api))

## Performance Check
Performance Checks are done using sitespeed.io. This must be installed locally currently.