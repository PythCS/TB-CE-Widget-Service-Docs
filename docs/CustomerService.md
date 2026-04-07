# CustomerService

### **CUSTOMERSERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const customerService = $injector.get(self.ctx.servicesMap.get('customerService'));

// Alternative: Direct context access
const customerService = self.ctx.customerService;
```

**1. getCustomers**

```javascript
customerService.getCustomers(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), { /* your config */ }).subscribe(cutomer => {
  console.log('Customers:', cutomer);
});
```

**2. getCustomer**

```javascript
customerService.getCustomer('your-customer-id', { /* your config */ }).subscribe(customer => {
  console.log('Customer:', customer);
});
```

**3. getCustomersByIds**

```javascript
customerService.getCustomersByIds(['id1', 'id2'], { /* your config */ }).subscribe(cutomerbyid => {
  console.log('Customers By Ids:', cutomerbyid);
});
```

**4. saveCustomer**

```javascript
customerService.saveCustomer({ /* your customer object */ }, { /* your config */ }).subscribe(savedCustomer => {
  console.log('Saved Customer:', savedCustomer);
});
```
