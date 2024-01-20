# Concepts

* Concurrency

* Multithreading

* Parallel Processing

* Asynchronous Programming

* Reactive Programming

# Task
* `Task class` represents a single operation that does **not return a value** and that usually executes asynchronously.

* For operations that **retun values** using `Task<TResult> class`.

* Task objects are one of the central components of the **Task-based asynchronous pattern (TAP)**

* Task objects typically executes asynchronously on a **Thread pool**.

* Having status as `IsCanceled`, `IsCompleted`, `IFaulted`.

## Task Instantiation
Having four basic way to creates and executes:
* **Created** by using a `Task class constructor`, but is **started** by calling its `Start()` method.

* **Created** and **started** in a single method by calling the `TaskFactory.StartNew(Action<Object>,
Object)` method. (This is equivalent to first way).

* **Created** and **started** in a single method by calling the `Run(Action)` method.

* **Executed** synchronously on the main thread by calling the `RunSynchronously()` method.

## Waiting tasks to complete

* `Task.Wait()`/ `Task.WaitAny(Task[])/ Task.WaitAll(Task[])` method.

* We can pass **TimeSpan** or **CancellationToken** into those methods.

# Workflows
* **I/O-bound** needs (such as requesting data from a network, accessing a database, or reading and writing to a file system).

* **CPU-bound** code, such as performing an expensive calculation

# Reference
https://devblogs.microsoft.com/pfxteam/task-run-vs-task-factory-startnew/
https://rubikscode.net/2018/06/04/asynchronous-programming-in-net-task-based-asynchronous-pattern-tap/
https://rubikscode.net/2018/05/28/asynchronous-programming-in-net-common-mistakes-and-best-practices/
https://gist.github.com/tuscen/410ed491e2086ae3b4e7aaf2fc9e2870#case-study-copytoasync
https://viblo.asia/p/parallel-processing-concurrency-va-async-programming-OeVKBdj0lkW
https://softwareengineering.stackexchange.com/questions/173575/what-is-a-thread-pool
https://gist.github.com/ghuntley/e5b5642ecc4428255e61185bb79856e4
