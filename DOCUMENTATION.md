# This is documentation for FunHub
---
## How add your plugins to FunHub:
In FunHub there is a two types of plugins that you can add:
* Local
  * A local .py file on your PC
  * Contain **name** of added plugin and a **full path** to it .py script file.
* Remote
  * A plugin that upload on PyPi
  * This type also has it **name** as previos one, but instead of file path it has **package name** (a name of PyPi project) and **command name** (a command to launch the plugin from terminal).
 
there is examples of it
```json
{
  plugins[
    {
      "type":"local",
      "name":"Example plugin",
      "pluginPath":"C:\\path\\to\\file\\plugin.py"
    }
  ]
}
```
```json
{
  plugins[
    {
      "type":"remote",
      "name":"Example plugin",
      "packageName":"plugin-pypi-name",
      "commandName":"commandToLaunchPlugin"
    }
  ]
}
```

**The name field it's a name that would seen in FunHud menu.**

### Requerments for plugins
there is not a lot actualy:
* For remote type plugins you need a command that it would launch. For example you can do it in setup.py file, before uploading your plugin to PyPi:
 ```
  entry_points={
        'console_scripts': [
            'yourCommand = yourFileName:main',
        ],
    },
  ```
* If you have some requerments for yout local type plugin you need install it all by your self.
