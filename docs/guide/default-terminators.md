# Default Terminators

:::danger
Adze v1.x is now deprecated! Please upgrade to [v2.x](https://adzejs.com/)!
:::

After you generated an Adze log instance from a [factory function](factories.md) and have applied the desired [modifiers](modifiers.md) you must terminate the method chain. The methods used to terminate the chain are called **terminators**.

When a log has been terminated it will generate a log render, check if it is allowed to print the log render, cache the log instance if a [Shed](/shed) exists, and then return a data object representing the log properties and the log render to any registered log listeners. After all of that it will return a [terminated log object](/guide/concepts.html#terminated-log-object).

Adze comes with 8 default log level terminators, all of which can be [configured](configuration):

| Level | Name                | Standard Method Used |
| ----- | ------------------- | -------------------- |
| 0     | [alert](#alert)     | error                |
| 1     | [error](#error)     | error                |
| 2     | [warn](#warn)       | warn                 |
| 3     | [info](#info)       | info                 |
| 4     | [fail](#fail)       | info                 |
| 5     | [success](#success) | info                 |
| 6     | [log](#log)         | log                  |
| 7     | [debug](#debug)     | debug                |
| 8     | [verbose](#verbose) | debug                |

## alert

This level should only be used for logs that require immediate attention. This should be used sparingly and only for the most critical of errors.

**Default log level** = 0

**Standard Log Method:** error

_This is not a standard API._

### Interface

```typescript
class BaseLog {
  public error(...args: unknown[]): TerminatedLog<this>;
}
```

### Example

```javascript
import { adze } from 'adze';

adze().alert('Something went horribly wrong!');
// With emoji's enabled
adze({ useEmoji: true }).alert('Something went horribly wrong!');
```

### Output

![alert example output](./examples/alert-example.png)

![alert terminal example output](./examples/alert-terminal-example.png)

## error

Use this for logging fatal errors or errors that impact functionality of your application.

**Default log level** = 1

**Standard Log Method:** error

[**MDN Docs**](https://developer.mozilla.org/en-US/docs/Web/API/Console/error)

### Interface

```typescript
class BaseLog {
  public error(...args: unknown[]): TerminatedLog<this>;
}
```

### Example

```javascript
import { adze } from 'adze';

adze().error('An error occurred!');
// With emoji's enabled
adze({ useEmoji: true }).error('An error occurred!');
```

### Output

![error example output](./examples/error-example.png)

![error terminal example output](./examples/error-terminal-example.png)

## warn

Use this for logging issues that may impact app performance in a less impactful way than an error.

**Default log level** = 2

**Standard Log Method:** warn

[**MDN Docs**](https://developer.mozilla.org/en-US/docs/Web/API/Console/warn)

### Interface

```typescript
class BaseLog {
  public warn(...args: unknown[]): TerminatedLog<this>;
}
```

### Example

```javascript
import { adze } from 'adze';

adze().warn("I'm warning you!");
// With emoji's enabled
adze({ useEmoji: true }).warn("I'm warning you!");
```

### Output

![warn example output](./examples/warn-example.png)

![warn terminal example output](./examples/warn-terminal-example.png)

## info

Use this for logging general insights into your application. This level does not indicate any problems.

**Default log level** = 3

**Standard Log Method:** info

[**MDN Docs**](https://developer.mozilla.org/en-US/docs/Web/API/Console/info)

### Interface

```typescript
class BaseLog {
  public info(...args: unknown[]): TerminatedLog<this>;
}
```

### Example

```javascript
import { adze } from 'adze';

adze().info('App information');
// With emoji's enabled
adze({ useEmoji: true }).info('App information');
```

### Output

![info example output](./examples/info-example.png)

![info terminal example output](./examples/info-terminal-example.png)

## fail

Use this for logging network communication errors or other non-fatal errors that do not break your application.

**Default log level** = 4

**Standard Log Method:** info

_This is not a standard API._

### Interface

```typescript
class BaseLog {
  public fail(...args: unknown[]): TerminatedLog<this>;
}
```

### Example

```javascript
import { adze } from 'adze';

adze().fail('An operation failed to execute!');
// With emoji's enabled
adze({ useEmoji: true }).fail('An operation failed to execute!');
```

### Output

![fail example output](./examples/fail-example.png)

![fail terminal example output](./examples/fail-terminal-example.png)

## success

Use this for logging successful network communications or other successful operations within your app.

**Default log level** = 5

**Standard Log Method:** info

_This is not a standard API._

### Interface

```typescript
class BaseLog {
  public success(...args: unknown[]): TerminatedLog<this>;
}
```

### Example

```javascript
import { adze } from 'adze';

adze().success('An operation was successful!');
// With emoji's enabled
adze({ useEmoji: true }).success('An operation was successful!');
```

### Output

![success example output](./examples/success-example.png)

![success terminal example output](./examples/success-terminal-example.png)

## log

Use this for general logging that doesn't apply to any of the lower levels.

**Default log level** = 6

**Standard Log Method:** log

[**MDN Docs**](https://developer.mozilla.org/en-US/docs/Web/API/Console/log)

### Interface

```typescript
class BaseLog {
  public log(...args: unknown[]): TerminatedLog<this>;
}
```

### Example

```javascript
import { adze } from 'adze';

adze().log('Logging a message.');
// With emoji's enabled
adze({ useEmoji: true }).log('Logging a message.');
```

### Output

![log example output](./examples/log-example.png)

![log terminal example output](./examples/log-terminal-example.png)

## debug

Use this for logging information that you typically do not want to see unless you are debugging a problem with your application. This is typically hidden by default.

**Default log level** = 7

**Standard Log Method:** debug

[**MDN Docs**](https://developer.mozilla.org/en-US/docs/Web/API/Console/debug)

### Interface

```typescript
class BaseLog {
  public debug(...args: unknown[]): TerminatedLog<this>;
}
```

### Example

```javascript
import { adze } from 'adze';

adze().debug('Debugging an issue.');
// With emoji's enabled
adze({ useEmoji: true }).debug('Debugging an issue.');
```

### Output

![debug example output](./examples/debug-example.png)

![debug terminal example output](./examples/debug-terminal-example.png)

## verbose

Use this for logging extremely detailed debugging information. Use this level when the values you are logging are granular enough that they are no longer easily human readable.

**Default log level** = 8

**Standard Log Method:** verbose

_This is not a standard API._

### Interface

```typescript
class BaseLog {
  public verbose(...args: unknown[]): TerminatedLog<this>;
}
```

### Example

```javascript
import { adze } from 'adze';

adze().verbose('Logging some extreme detail.');
// With emoji's enabled
adze({ useEmoji: true }).verbose('Logging some extreme detail.');
```

### Output

![verbose example output](./examples/verbose-example.png)

![verbose terminal example output](./examples/verbose-terminal-example.png)
