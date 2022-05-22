# Open Desk Dash Desktop Companion
Open Source Desk Desktop Companion, is an Desktop API that is ran on your computer as an interface for the Open Desk Dash to query system information or any information required using Plugins.

## Desktop Service
A service that runs on the your desktop that acts as an interface to the PI, so it can query the desktop for information.

### Getting API key
The API key is auto generated on first run, this is printed our during that. If missed a query can be ran locally to view the key, as all API call's can be made locally without a key.

```
curl localhost:5000/api/key
```

### Plugins
The desktop service API can easily be extended with Plugins, by creating a flask blueprint and inserting the module into the "plugins" directory.
The blueprint module directory name and primary python script must have the same name, and the blueprint must be called api.
```
├── plugins
│   ├── example
│   │   ├── example.py
│   │   ├── __init__.py
```

```
api = Blueprint("example", __name__, url_prefix="/example")
```