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
