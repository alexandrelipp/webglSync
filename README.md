# Webgl2 warnings

# ClientWaitSYnc
WebGL warning: clientWaitSync: ClientWaitSync must return TIMEOUT_EXPIRED until control has returned to the user agent's main loop. (only warns once

### FIREFOX
Cause : calling glGetSync twice without giving back control to user agent

### CHROME
does not happen

separator

# Timout
`timeout` must not exceed MAX_CLIENT_WAIT_TIMEOUT_WEBGL nanoseconds.

### CHROME and FireFox
- calling waitSync with timout max then `MAX_CLIENT_WAIT_TIMEOUT`

```
gl.clientWaitSync(sync, 0, max + 1);
shouldBe("gl.getError()", "gl.INVALID_OPERATION");
```


