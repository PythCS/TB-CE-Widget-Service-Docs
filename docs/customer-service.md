# CUSTOMER

Customer account management.

## Service Injection

```javascript
const $injector = self.ctx.$scope.$injector;
const customerService = $injector.get(self.ctx.servicesMap.get('customerService'));

// Alternative: Direct context access
const customerService = self.ctx.customerService;
```

## Methods

### getCustomers

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');

customerService.getCustomers(pageLink).subscribe(customers => {
  console.log('Customers:', customers);
});
```

### getCustomer

```javascript
const customerId = 'your-customer-id';

customerService.getCustomer(customerId).subscribe(customer => {
  console.log('Customer:', customer);
});
```

### getCustomersByIds

```javascript
const customerIds = 'your-customers-id';

customerService.getCustomersByIds(customerIds).subscribe(customer => {
  console.log('Customer:', customer);
});
```

### saveCustomer

```javascript
const customer = {
  // your customer object
};

customerService.saveCustomer(customer).subscribe(customer => {
  console.log('Customer:', customer);
});
```

