## letrest-angular-ui

LetRestUi is a set of Directives, Controllers and Services

### Installing letrest—angular-ui

```bash
bower install letrest-angular --save
```

## Directives

### lrSecurity
### lrShowAtLeastOn
### lrShowWhenLogged
### lrHideWhenLogged
### lrClassWhenLogged

## Services

### LetRestService
You can create an instance of a `LetRestService` for a given type doing
```javascript
  LetRestService.getLetRestService('entity_name');
```
This provide a singleton having these members
```
  Array all
  Object one
  Int totalRows
  promise get()
  promise getAll(options)
  promise save(options)
  promise delete(options)
  Object getNew() //needs an empty model generated server side, included as 'new' on the response, otherwise returns {}
```
A suggested implementation is to wrap this on a factory, i.e.
```javascript
angular
  .module('yourModule')
  .factory('AccountService', function(LetRestService){
    return LetRestService.getLetRestService('account');
  });
```
So you can inject this particular instance on your controllers as follow
```javascript
function myController(AccountService){
  this.theData = AccountService.all;
  AccountService.getAll();
}
```

### LetRestSecurityService
### LetRestSecurityEvents
* PANIC
* SECURITY
* DOLOGIN
* SYNC

## Filters

### lrHasPermissions

## Views

### LoginView (security)
### PanicView (security)
