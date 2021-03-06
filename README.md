##Ionic templates for MobileFirst Platform Foundation (MFP)

### Install

- Download the Ionic templates for MFP

```javascript
$ git clone https://github.com/csantanapr/mfp-ionic-templates.git
````
- Download and Install the [MobileFirst Platform Foundation (MFP) CLI](https://developer.ibm.com/mobilefirstplatform/install/#clui) 7.1 (minimum 7.1.0.00.20150907)

### How to use

- Create a Cordova App using one of the templates (blank, tabs, sidemenu) and run npm install
- MFP cordova create can take more arguments, must specify at least one platform ios or android (mfp help cordova create for more info)

```javascript
$ mfp cordova create myapp -p ios,android -t ~/Downlaods/mfp-ionic-templates-master/tabs
$ cd myapp
$ npm install
````

or in one single command (Linux, Mac)

```javascript
$ APP=myapp; mfp cordova create ${APP} -p ios,android -t ~/Downlaods/mfp-ionic-templates-master/tabs && cd ${APP} && npm install
````

### How to use the MFP CLI

- Use mfp cli to add additional platforms and plugins

```javascript
$ mfp cordova platform add 
$ mfp cordova platform add android
$ mfp cordova plugin add 
$ mfp cordova plugin add cordova-plugin-mfp-jsonstore
$ mfp cordova plugin add cordova-plugin-mfp-push

````

- Use mfp cli to emulate and run

```javascript
$ mfp cordova emulate
$ mfp cordova emulate -p ios
$ mfp cordova run
$ mfp cordova run -p android

````
Ignore if the emulate or run command prints something starting with "Error:" and ending with "console.log", It's not a real error just info from ios-sim into stderr

- Use ionic cli for other cordova actions *

```javascript
$ ionic serve
$ ionic serve --lab --livereload
$ ionic prepare
$ ionic build
```

*Note: --livereload for ionic emulate and ionic run don't work with MFP plugin (hoping this works in some time in the future :-) )

- To Preview using MobileFirst Browser Simulator (Cordova Emulation) or Simple Browser you need a local development Server with a backend running

```javascript
$ cd ../
$ mfp create backend
$ cd backend
$ mfp start
$ cd ../myapp/
$ mfp cordova preview
```

- Push the app to a remote server like the one in Bluemix Containers (Docker)

```javascript
$ mfp server add
$ mfp push <servername>
$ mfp console <servername>
```

### Demo
![Picture of screenshot of Mobile Browser Simulator running Ionic App](mbs_preview.png "Mobile Browser Simulator")

### License
Apache 2.0
