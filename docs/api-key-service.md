# API KEY

## Service Injection

```javascript
const $injector = self.ctx.$scope.$injector;
const apiKeyService = $injector.get(self.ctx.servicesMap.get('apiKeyService'));
```

## Methods

### saveApiKey

```javascript
const apiKey = {
  // your apiKey object
};

apiKeyService.saveApiKey(apiKey).subscribe(savedResult => {
  console.log('Saved Result:', savedResult);
});
```

### deleteApiKey

```javascript
const id = 'your--id';

apiKeyService.deleteApiKey(id).subscribe(result => {
  console.log('Result:', result);
});
```

### updateApiKeyDescription

```javascript
const id = 'your--id';
const description = 'your-description';

apiKeyService.updateApiKeyDescription(id, description).subscribe(info => {
  console.log('Info:', info);
});
```

### enableApiKey

```javascript
const id = 'your--id';
const enabledValue = true;

apiKeyService.enableApiKey(id, enabledValue).subscribe(info => {
  console.log('Info:', info);
});
```

### getUserApiKeys

```javascript
const userId = 'your-user-id';
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');

apiKeyService.getUserApiKeys(userId, pageLink).subscribe(info => {
  console.log('Info:', info);
});
```

