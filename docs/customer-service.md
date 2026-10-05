# CUSTOMER SERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const customerService = $injector.get(self.ctx.servicesMap.get('customerService'));

// Alternative: Direct context access
const customerService = self.ctx.customerService;
```

**1. getCustomers**

```javascript
const customerService = self.ctx.customerService;
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
customerService.getCustomers(pageLink).subscribe(customers => {
  console.log('List of Customers:', customers);
});
```

**2. getCustomer**

```javascript
const customerService = self.ctx.customerService;
const customerId = 'your-customer-id';
customerService.getCustomer(customerId).subscribe(customer => {
  console.log('Get Customer:', customer);
});
```

**3. getCustomerInfo**

```javascript
const customerService = self.ctx.customerService;
const customerId = 'your-customer-id';
customerService.getCustomerInfo(customerId).subscribe(customerInfo => {
  console.log('Get Customer Info:', customerInfo);
});
```

**4. saveCustomer**

```javascript
const customerService = self.ctx.customerService;
const customer = {  // Customer object
  // ... set the fields you need
};
const entityGroupIds = ['your-entity-group-i-1', 'your-entity-group-i-2'];
const result = customerService.saveCustomer(customer, entityGroupIds);
console.log('Result:', result);
```

**5. getCustomersByIds**

```javascript
const customerService = self.ctx.customerService;
const customerIds = ['your-customer-i-1', 'your-customer-i-2'];
customerService.getCustomersByIds(customerIds).subscribe(customersBys => {
  console.log('List of Customers By Ids:', customersBys);
});
```

**6. getUserCustomers**

```javascript
const customerService = self.ctx.customerService;
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
customerService.getUserCustomers(pageLink).subscribe(userCustomers => {
  console.log('List of User Customers:', userCustomers);
});
```

**7. getAllCustomerInfos**

```javascript
const customerService = self.ctx.customerService;
const includeCustomers = true;
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
customerService.getAllCustomerInfos(includeCustomers, pageLink).subscribe(allCustomerInfos => {
  console.log('List of All Customer Infos:', allCustomerInfos);
});
```

**8. getCustomerCustomerInfos**

```javascript
const customerService = self.ctx.customerService;
const includeCustomers = true;
const customerId = 'your-customer-id';
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
customerService.getCustomerCustomerInfos(includeCustomers, customerId, pageLink).subscribe(customerCustomerInfos => {
  console.log('List of Customer Customer Infos:', customerCustomerInfos);
});
```

**9. getShortCustomerInfo**

```javascript
const customerService = self.ctx.customerService;
const customerId = 'your-customer-id';
customerService.getShortCustomerInfo(customerId).subscribe(shortCustomerInfo => {
  console.log('Get Short Customer Info:', shortCustomerInfo);
});
```
