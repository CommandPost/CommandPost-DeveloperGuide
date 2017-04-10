# Hammerspoon docs: hs.task

Execute processes in the background and capture their output

Notes:
 * This is not intended to be used for processes which never exit. While it is possible to run such things with hs.task, it is not possible to read their output while they run and if they produce significant output, eventually the internal OS buffers will fill up and the task will be suspended.
 * An hs.task object can only be used once

## API Overview
* Functions - API calls offered directly by the extension</li>
  * new
* Methods - API calls which can only be made on an object returned by a constructor</li>
  * closeInput
  * environment
  * interrupt
  * isRunning
  * pause
  * pid
  * resume
  * setCallback
  * setEnvironment
  * setInput
  * setStreamCallback
  * setWorkingDirectory
  * start
  * terminate
  * terminationReason
  * terminationStatus
  * waitUntilExit
  * workingDirectory

## API Documentation

### Functions

#### new
  * Signature: hs.task.new(launchPath, callbackFn[, streamCallbackFn, arguments]) -> hs.task object
  * Type: Function
  * Description: Creates a new hs.task object
  * Parameters:
     * launchPath - A string containing the path to an executable file.  This must be the full path to an executable and not just an executable which is in your environment's path (e.g. `/bin/ls` rather than just `ls`).
     * callbackFn - A callback function to be called when the task terminates, or nil if no callback should be called. The function should accept three arguments:
      * exitCode - An integer containing the exit code of the process
      * stdOut - A string containing the standard output of the process
      * stdErr - A string containing the standard error output of the process
     * streamCallbackFn - A optional callback function to be called whenever the task outputs data to stdout or stderr. The function must return a boolean value - true to continue calling the streaming callback, false to stop calling it. The function should accept three arguments:
      * task - The hs.task object
      * stdOut - A string containing the standard output received since the last call to this callback
      * stdErr - A string containing the standard error output received since the last call to this callback
     * arguments - An optional table containing command line arguments for the executable
  * Returns:
     * An `hs.task` object

### Methods

#### closeInput
  * Signature: hs.task:closeInput() -> hs.task object
  * Type: Method
  * Description: Closes the task's stdin
  * Parameters:
     * None
  * Returns:
     * The hs.task object
  * Notes:
     * This should only be called on tasks with a streaming callback - tasks without it will automatically close stdin when any data supplied via `hs.task:setInput()` has been written
     * This is primarily useful for sending EOF to long-running tasks

#### environment
  * Signature: hs.task:environment() -> environment
  * Type: Method
  * Description: Returns the environment variables as a table for the task.
  Note:
     * if you have not yet set an environment table with the `hs.task:setEnvironment` method, this method will return a copy of the Hammerspoon environment table, as this is what the task will inherit by default.
  * Parameters:
     * None
  * Returns:
     * a table of the environment variables for the task where each key is the environment variable name.

#### interrupt
  * Signature: hs.task:interrupt() -> hs.task object
  * Type: Method
  * Description: Interrupts the task
  * Parameters:
     * None
  * Returns:
     * The `hs.task` object
  * Notes:
     * This will send SIGINT to the process

#### isRunning
  * Signature: hs.task:isRunning() -> boolean
  * Type: Method
  * Description: Test if a task is still running.
  * Parameters:
     * None
  * Returns:
     * true if the task is running or false if it is not.
  * Notes:
     * A task which has not yet been started yet will also return false.

#### pause
  * Signature: hs.task:pause() -> boolean
  * Type: Method
  * Description: Pauses the task
  * Parameters:
     * None
  * Returns:
     *  If the task was paused successfully, returns the task object; otherwise returns false
  * Notes:
     * If the task is not paused, the error message will be printed to the Hammerspoon Console
     * This method can be called multiple times, but a matching number of `hs.task:resume()` calls will be required to allow the process to continue

#### pid
  * Signature: hs.task:pid() -> integer
  * Type: Method
  * Description: Gets the PID of a running/finished task
  * Parameters:
     * None
  * Returns:
     * An integer containing the PID of the task
  * Notes:
     * The PID will still be returned if the task has already completed and the process terminated

#### resume
  * Signature: hs.task:resume() -> boolean
  * Type: Method
  * Description: Resumes the task
  * Parameters:
     * None
  * Returns:
     *  If the task was resumed successfully, returns the task object; otherwise returns false
  * Notes:
     * If the task is not resumed successfully, the error message will be printed to the Hammerspoon Console

