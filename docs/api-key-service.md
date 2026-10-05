# API KEY SERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const apiKeyService = $injector.get(self.ctx.servicesMap.get('apiKeyService'));
```

**1. saveApiKey**

```javascript
const $injector = self.ctx.$scope.$injector;
const apiKeyService = $injector.get(self.ctx.servicesMap.get('apiKeyService'));
const apiKey = {  // ApiKeyInfo object
  // ... set the fields you need
};
apiKeyService.saveApiKey(apiKey).subscribe(savedApiKey => {
  console.log('Saved Api Key:', savedApiKey);
});
```

**2. deleteApiKey**

```javascript
const $injector = self.ctx.$scope.$injector;
const apiKeyService = $injector.get(self.ctx.servicesMap.get('apiKeyService'));
const id = 'your-id';
apiKeyService.deleteApiKey(id).subscribe(result => {
  console.log('Delete Api Key result:', result);
});
```

**3. updateApiKeyDescription**

```javascript
const $injector = self.ctx.$scope.$injector;
const apiKeyService = $injector.get(self.ctx.servicesMap.get('apiKeyService'));
const id = 'your-id';
const description = 'your-description';
apiKeyService.updateApiKeyDescription(id, description).subscribe(savedApiKeyDescription => {
  console.log('Saved Api Key Description:', savedApiKeyDescription);
});
```

**4. enableApiKey**

```javascript
const $injector = self.ctx.$scope.$injector;
const apiKeyService = $injector.get(self.ctx.servicesMap.get('apiKeyService'));
const id = 'your-id';
const enabledValue = true;
apiKeyService.enableApiKey(id, enabledValue).subscribe(enableApiKey => {
  console.log('Enable Api Key:', enableApiKey);
});
```

**5. getUserApiKeys**

```javascript
const $injector = self.ctx.$scope.$injector;
const apiKeyService = $injector.get(self.ctx.servicesMap.get('apiKeyService'));
const userId = 'your-user-id';
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
apiKeyService.getUserApiKeys(userId, pageLink).subscribe(userApiKeys => {
  console.log('List of User Api Keys:', userApiKeys);
});
```
