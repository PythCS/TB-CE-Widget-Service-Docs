# ApiKeyService

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const apiKeyService = $injector.get(self.ctx.servicesMap.get('ApiKeyService'));
```

**1. saveApiKey**

```javascript
apiKeyService.saveApiKey('your-api-key').subscribe(result => {
  console.log('Saved  Api Key result:', result);
});
```

**2. deleteApiKey**

```javascript
apiKeyService.deleteApiKey('your--id').subscribe(result => {
  console.log('Operation completed:', result);
});
```

**3. updateApiKeyDescription**

```javascript
apiKeyService.updateApiKeyDescription('your--id', 'your-description-value').subscribe(result => {
  console.log('update Api Key Description result:', result);
});
```

**4. enableApiKey**

```javascript
apiKeyService.enableApiKey('your--id', true).subscribe(result => {
  console.log('enable Api Key result:', result);
});
```

**5. getUserApiKeys**

```javascript
apiKeyService.getUserApiKeys('your-user-id', self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder')).subscribe(users => {
  console.log('Fetched  User Api Keys users:', users);
});
```
