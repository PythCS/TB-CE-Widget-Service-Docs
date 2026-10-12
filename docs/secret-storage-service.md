# SECRET STORAGE SERVICE

Part of the [ThingsBoard CE Widget Services Documentation](../DOCUMENTATION.md).

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const secretStorageService = $injector.get(self.ctx.servicesMap.get('secretStorageService'));
```

**1. getSecrets**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
secretStorageService.getSecrets(pageLink).subscribe(secrets => {
  console.log('Get Secrets:', secrets);
});
```

**2. saveSecret**

```javascript
secretStorageService.saveSecret('your-secret-value').subscribe(secret => {
  console.log('Save Secret:', secret);
});
```

**3. updateSecretDescription**

```javascript
secretStorageService.updateSecretDescription('your-secret-id', 'your-description-value').subscribe(result => {
  console.log('Update Secret Description:', result);
});
```

**4. updateSecretValue**

```javascript
secretStorageService.updateSecretValue('your-secret-id', 'your-value-value').subscribe(result => {
  console.log('Update Secret Value:', result);
});
```

**5. getSecretByName**

```javascript
secretStorageService.getSecretByName('your-name-value').subscribe(secretByName => {
  console.log('Get Secret By Name:', secretByName);
});
```
