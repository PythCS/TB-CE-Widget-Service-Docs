# Customer

```javascript
// Service name: customer
// File: customer.service.ts
```

TO INJECT THE SERVICE:

```javascript
// Via direct context access (preferred)
const customer = self.ctx.customerService;
```

```javascript
// Via injector
const $injector = self.ctx.$scope.$injector;
const customer = $injector.get(self.ctx.servicesMap.get('customer'));
```

### **1. getCustomers**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
customer.getCustomers(pageLink).subscribe(customers => {
  console.log('Customers:', customers);
});
```

### **2. getCustomer**

```javascript
customer.getCustomer(customerId).subscribe(customer => {
  console.log('Customer:', customer);
});
```

### **3. getCustomersByIds**

```javascript
customer.getCustomersByIds(customerIds).subscribe(customers => {
  console.log('Customers:', customers);
});
```

### **4. saveCustomer**

```javascript
customer.saveCustomer(customer).subscribe(customer => {
  console.log('Customer:', customer);
});
```