#### setCallback
  * Signature: hs.task:setCallback(fn) -> hs.task object
  * Type: Method
  * Description: Set or remove a callback function for a task.
  * Parameters:
     * fn - A function to be called when the task completes or is terminated, or nil to remove an existing callback
  * Returns:
     * the hs.task object

#### setEnvironment
  * Signature: hs.task:setEnvironment(environment) -> hs.task object | false
  * Type: Method
  * Description: Sets the environment variables for the task.
  Note:
     * If you do not set an environment table with this method, the task will inherit the environment variables of the Hammerspoon application.  Set this to an empty table if you wish for no variables to be set for the task.
  * Parameters:
     * environment - a table of key-value pairs representing the environment variables that will be set for the task.
  * Returns:
     * The hs.task object, or false if the table was not set (usually because the task is already running or has completed)

#### setInput
  * Signature: hs.task:setInput(inputData) -> hs.task object
  * Type: Method
  * Description: Sets the standard input data for a task
  * Parameters:
     * inputData - Data, in string form, to pass to the task as its standard input
  * Returns:
     * The hs.task object
  * Notes:
     * This method can be called before the task has been started, to prepare some input for it (particularly if it is not a streaming task)
     * If this method is called multiple times, any input that has not been passed to the task already, is discarded (for streaming tasks, the data is generally consumed very quickly, but for now there is no way to syncronise this)

#### setStreamCallback
  * Signature: hs.task:setStreamCallback(fn) -> hs.task object
  * Type: Method
  * Description: Set a stream callback function for a task
  * Parameters:
     * fn - A function to be called when the task outputs to stdout or stderr, or nil to remove a callback
  * Returns:
     * The hs.task object
  * Notes:
     * For information about the requirements of the callback function, see `hs.task.new()`
     * If a callback is removed without it previously having returned false, any further stdout/stderr output from the task will be silently discarded

#### setWorkingDirectory
  * Signature: hs.task:setWorkingDirectory(path) -> hs.task object | false
  * Type: Method
  * Description: Sets the working directory for the task.
  * Parameters:
     * path - a string containing the path you wish to be the working directory for the task.
  * Returns:
     * The hs.task object, or false if the working directory was not set (usually because the task is already running or has completed)
  * Notes:
     * You can only set the working directory if the task has not already been started.
     * This will only set the directory that the task starts in.  The task itself can change the directory while it is running.

#### start
  * Signature: hs.task:start() -> hs.task object | false
  * Type: Method
  * Description: Starts the task
  * Parameters:
     * None
  * Returns:
     *  If the task was started successfully, returns the task object; otherwise returns false
  * Notes:
     * If the task does not start successfully, the error message will be printed to the Hammerspoon Console

#### terminate
  * Signature: hs.task:terminate() -> hs.task object
  * Type: Method
  * Description: Terminates the task
  * Parameters:
     * None
  * Returns:
     * The `hs.task` object
  * Notes:
     * This will send SIGTERM to the process

#### terminationReason
  * Signature: hs.task:terminationReason() -> exitCode | false
  * Type: Method
  * Description: Returns the termination reason for a task, or false if the task is still running.
  * Parameters:
     * None
  * Returns:
     * a string value of "exit" if the process exited normally or "interrupt" if it was killed by a signal.  Returns false if the termination reason is unavailable (the task is still running, or has not yet been started).

#### terminationStatus
  * Signature: hs.task:terminationStatus() -> exitCode | false
  * Type: Method
  * Description: Returns the termination status of a task, or false if the task is still running.
  * Parameters:
     * None
  * Returns:
     * the numeric exitCode of the task, or the boolean false if the task has not yet exited (either because it has not yet been started or because it is still running).

#### waitUntilExit
  * Signature: hs.task:waitUntilExit() -> hs.task object
  * Type: Method
  * Description: Blocks Hammerspoon until the task exits
  * Parameters:
     * None
  * Returns:
     * The `hs.task` object
  * Notes:
     * All Lua and Hammerspoon activity will be blocked by this method. Its use is highly discouraged.

#### workingDirectory
  * Signature: hs.task:workingDirectory() -> path
  * Type: Method
  * Description: Returns the working directory for the task.
  * Parameters:
     * None
  * Returns:
     * a string containing the working directory for the task.
  * Notes:
     * This only returns the directory that the task starts in.  If the task changes the directory itself, this value will not reflect that change.
