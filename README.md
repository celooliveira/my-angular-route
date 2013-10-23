my-angular-route
================

My angular-route.js file with auto route modification

controller definition by route params via ngRoute.

default behaviour:

    $routeProvider
        //  Default call
        .when('/main', {
            templateUrl: 'views/main.html',
            controller: 'MainCtrl'
          })
          .otherwise({ redirectTo: '/error' });

behaviour using route params support:

    $routeProvider
        //  Default call
        .when('/:section', {
            templateUrl: function(req) {
                return 'views/' + req.section + '.html';
            },
            controller: function(req) {
                return req.section+ 'Ctrl';
            }, 
            autoRoute: true
        })
        .otherwise({ redirectTo: '/error' });


How to use in project (a example of how i use it)

App.js: application routes settings

https://github.com/willmendesneto/angular-architecture/blob/master/app/scripts/app.js

BaseCtrl:how i receive the routeParam method and call it 

https://github.com/willmendesneto/angular-architecture/blob/master/app/scripts/controllers/base/base.js
