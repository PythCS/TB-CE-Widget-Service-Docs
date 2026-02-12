### **CUSTOMER SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const customerservice = $injector.get(self.ctx.servicesMap.get('customerservice'));

// Alternative: Direct context access
const customerservice = self.ctx.customerService;
```

**1. getCustomers**

```javascript
const customerservice = self.ctx.customerService;
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
customerservice.getCustomers(pageLink).subscribe(customers => {
  console.log('Customers:', customers);
});
```

**2. getCustomer**

```javascript
const customerservice = self.ctx.customerService;
customerservice.getCustomer('your-customer-id').subscribe(customer => {
  console.log('Customer:', customer);
});
```

**3. getCustomersByIds**

```javascript
const customerservice = self.ctx.customerService;
customerservice.getCustomersByIds('your-customers-id').subscribe(customersbyids => {
  console.log('Customersbyids:', customersbyids);
});
```

**4. saveCustomer**

```javascript
const customerservice = self.ctx.customerService;
customerservice.saveCustomer(customer).subscribe(savecustomer => {
  console.log('Savecustomer:', savecustomer);
});
```

