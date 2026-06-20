# CUSTOMER SERVICE

Part of [ThingsBoard CE Widget Service Documentation](../DOCUMENTATION.md)

### **CUSTOMER SERVICE**

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
customerService.getCustomers(pageLink).subscribe(customers => {
  console.log('Get Customers: customers');
});
```

**2. getCustomer**

```javascript
customerService.getCustomer('your-customer-id').subscribe(customer => {
  console.log('Get Customer: customer');
});
```

**3. getCustomersByIds**

```javascript
customerService.getCustomersByIds('your-id').subscribe(customersbyids => {
  console.log('Get Customers By Ids: customersbyids');
});
```

**4. saveCustomer**

```javascript
const customer = customer;
customerService.saveCustomer(customer).subscribe(savedCustomer => {
  console.log('Save Customer: savedCustomer');
});
```
