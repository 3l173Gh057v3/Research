## Subprocess Modules (Python)

Basically subprocess module allows you to spawn new processes, connect to input/output/error pipes, and even obtain return codes. 

Subprocess intends to replace several older modules and functions:

    os.system
    os.spawn*

## How to use subprocess module?
The best way to invoking subprocesses is to use the **run()** function or even in most advanced cases, we can use **Popen** interface directly.

example 1:

    os.system("ls -l")

example 2:

    os.system('pdv -t %s > 123.txt' % epoch_name)

## Ok so what's actually a class.subprocess ?

| class.subprocess | description |
|--|--|
| **CompletedProcess** | The return value from [`run()`](https://docs.python.org/3/library/subprocess.html#subprocess.run "subprocess.run"), representing a process that has finished. |
| **args** | The arguments used to launch the process. This may be a list or a string. |
| **returncode** | Exit status of the child process. Typically, an exit status of 0 indicates that it ran successfully. |
| **stdout** | Captured stdout from the child process. A bytes sequence, or a string if [`run()`](https://docs.python.org/3/library/subprocess.html#subprocess.run "subprocess.run") was called with an encoding, errors, or text=True. `None` if stdout was not captured. |
| **stderr** | Captured stderr from the child process. A bytes sequence, or a string if [`run()`](https://docs.python.org/3/library/subprocess.html#subprocess.run "subprocess.run") was called with an encoding, errors, or text=True. `None` if stderr was not captured. |
| **check_returncode()** | If [`returncode`](https://docs.python.org/3/library/subprocess.html#subprocess.CompletedProcess.returncode "subprocess.CompletedProcess.returncode") is non-zero, raise a [`CalledProcessError`](https://docs.python.org/3/library/subprocess.html#subprocess.CalledProcessError "subprocess.CalledProcessError"). |
| **DEVNULL** | Special value that can be used as the stdin, stdout or stderr argument to Popen and indicates that the special file os.devnull will be used. |
| **PIPE** | Special value that can be used as the stdin, stdout or stderr argument to Popen and indicates that a pipe to the standard stream should be opened. Most useful with Popen.communicate(). |
| **STDOUT** | Special value that can be used as the stderr argument to Popen and indicates that standard error should go into the same handle as standard output. |

## Ok then what's exception subprocess ?
| exception subprocess | description |
|--|--|
| **SubprocessError** | Base class for all other exceptions from this module. |
| **TimeoutExpired** | Subclass of SubprocessError, raised when a timeout expires while waiting for a child process. |
| **CalledProcessError** | Subclass of SubprocessError, raised when a process run by check_call(), check_output(), or run() (with check=True) returns a non-zero exit status. |
|  **cmd** | Command that was used to spawn the child process. |
| **timeout** | Timeout in seconds. |
| **output** | Output of the child process if it was captured by [`run()`](https://docs.python.org/3/library/subprocess.html#subprocess.run "subprocess.run") or [`check_output()`](https://docs.python.org/3/library/subprocess.html#subprocess.check_output "subprocess.check_output"). Otherwise, `None`. |
| **stdout** | Alias for output, for symmetry with [`stderr`](https://docs.python.org/3/library/subprocess.html#subprocess.TimeoutExpired.stderr "subprocess.TimeoutExpired.stderr"). |
| **stderr** | Stderr output of the child process if it was captured by [`run()`](https://docs.python.org/3/library/subprocess.html#subprocess.run "subprocess.run"). Otherwise, `None`. |

## Popen Constructor

The underlying process creation and management in this module is handled by the [`Popen`](https://docs.python.org/3/library/subprocess.html#subprocess.Popen "subprocess.Popen") class. It offers a lot of flexibility so that developers are able to handle the less common cases not covered by the convenience functions.

Example 1:

    Popen(["/usr/bin/git", "commit", "-m", "Fixes a bug."])

Example 2:

    Popen(['/bin/sh', '-c', args[0], args[1], ...])








