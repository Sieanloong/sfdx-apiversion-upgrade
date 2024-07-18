# Easy to use tool for upgrading API versions salesforce meta xml files!

Helps in upgrading salesforce api version for selected metadata files. Specify a target api version and the plugin will take care of modifying all the meta xml files with the target api version!

#original source code reference: 
https://github.com/ganesh2109/salesforce-apiversion-upgrade

<!-- toc -->
* [Easy to use tool for upgrading API versions salesforce meta xml files!](#easy-to-use-tool-for-upgrading-api-versions-salesforce-meta-xml-files)
<!-- tocstop -->

Since this is a SFDX plugin, it is a pre-requisite to have salesforce CLI installed globally first.
Once that is in place, you can use the below to install this plugin!

```sh-session
Install the plugin
$ sfdx plugins:install sfdx-apiversion-upgrade

To check whether the plugin is installed
$ sfdx metadatautil:upgradeapiversion

To update the plugin to the latest version
$ sfdx plugins:update
```

```
USAGE:
  $ sfdx metadatautil:upgradeapiversion -m <array> -p <string> [-s <number>] [-t <number>] [-x <string>] [-d] [--json]
  [--loglevel trace|debug|info|warn|error|fatal|TRACE|DEBUG|INFO|WARN|ERROR|FATAL]

OPTIONS:
  -d, --dryrun If present will only output the files changed without actually changing them
  -m, --metadata (required) Select metadata type.pick one or several of them, e.g: classes or classes/triggers; Possible values:  classes/pages/components/triggers/aura/lwc/flows
  -p, --path (required) The path to your src folder
  -s, --sourceversion The API version threshold from which you wish to upgrade. Minimum: 10, Maximum: 199, Default: 50
  -t, --targetversion The API version you want to upgrade to. Minimum:51 Maximum:200 Default:51
  -x, --fileprefix Metadata filename prefix. E.g. App for App_Utils.cls. Default: none(all files)

EXAMPLES:
sfdx metadatautil:upgradeapiversion -m classes -s 40 -t 48 -p "{yourprojectsrc-path}\src"
sfdx metadatautil:upgradeapiversion -m classes/pages -s 40 -t 48 -p "{yourprojectsrc-path}\src" -x "App"
```
