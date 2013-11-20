# featureservice2triggers

A command line tool for creating Geotrigger Rules from an ArcGIS FeatureService.

## Installation

Just install with NPM. You will need Node.js installed.

```
$ npm install -g featureservice2triggers
```

## Usage

To print the full usage infromation just do...

```
$ featureservice2triggers
```

Here is an example of using `featureservice2triggers` to import a Feature Service of city parks.

```
$ featureservice2triggers --clientId=YOUR_CLIENT_ID --clientSecret=YOUR_CLIENT_SECRET --tag=parks --tag=portland --serviceUrl="http://services.arcgis.com/rOo16HdIMeOBI4Mb/arcgis/rest/services/Parks_pdx/FeatureServer/0" --notificationTemplate="Welcome to {{NAME}}"
```

The service you want to import **MUST** be publicly accessible.

## Options

Options | Description
--- | ---
`clientId` - **Required** | Client id from an application on http://developers.arcgis.com/en/applications/.
`clientSecret` - **Required** | Client secret from an application on developers.arcgis.com/en/applications/.
`serviceUrl` - **Required** | The URL of the Feature Layer you would like to import. You can find urls for your existing services at http://developers.arcgis.com/en/hosted-data/.
`tag`  - **Required** | Tag or tags to apply to the triggers created in the Geotrigger API. You can define `tag` as many times as you like to apply multipile tags to each trigger.
`buffer` | If you are importing point features, buffer them by this amount to create the trigger area. Defaults to 250 meters.
`useFeatureIds` | Use the ids of the features as the id of the trigger.
`callbackUrl` | When the triggers condition is satisfied a POST request will be sent to this URL
`notificationTemplate` |  A Mustache template for the push notification. Feature attributes will be passed into the template context. So a feature with attributes like `{NAME: Mt. Tabor Park}` and a template like `"Welcome to {{NAME"}}` will turn into `Welcome to Mt. Tabor Park`.
`trackingProfile` | Changes the devices tracking profile to this when the trigger is fired. Should be `off`, `adaptive`, `fine`, or `rough`
`direction` | The direction the device shold be traveling to fire the trigger. Either `enter` or `leave`

## Resources

* [ArcGIS for Developers](https://developers.arcgis.com)
* [ArcGIS Geotrigger Service](https://developers.arcgis.com/en/geotrigger-service/)
* [@esripdx](http://twitter.com/esri)

## Issues

Find a bug or want to request a new feature?  Please let us know by submitting an issue.

## Contributing

Esri welcomes contributions from anyone and everyone. Please see our [guidelines for contributing](https://github.com/esri/contributing).

## Licensing
Copyright 2013 Esri

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

   http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.

A copy of the license is available in the repository's [license.txt]( https://raw.github.com/Esri/esri-leaflet/master/license.txt) file.

[](Esri Tags: ArcGIS Geotrigger Service Tools Import FeatureLayer FeatureServer)
[](Esri Language: JavaScript)