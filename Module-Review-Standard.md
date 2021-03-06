# Module Review Standard

This document is based on ABP official [Module Development Best Practices & Conventions](https://docs.abp.io/en/abp/latest/Best-Practices/Index). You can review an ABP module design according to this document.

## Common

* Repositories outside of current module should not be used.
* Handle more exceptions so people can replace them for easier customization.

## Application Project

* TodoAppService should implement ITodoAppService.

## Application.Contracts Project

* ITodoAppService interface should contains all the public methods.

## Domain Project

* All the repository query methods should have `CancellationToken cancellationToken = default` param.
* If the Todo entity has relationships, all the custom repository query methods should have `bool includeDetails` param, the default value for get list methods is `false` and for get/find methods is `false`.

## EntityFrameworkCore Project

* No table shared with ABP framework or ABP official modules.

## Web Project

* Todo menu item should be a sub item of administration menu item by default.
* Use application services instead of domain services or repositories.
* In Pages folder, the Todo folders should in the TodoManagement (module name) folder.
* List pages should have the `Title`, `BreadCrumb` and `MenuItemName` configurations in PageLayout.Content.
* List pages should have actions permission check.
* Sub list pages should show the parent entity identification. For example, using `PageLayout.Content.Title = "TodoItem (TodoName1)";` and `<abp-card-title>TodoItem (TodoName1)</abp-card-title>`
