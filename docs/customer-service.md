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

**3. getCustomerInfo**

```javascript
self.ctx.customerService.getCustomerInfo('your-customer-id').subscribe(customerInfo => {
  console.log('Get Customer Info:', customerInfo);
});
```

**4. saveCustomer**

```javascript
self.ctx.customerService.saveCustomer('your-customer-value', 'your-entitygroupids-value').subscribe(customer => {
  console.log('Save Customer:', customer);
});
```

**5. getCustomersByIds**

```javascript
self.ctx.customerService.getCustomersByIds('your-customerids-value').subscribe(customersByIds => {
  console.log('Get Customers By Ids:', customersByIds);
});
```

**6. getUserCustomers**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.customerService.getUserCustomers(pageLink).subscribe(userCustomers => {
  console.log('Get User Customers:', userCustomers);
});
```

**7. getAllCustomerInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.customerService.getAllCustomerInfos(true, pageLink).subscribe(allCustomerInfos => {
  console.log('Get All Customer Infos:', allCustomerInfos);
});
```

**8. getCustomerCustomerInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.customerService.getCustomerCustomerInfos(true, 'your-customer-id', pageLink).subscribe(customerCustomerInfos => {
  console.log('Get Customer Customer Infos:', customerCustomerInfos);
});
```

**9. getShortCustomerInfo**

```javascript
self.ctx.customerService.getShortCustomerInfo('your-customer-id').subscribe(shortCustomerInfo => {
  console.log('Get Short Customer Info:', shortCustomerInfo);
});
```
