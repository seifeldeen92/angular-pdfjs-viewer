# PDF.js Angular directive

Embed [PDF.js](https://mozilla.github.io/pdf.js/) into your angular application, maintaining that look and feel of pdf's we all love. This directive also allows you to scroll through the pdf.  

**Note that the guide below may still contain errors**


## Installation

    bower install angular-pdfjs --save


## Usage

Note that the order of the scripts being included should stay the same as in the example below.
Also note that images, translations and such are being loaded from the `web` folder.

** View **

    <!DOCTYPE html ng-app="app" ng-controller="AppCtrl">
    <html>
        <head>
            <title>Angular PDF.js demo</title>
            <meta name="viewport" content="width=device-width, initial-scale=1">

            <!-- pdfjs dependencies -->
            <link rel="stylesheet" href="web/viewer.css"/>
            <link rel="resource" type="application/l10n" href="web/locale/locale.properties"/>
            <script src="vendor/angular/angular.js"></script>
            <script src="vendor/angular-pdfjs/dist/web/l10n.js"></script>
            <script src="vendor/angular-pdfjs/dist/build/pdf.js"></script>
            <script src="vendor/angular-pdfjs/dist/build/pdf.worker.js"></script>
            <script src="vendor/angular-pdfjs/dist/web/compatibility.js"></script>
            <script src="vendor/angular-pdfjs/dist/web/debugger.js"></script>
            <script src="vendor/angular-pdfjs/dist/web/viewer.js"></script>

            <!-- the directive -->
            <script src="vendor/angular-pdfjs/dist/pdfjs-viewer.js"></script>
        </head>
        <body>
            <pdfjs-viewer src="{{ pdf.src }}"></pdfjs-viewer>
        </body>
    </html>

The directive takes the following optional attributes to modify the toolbar

    download="false" print="false" open="false"

Omitting these attributes will by default show the options in the toolbar.

** Controller **

    angular.module('app', ['pdfjs']);

    angular.module('app').controller('AppCtrl', function($scope) {
        $scope.pdf = {
            src: 'demo/example.pdf'
        };
    });


## Demo

You can test out a demo of this directive. You must run the node server first due to CORS reasons. First make sure the dependencies are installed.

    npm install

Afterwards run the server like so.

    node server.js

The server will be running on localhost:8080