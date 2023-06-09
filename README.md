# wbteampropy
Python interface for the WbTeamPro API


# WbTeamPropy

WbTeamPropy is a Python interface to the WbTeamPro REST API.

[![PyPI version](https://badge.fury.io/py/wbteampropy.svg)](https://badge.fury.io/py/wbteampropy)

## Usage

Create a WbTeamPro interface with the API URL and credentials and use it to
call the API.

```python
import wbteampropy

wbteampro = wbteampropy.WBTEAMPRO(
    'https://example.com/modules/addons/wbteampro/api.php',
    'username',
    'password')
wbteampro.get_project(110)
```

API USERNAME 
This is a valid Administrator username that is within a WHMCS Administrative Role that has been granted access to the wbTeamPro system.

API PASSWORD 
This is the password for the valid Administrator

In general API methods can be called as methods in the WBTEAMPRO class. For
available API methods see the [WbTeamPro API reference](
https://docs.holodyn.com/WHMCS/wbTeamPro/v3/Web_API).
Note that the casing of the methods differ from the API actions. While the
API actions are CamelCased the methods are snake_cased.

### Calling unimplemented actions

Not all API actions are implemented as Python methods (they will be
implemented as required, of course pull-requests are accepted). In order to
call actions that are not yet implemented call() can be used. Example:

```python
response = wbteampro.call(
    'SomeAction',
    param=value,
    list_param=[
        element,
        element2,
    ]
)
```

See the call() documentation for more info.



