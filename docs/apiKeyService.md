# API KEY SERVICE

Part of [ThingsBoard CE Widget Service Documentation](../DOCUMENTATION.md)

### **API KEY SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const apiKeyService = $injector.get(self.ctx.servicesMap.get('apiKeyService'));
```

**1. saveApiKey**

```javascript
const apiKey = apiKey;
apiKeyService.saveApiKey(apiKey).subscribe(savedApiKey => {
  console.log('Save Api Key: savedApiKey');
});
```

**2. deleteApiKey**

```javascript
apiKeyService.deleteApiKey('your-id').subscribe(result => {
  console.log('Delete Api Key: result');
});
```

**3. updateApiKeyDescription**

```javascript
const description = description;
apiKeyService.updateApiKeyDescription('your-id', description).subscribe(result => {
  console.log('Update Api Key Description: result');
});
```

**4. enableApiKey**

```javascript
apiKeyService.enableApiKey('your-id', true).subscribe(result => {
  console.log('Enable Api Key: result');
});
```

**5. getUserApiKeys**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
apiKeyService.getUserApiKeys('your-user-id', pageLink).subscribe(userapikeys => {
  console.log('Get User Api Keys: userapikeys');
});
```
