# [docs](index.md) » hs.task
---

Execute processes in the background and capture their output

Notes:
 * This is not intended to be used for processes which never exit. While it is possible to run such things with hs.task, it is not possible to read their output while they run and if they produce significant output, eventually the internal OS buffers will fill up and the task will be suspended.
 * An hs.task object can only be used once

## API Overview
* Functions - API calls offered directly by the extension
 * [new](#new)
* Methods - API calls which can only be made on an object returned by a constructor
 * [closeInput](#closeinput)
 * [environment](#environment)
 * [interrupt](#interrupt)
 * [isRunning](#isrunning)
 * [pause](#pause)
 * [pid](#pid)
 * [resume](#resume)
 * [setCallback](#setcallback)
 * [setEnvironment](#setenvironment)
 * [setInput](#setinput)
 * [setStreamingCallback](#setstreamingcallback)
 * [setWorkingDirectory](#setworkingdirectory)
 * [start](#start)
 * [terminate](#terminate)
 * [terminationReason](#terminationreason)
 * [terminationStatus](#terminationstatus)
 * [waitUntilExit](#waituntilexit)
 * [workingDirectory](#workingdirectory)

## API Documentation

### Functions

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.task.new(launchPath, callbackFn[, streamCallbackFn, arguments]) -> hs.task object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Creates a new hs.task object |
| **Parameters**                                       | <ul><li>launchPath - A string containing the path to an executable file.  This must be the full path to an executable and not just an executable which is in your environment's path (e.g. <code>/bin/ls</code> rather than just <code>ls</code>).</li><li>callbackFn - A callback function to be called when the task terminates, or nil if no callback should be called. The function should accept three arguments:</li><li>exitCode - An integer containing the exit code of the process</li><li>stdOut - A string containing the standard output of the process</li><li>stdErr - A string containing the standard error output of the process</li><li>streamCallbackFn - A optional callback function to be called whenever the task outputs data to stdout or stderr. The function must return a boolean value - true to continue calling the streaming callback, false to stop calling it. The function should accept three arguments:</li><li>task - The hs.task object or nil if this is the final output of the completed task.</li><li>stdOut - A string containing the standard output received since the last call to this callback</li><li>stdErr - A string containing the standard error output received since the last call to this callback</li><li>arguments - An optional table of command line argument strings for the executable</li></ul> |
| **Returns**                                          | <ul><li>An <code>hs.task</code> object</li></ul> |
| **Notes**                                            | <ul><li>The arguments are not processed via a shell, so you do not need to do any quoting or escaping. They are passed to the executable exactly as provided.</li><li>When using a stream callback, the callback may be invoked one last time after the termination callback has already been invoked. In this case, the <code>task</code> argument to the stream callback will be <code>nil</code> rather than the task userdata object and the return value of the stream callback will be ignored.</li></ul> |

### Methods

#### [closeInput](#closeinput)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.task:closeInput() -> hs.task object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Closes the task's stdin |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The hs.task object</li></ul> |
| **Notes**                                            | <ul><li>This should only be called on tasks with a streaming callback - tasks without it will automatically close stdin when any data supplied via <code>hs.task:setInput()</code> has been written</li><li>This is primarily useful for sending EOF to long-running tasks</li></ul> |

#### [environment](#environment)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.task:environment() -> environment` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the environment variables as a table for the task. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>a table of the environment variables for the task where each key is the environment variable name.</li></ul> |

#### [interrupt](#interrupt)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.task:interrupt() -> hs.task object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Interrupts the task |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>hs.task</code> object</li></ul> |
| **Notes**                                            | <ul><li>This will send SIGINT to the process</li></ul> |

#### [isRunning](#isrunning)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.task:isRunning() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Test if a task is still running. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>true if the task is running or false if it is not.</li></ul> |
| **Notes**                                            | <ul><li>A task which has not yet been started yet will also return false.</li></ul> |

#### [pause](#pause)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.task:pause() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Pauses the task |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>If the task was paused successfully, returns the task object; otherwise returns false</li></ul> |
| **Notes**                                            | <ul><li>If the task is not paused, the error message will be printed to the Hammerspoon Console</li><li>This method can be called multiple times, but a matching number of <code>hs.task:resume()</code> calls will be required to allow the process to continue</li></ul> |

#### [pid](#pid)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.task:pid() -> integer` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Gets the PID of a running/finished task |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>An integer containing the PID of the task</li></ul> |
| **Notes**                                            | <ul><li>The PID will still be returned if the task has already completed and the process terminated</li></ul> |

#### [resume](#resume)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.task:resume() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Resumes the task |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>If the task was resumed successfully, returns the task object; otherwise returns false</li></ul> |
| **Notes**                                            | <ul><li>If the task is not resumed successfully, the error message will be printed to the Hammerspoon Console</li></ul> |

#### [setCallback](#setcallback)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.task:setCallback(fn) -> hs.task object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Set or remove a callback function for a task. |
| **Parameters**                                       | <ul><li>fn - A function to be called when the task completes or is terminated, or nil to remove an existing callback</li></ul> |
| **Returns**                                          | <ul><li>the hs.task object</li></ul> |

#### [setEnvironment](#setenvironment)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.task:setEnvironment(environment) -> hs.task object | false` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Sets the environment variables for the task. |
| **Parameters**                                       | <ul><li>environment - a table of key-value pairs representing the environment variables that will be set for the task.</li></ul> |
| **Returns**                                          | <ul><li>The hs.task object, or false if the table was not set (usually because the task is already running or has completed)</li></ul> |

#### [setInput](#setinput)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.task:setInput(inputData) -> hs.task object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Sets the standard input data for a task |
| **Parameters**                                       | <ul><li>inputData - Data, in string form, to pass to the task as its standard input</li></ul> |
| **Returns**                                          | <ul><li>The hs.task object</li></ul> |
| **Notes**                                            | <ul><li>This method can be called before the task has been started, to prepare some input for it (particularly if it is not a streaming task)</li><li>If this method is called multiple times, any input that has not been passed to the task already, is discarded (for streaming tasks, the data is generally consumed very quickly, but for now there is no way to syncronise this)</li></ul> |

#### [setStreamingCallback](#setstreamingcallback)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.task:setStreamingCallback(fn) -> hs.task object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Set a stream callback function for a task |
| **Parameters**                                       | <ul><li>fn - A function to be called when the task outputs to stdout or stderr, or nil to remove a callback</li></ul> |
| **Returns**                                          | <ul><li>The hs.task object</li></ul> |
| **Notes**                                            | <ul><li>For information about the requirements of the callback function, see <code>hs.task.new()</code></li><li>If a callback is removed without it previously having returned false, any further stdout/stderr output from the task will be silently discarded</li></ul> |

#### [setWorkingDirectory](#setworkingdirectory)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.task:setWorkingDirectory(path) -> hs.task object | false` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Sets the working directory for the task. |
| **Parameters**                                       | <ul><li>path - a string containing the path you wish to be the working directory for the task.</li></ul> |
| **Returns**                                          | <ul><li>The hs.task object, or false if the working directory was not set (usually because the task is already running or has completed)</li></ul> |
| **Notes**                                            | <ul><li>You can only set the working directory if the task has not already been started.</li><li>This will only set the directory that the task starts in.  The task itself can change the directory while it is running.</li></ul> |

#### [start](#start)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.task:start() -> hs.task object | false` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Starts the task |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>If the task was started successfully, returns the task object; otherwise returns false</li></ul> |
| **Notes**                                            | <ul><li>If the task does not start successfully, the error message will be printed to the Hammerspoon Console</li></ul> |

#### [terminate](#terminate)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.task:terminate() -> hs.task object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Terminates the task |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>hs.task</code> object</li></ul> |
| **Notes**                                            | <ul><li>This will send SIGTERM to the process</li></ul> |

#### [terminationReason](#terminationreason)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.task:terminationReason() -> exitCode | false` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the termination reason for a task, or false if the task is still running. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>a string value of "exit" if the process exited normally or "interrupt" if it was killed by a signal.  Returns false if the termination reason is unavailable (the task is still running, or has not yet been started).</li></ul> |

#### [terminationStatus](#terminationstatus)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.task:terminationStatus() -> exitCode | false` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the termination status of a task, or false if the task is still running. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>the numeric exitCode of the task, or the boolean false if the task has not yet exited (either because it has not yet been started or because it is still running).</li></ul> |

#### [waitUntilExit](#waituntilexit)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.task:waitUntilExit() -> hs.task object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Blocks Hammerspoon until the task exits |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>hs.task</code> object</li></ul> |
| **Notes**                                            | <ul><li>All Lua and Hammerspoon activity will be blocked by this method. Its use is highly discouraged.</li></ul> |

#### [workingDirectory](#workingdirectory)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.task:workingDirectory() -> path` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the working directory for the task. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>a string containing the working directory for the task.</li></ul> |
| **Notes**                                            | <ul><li>This only returns the directory that the task starts in.  If the task changes the directory itself, this value will not reflect that change.</li></ul> |

