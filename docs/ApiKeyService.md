# ApiKeyService

### **APIKEYSERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const apiKeyService = $injector.get(self.ctx.servicesMap.get('apiKeyService'));
```

**1. saveApiKey**

```javascript
apiKeyService.saveApiKey({ /* your apiKey */ }, { /* your config */ }).subscribe(savedApiKey => {
  console.log('Saved ApiKey:', savedApiKey);
});
```

**2. deleteApiKey**

```javascript
apiKeyService.deleteApiKey('your-id', { /* your config */ }).subscribe(result => {
  console.log('Delete Result:', result);
});
```

**3. updateApiKeyDescription**

```javascript
apiKeyService.updateApiKeyDescription('your-id', 'your-description', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**4. enableApiKey**

```javascript
apiKeyService.enableApiKey('your-id', true, { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**5. getUserApiKeys**

```javascript
apiKeyService.getUserApiKeys('your-user-id', self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), { /* your config */ }).subscribe(uerapikey => {
  console.log('User Api Keys:', uerapikey);
});
```
