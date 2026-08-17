# API KEY SERVICE

Part of the [ThingsBoard CE Widget Services Documentation](../DOCUMENTATION.md).

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const apiKeyService = $injector.get(self.ctx.servicesMap.get('apiKeyService'));
```

**1. saveApiKey**

```javascript
apiKeyService.saveApiKey('your-api-key').subscribe(apiKey => {
  console.log('Save Api Key:', apiKey);
});
```

**2. deleteApiKey**

```javascript
apiKeyService.deleteApiKey('your--id').subscribe(result => {
  console.log('Delete Api Key:', result);
});
```

**3. updateApiKeyDescription**

```javascript
apiKeyService.updateApiKeyDescription('your--id', 'your-description-value').subscribe(apiKeyDescription => {
  console.log('Update Api Key Description:', apiKeyDescription);
});
```

**4. enableApiKey**

```javascript
apiKeyService.enableApiKey('your--id', true).subscribe(enableApiKey => {
  console.log('Enable Api Key:', enableApiKey);
});
```

**5. getUserApiKeys**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
apiKeyService.getUserApiKeys('your-user-id', pageLink).subscribe(userApiKeys => {
  console.log('Get User Api Keys:', userApiKeys);
});
```
