# Api Key

```javascript
// Service name: apiKey
// File: api-key.service.ts
```

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const apiKey = $injector.get(self.ctx.servicesMap.get('apiKey'));
```

### **1. saveApiKey**

```javascript
apiKey.saveApiKey(apiKey).subscribe(apiKey => {
  console.log('Api Key:', apiKey);
});
```

### **2. deleteApiKey**

```javascript
apiKey.deleteApiKey(id).subscribe(apiKey => {
  console.log('Api Key:', apiKey);
});
```

### **3. updateApiKeyDescription**

```javascript
apiKey.updateApiKeyDescription(id, description).subscribe(apiKey => {
  console.log('Api Key:', apiKey);
});
```

### **4. enableApiKey**

```javascript
apiKey.enableApiKey(id, enabledValue).subscribe(apiKey => {
  console.log('Api Key:', apiKey);
});
```

### **5. getUserApiKeys**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
apiKey.getUserApiKeys(pageLink).subscribe(users => {
  console.log('Users:', users);
});
```
