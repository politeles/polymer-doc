# polymer-doc
How to start a polymer project with nodeJS,bower, grunt and yeoman.
##This is the Ubuntu Guide 14.04 LTS:

### Install node JS
First of all install node and npm.

distros package managers are usually out-dated, so it's better to work with Node Version Manager (NVM) [https://github.com/creationix/nvm]
```bash
wget -qO- https://raw.githubusercontent.com/creationix/nvm/v0.26.1/install.sh | bash
```

And that's the response on my system, when you have previously installed some node packages:
```bash
=> Downloading nvm from git to '/home/joseenriquep/.nvm'
=> Clonar en «/home/joseenriquep/.nvm»...
remote: Counting objects: 3906, done.
remote: Compressing objects: 100% (19/19), done.
remote: Total 3906 (delta 8), reused 0 (delta 0), pack-reused 3887
Receiving objects: 100% (3906/3906), 967.65 KiB | 180.00 KiB/s, done.
Resolving deltas: 100% (2261/2261), done.
Checking connectivity... hecho.
* (detached from v0.26.1)
  master

=> Appending source string to /home/joseenriquep/.bashrc
npm ERR! max depth reached: cordova@5.1.1, required by undefined@undefined
npm ERR! max depth reached: http-server@0.8.0, required by undefined@undefined
npm ERR! max depth reached: phonegap@5.1.1-0.29.0, required by undefined@undefined
npm ERR! max depth reached: spawn-sync@1.0.13, required by undefined@undefined
npm ERR! max depth reached: yo@1.4.8, required by undefined@undefined
npm ERR! not ok code 0
=> You currently have modules installed globally with `npm`. These will no
=> longer be linked to the active version of Node when you install a new node
=> with `nvm`; and they may (depending on how you construct your `$PATH`)
=> override the binaries of modules installed with `nvm`:

/usr/local/lib
├── cordova@5.1.1
├── http-server@0.8.0
├── phonegap@5.1.1-0.29.0
├── spawn-sync@1.0.13
└── yo@1.4.8

=> If you wish to uninstall them at a later point (or re-install them under your
=> `nvm` Nodes), you can remove them from the system Node as follows:

     $ nvm use system
     $ npm uninstall -g a_module

=> You can now start using nvm

```
After that message, you have to log out or reload your profile:
```bash
joseenriquep@mortimer:~$ source ~/.profile
```

Then you can start nvm from your home folder:
```bash
joseenriquep@mortimer:~$ nvm ls-remote
        v0.1.14
        v0.1.15

```
Lastest version is v0.12.7
```bash
nvm install v0.12.7
```

The output is the following:

