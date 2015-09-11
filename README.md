# polymer-doc
How to start a polymer project with nodeJS,bower, grunt and yeoman.
This is the Ubuntu Guide 14.04 LTS:

First of all install node and npm.
Then, install yeoman:
```bash
sudo npm install -g yo
```

you might see some warnings complaining about your node version.
I'd recommend first of all to update to the lastest nodeJS version.
```bash
npm WARN engine cryptiles@2.0.5: wanted: {"node":">=0.10.40"} (current: {"node":"v0.10.25","npm":"1.3.10"})
npm WARN engine hoek@2.15.0: wanted: {"node":">=0.10.40"} (current: {"node":"v0.10.25","npm":"1.3.10"})

```
After that, you can get an error:

```bash
> yodoctor


Yeoman Doctor
Running sanity checks on your system

✔ Global configuration file is valid
✔ No .bowerrc file in home directory
✔ NODE_PATH matches the npm root
✖ Node.js version

Your Node.js version is outdated.
Upgrade to the latest version: https://nodejs.org

✔ No .yo-rc.json file in home directory
✖ npm version

Your npm version is outdated.

Upgrade to the latest version by running:
npm install -g npm


Found potential issues on your machine :(

```

