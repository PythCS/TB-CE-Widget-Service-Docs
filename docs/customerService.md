# CUSTOMER SERVICE

Part of the [ThingsBoard CE Widget Services Documentation](../DOCUMENTATION.md).

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const customerService = $injector.get(self.ctx.servicesMap.get('customerService'));

// Alternative: Direct context access
const customerService = self.ctx.customerService;
```

**1. getCustomers**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.customerService.getCustomers(pageLink).subscribe(customers => {
  console.log('Get Customers:', customers);
});
```

**2. getCustomer**

```javascript
self.ctx.customerService.getCustomer('your-customer-id').subscribe(customer => {
  console.log('Get Customer:', customer);
});
```

**3. getCustomersByIds**

```javascript
self.ctx.customerService.getCustomersByIds('your-customerids-value').subscribe(customersByIds => {
  console.log('Get Customers By Ids:', customersByIds);
});
```

**4. saveCustomer**

```javascript
self.ctx.customerService.saveCustomer('your-customer-value').subscribe(customer => {
  console.log('Save Customer:', customer);
});
```
