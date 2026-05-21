# CustomerService

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const customerService = $injector.get(self.ctx.servicesMap.get('CustomerService'));

// Alternative: Direct context access
const customerService = self.ctx.customerService;
```

**1. getCustomers**

```javascript
customerService.getCustomers(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder')).subscribe(result => {
  console.log('Fetched  Customers result:', result);
});
```

**2. getCustomer**

```javascript
customerService.getCustomer('your-customer-id').subscribe(result => {
  console.log('Fetched  Customer result:', result);
});
```

**3. getCustomersByIds**

```javascript
customerService.getCustomersByIds('your-customerids-value').subscribe(result => {
  console.log('Fetched  Customers By Ids result:', result);
});
```

**4. saveCustomer**

```javascript
customerService.saveCustomer('your-customer-value').subscribe(result => {
  console.log('Saved  Customer result:', result);
});
```
