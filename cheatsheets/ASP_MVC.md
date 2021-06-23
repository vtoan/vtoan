#  Filters ?
To execute some logic before or after an stage in the request processing pipeline (MVC/API Context). Ex: Caching, Logging, Error handling, Authorization...

To handle cross-cutting concerns. Filters avoid duplicating code. For example, an error handling exception filter could consolidate error handling.

The filter pipeline runs after ASP.NET Core selects the action to execute.

#  Filter types
`Authorization filters`
* Run first and are used to determine whether the current user is authorized for the current request.

* They can short-circuit the pipeline if a request is unauthorized.   

`Resource filters`
* `OnResourceExecuting` runs code before the rest of the filter pipeline.

* `OnResourceExecuted` runs code after the rest of the pipeline has completed.

* Can use it to implement caching or short-circuit the filter pipeline for performance reasons.

* Used for caching, large file uploads.

`Action filters`
* Run code immediately before and after an action method is called.

* Can change the arguments passed into an action.

* Can change the result returned from the action.

* Are not supported in Razor Pages.

* Used for validate model state, return an error if the state is invalid.

`Exception filters`
* Runs only if another filter, the action method, or the action result throws an exception     

`Result filters`
* Run before and after a view result is executed.

* Like if you want to modify a view result right before the view is rendered to the browser or formatter execution  

**How filter types interact in the filter pipeline**

![How filter types interact in the filter pipeline](https://docs.microsoft.com/en-us/aspnet/core/mvc/controllers/filters/_static/filter-pipeline-2.png?view=aspnetcore-5.0)

# Custom filters
Can create the Custom Filter for all the above different categories of Filters by implement corresponding interfaces.

Filter stages (types) can be implemented in a single class.

# Scope and Order of filters
### Filters can be applied at three levels
* Global

* Controller

* Action Method

**Default order of execution**

When there are multiple filters for a particular stage of the pipeline, scope determines the default order of filter execution.

Global filters surround class filters, which in turn surround method filters.

![Filters](https://dotnettrickscloud.blob.core.windows.net/img/aspnetcore/aspnet-core-filter-execution.jpg)

**Overriding the default order**

The default sequence of execution can be overridden by implementing `IOrderedFilter`. This exposes the `Order` property that takes precedence over scope to determine the order of execution.

Filters will executed by **ascending of Order**.

**Controller level filters**

Every controller that inherits from the `Controller` that **wrap the filters** that run for a given action. base class includes:
* `OnActionExecuting` is called before any of the action's filters.

* `OnActionExecuted` is called after all of the action filters.

* `OnActionExecutionAsync` is called before any of the action's filters.

# Cancellation and short-circuiting

Can be short-circuited by setting the `Result` property on the `context` parameter provided to the filter method.

# Dependency injection
Filters can be added by type or by instance.

* An instance is added, that instance is used for every request.

# IFilterFactory

Filters that implement `IFilterFactory` are useful for filters that:

* Don't require passing parameters.
* Have constructor dependencies that need to be filled by DI.

**Read more**

https://www.thecodebuzz.com/filters-in-net-core-best-practices/   
https://dotnettutorials.net/lesson/filters-in-mvc/
https://docs.microsoft.com/en-us/aspnet/core/mvc/controllers/filters?view=aspnetcore-5.0#authorization-filters