```bash
--2015-09-11 21:03:49--  https://nodejs.org/dist/v0.12.7/node-v0.12.7-linux-x64.tar.gz
Resolviendo nodejs.org (nodejs.org)... 104.20.22.46, 104.20.23.46, 2400:cb00:2048:1::6814:162e, ...
Conectando con nodejs.org (nodejs.org)[104.20.22.46]:443... conectado.
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 10060524 (9,6M) [application/gzip]
Grabando a: “/home/joseenriquep/.nvm/bin/node-v0.12.7-linux-x64/node-v0.12.7-linux-x64.tar.gz”

100%[======================================>] 10.060.524   485KB/s   en 13s    

2015-09-11 21:04:03 (728 KB/s) - “/home/joseenriquep/.nvm/bin/node-v0.12.7-linux-x64/node-v0.12.7-linux-x64.tar.gz” guardado [10060524/10060524]

Now using node v0.12.7 (npm v2.11.3)

```
Then you can check which versions are you running:
```bash
joseenriquep@mortimer:~$ node -v
v0.12.7
joseenriquep@mortimer:~$ npm -v
2.11.3

```
Beware of the differences:
```bash
joseenriquep@mortimer:~$ npm -v
2.11.3
joseenriquep@mortimer:~$ sudo npm -v
1.3.10

```
To avoid problems, I set the following command on my .bashrc:
```bash
 nvm use stable
```
### Install yeoman
Then, install yeoman:
```bash
sudo npm install -g yo
```
From the official documentation [http://yeoman.io/learning/] you usually install the following components:
`` bash
npm install -g yo bower grunt-cli gulp
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

With an updated version of node and npm you will get:
```bash
> yodoctor


Yeoman Doctor
Running sanity checks on your system

✔ Global configuration file is valid
✔ NODE_PATH matches the npm root
✔ Node.js version
✔ No .bowerrc file in home directory
✔ No .yo-rc.json file in home directory
✔ npm version

Everything looks all right!

```
### Yeoman and Polymer
Set up a project folder and then configure the generator for polymer and yeoman.
The installation guide can be found here[https://github.com/yeoman/generator-polymer]
```bash
npm install -g generator-polymer
```
The output of the command should be something like:
```bash
npm WARN deprecated CSSselect@0.4.1: the module is now available as 'css-select'
npm WARN deprecated CSSwhat@0.4.7: the module is now available as 'css-what'
generator-polymer@1.1.0 /home/joseenriquep/.nvm/versions/node/v0.12.7/lib/node_modules/generator-polymer
├── ncp@2.0.0
├── chalk@1.1.1 (escape-string-regexp@1.0.3, supports-color@2.0.0, ansi-styles@2.1.0, has-ansi@2.0.0, strip-ansi@3.0.0)
├── yosay@1.0.5 (ansi-regex@1.1.1, ansi-styles@2.1.0, word-wrap@1.1.0, strip-ansi@2.0.1, pad-component@0.0.1, minimist@1.2.0, taketalk@1.0.0, string-width@1.0.1, repeating@1.1.3)
├── validate-element-name@1.0.0 (log-symbols@1.0.2, ncname@1.0.0)
├── lodash@3.10.1
├── rimraf@2.4.3 (glob@5.0.14)
└── yeoman-generator@0.18.10 (read-chunk@1.0.1, detect-conflict@1.0.0, dargs@3.0.1, user-home@1.1.1, yeoman-welcome@1.0.1, xdg-basedir@1.0.1, class-extend@0.1.1, diff@1.4.0, text-table@0.2.0, mime@1.3.4, underscore.string@2.4.0, async@0.9.2, debug@2.2.0, run-async@0.1.0, nopt@3.0.4, cross-spawn@0.2.9, istextorbinary@1.0.2, mkdirp@0.5.1, shelljs@0.3.0, cli-table@0.3.1, lodash@2.4.2, pretty-bytes@1.0.4, dateformat@1.0.11, through2@0.6.5, inquirer@0.8.5, sinon@1.16.1, github-username@1.1.1, yeoman-assert@1.0.0, glob@4.5.3, file-utils@0.2.2, findup-sync@0.2.1, mem-fs-editor@1.2.3, yeoman-environment@1.2.7, cheerio@0.18.0, gruntfile-editor@0.2.0, download@3.3.0)

```

#### Create your app boiler plate

```bash
yo polymer
```
After that you can just check out the result:
```bash
gulp serve
```
That's the terminal output:
```bash
[11:15:43] Using gulpfile ~/Documentos/Develop/polymer-doc/polymer-doc/test-project/gulpfile.js
[11:15:43] Starting 'styles'...
[11:15:44] Starting 'elements'...
[11:15:44] Starting 'images'...
[11:15:45] Finished 'elements' after 647 ms
[11:15:45] styles all files 98 B
[11:15:45] Finished 'styles' after 1.57 s
[11:15:45] images all files 24.13 kB
[11:15:45] Finished 'images' after 849 ms
[11:15:45] Starting 'serve'...
[11:15:45] Finished 'serve' after 145 ms
[PSK] Access URLs:
 --------------------------------------
       Local: http://localhost:3000
    External: http://192.168.0.102:3000
 --------------------------------------
          UI: http://localhost:3001
 UI External: http://192.168.0.102:3001
 --------------------------------------
[PSK] Serving files from: .tmp
[PSK] Serving files from: app

```
