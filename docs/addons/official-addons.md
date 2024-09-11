# Official Add-on's

The following list contains add-on's that are officially supported by core Adze contributors and are maintained under the [`@adze` npm organization namespace](). We hope that over time this list will grow and hopefully community created add-on's can be adopted by the official organization.

---

## @adze/security-validator

This project is a plugin for the Adze logging library to provide tools for ensuring proper context is applied to logs that are meant to record security events such as access events and authentication events.

This library exposes some opinionated interfaces and a log listener factory for validating your security event logs.

|             | Location                                                                                                         |
| ----------- | ---------------------------------------------------------------------------------------------------------------- |
| Source Code | [https://github.com/AJStacy/adze-security-validator](https://github.com/AJStacy/adze-security-validator)         |
| npm         | [https://www.npmjs.com/package/@adze/security-validator](https://www.npmjs.com/package/@adze/security-validator) |

## @adze/transport-cloudwatch-logs

This project is a plugin for the Adze logging library to transport log data to AWS CloudWatch Logs.

This library exposes a log listener factory for setting up log groups and streams in CloudWatch Logs. It can be configured to automatically create the group or stream if it does not already exist.

|             | Location                                                                                                                       |
| ----------- | ------------------------------------------------------------------------------------------------------------------------------ |
| Source Code | [https://github.com/AJStacy/adze-transport-cloudwatch-logs](https://github.com/AJStacy/adze-transport-cloudwatch-logs)         |
| npm         | [https://www.npmjs.com/package/@adze/transport-cloudwatch-logs](https://www.npmjs.com/package/@adze/transport-cloudwatch-logs) |
