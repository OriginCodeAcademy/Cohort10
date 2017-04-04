# Vehicle Manager (Frontend)

Over the next week, you'll be building a vehicle inventory system for car dealerships to manage inventory and sales to their customers. Sales staff need to be able to manage customer information, and enter sales data for reporting purposes.

Let's get to work!

## Toolbox
You will be using everything you have learned in the course so far to complete this project.

**Required Tools**

```
--Backend--
SQL Server
Entity Framework
ASP Web API

--Frontend--
HTML5
CSS Frameworks (Feeling adventurous? Try Semantic UI!)
Angular
Angular-UI-Router
Angular-Toastr
```

## Pages
- Dashboard (Optional)
	- Monthly Revenue
	- Number of Sales

- Customer Grid
	- Full Name
	- Email Address
	- Telephone
	- Outstanding Sales (# of sales where payment date is null)
	- Paid Sales (# of sales where payment date is not null)
	- Edit Button (Link to detail page with url e.g. `/customers/detail/1`)
	- Remove Button (Remember to confirm with user!)
- Customer Detail
	- First name field
	- Last name field
	- Email field
	- Telephone field
	- Date of Birth field
	- Table of Sales (optional)
		- Reuse the markup from the Sales Grid page.

- Sales Grid
	- Customer Name
	- Vehicle Year, Make, Model
	- Invoiced? (Should be either "Yes" or "No", depending on whether invoicedDate is null)
	- Paid? (See above, extrapolate for paymentReceived.)
	- Sale Price
	- Edit Button (Link to detail page with url e.g. `/sales/detail/1`)
	- Remove Button (Remember to confirm with user!)
- Sales Detail
	- Customer dropdown (Easy mode: use `<select>` with `ng-options`. Hard mode: use [`angular-selectize`](https://github.com/machineboy2045/angular-selectize) for an improved dropdown user experience.)
	- Vehicle dropdown (See above)
	- Sale Price
	- Invoice Date (Use `<input type='date' />` for a datepicker)
	- Payment Received Date (See above)

## Create the frontend

### Step by Step

#### Project Setup

- [ ] Fork and clone the [starter repository](https://github.com/origincodeacademy/vehicle-manager-web-base).
- [ ] Run `npm install` to reinstall development dependencies (gulp etc)
- [ ] Run `bower install angular bootstrap --save` to install angular/bootstrap.
- [ ] Add the following files in the following folder structure under `src/app`

![](https://snag.gy/wPz4nj.jpg)

#### Shell your JavaScript files

##### For every `*.module.js` file
- [ ] Use the `ngmodule` snippet to generate a bare minimum module.

**Example: customers.module.js**

```js
(function() {
    'use strict';

    angular
        .module('app.customers', []);
})();
```

##### For every `*.controller.js` file
- [ ] Use the `ngcontroller` snippet to generate a bare minimum controller. **Pay special attention to the module name you give to the `.module()` function**.

**Example: `customers.grid.controller.js`**

```js
(function() {
    'use strict';

    angular
        .module('app.customers')
        .controller('CustomersGridController', CustomersGridController);

    CustomersGridController.$inject = [];

    function CustomersGridController() {
        var vm = this;

        activate();

        function activate() {

        }
    }
})();
```

##### For every `*.factory.js` file
- [ ] Use the `ngfactory` snippet to generate a bare minimum factory.
- [ ] Refer back to your VSTDA project to see how you did the todoFactory, and apply that to each factory made in this project.

**Example: `customers.factory.js`**

```js
(function() {
    'use strict';

    angular
        .module('app.customers')
        .factory('customerFactory', customerFactory);

    customerFactory.$inject = [];

    function customerFactory() {
        var service = {
            getAll: getAll,
            getById: getById,
            create: create,
            remove: remove,
            update: update
        };

        return service;

        ///////////

        // functions go here
    }
})();
```

##### For `/src/app/app.module.js`
- [ ] Link all the feature modules together to form your app.

```js
(function() {
    'use strict';

    angular
        .module('app', [
            'app.customers',
            'app.dashboard',
            'app.sales',
            'app.vehicles'
        ]);
})();
```

## Setup your page routing using `ui-router`

### Install `angular-ui-router`
- [ ] In terminal, run `bower install angular-ui-router --save`

### Configure your States in `app.module.js`
- [ ] Add the state configurations as shown in the video. Below you can see an example of how to configure the states for the customers feature.

**Example: Customer States**

```js
$stateProvider
  .state('customer', {
    url: '/customer',
    abstract: true,
    template: '<div ui-view></div>'
  })
  .state('customer.grid', {
    url: '/grid',
    controller: 'CustomerGridController as customerGridCtrl',
    templateUrl: 'app/customer/customer.grid.html'
  })
  .state('customer.detail', {
    url: '/detail?id',
    controller: 'CustomerDetailController as customerDetailCtrl',
    templateUrl: 'app/customer/customer.detail.html'
  })
})
```

### Build your `index.html` file.

- [ ] Find and implement a bootstrap navbar that looks like the given screenshot.

- [ ] Place the following markup in `index.html` under the markup for the navbar.

```html
<div class="container">
	<div ui-view></div>
</div>
```

> The `ui-view` directive acts as a placeholder to render the current "state" that the user has visited. Each state has a partial template, which is rendered when the current "state" is active.

### Build each feature area

> Start with the customers grid controller. This grid will act in a similar way to your VSTDA app. (Maybe you can even reuse some code!)



---

# More released tomorrow!
