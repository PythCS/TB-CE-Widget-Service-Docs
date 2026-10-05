# SECRET STORAGE SERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const secretStorageService = $injector.get(self.ctx.servicesMap.get('secretStorageService'));
```

**1. getSecrets**

```javascript
const $injector = self.ctx.$scope.$injector;
const secretStorageService = $injector.get(self.ctx.servicesMap.get('secretStorageService'));
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
secretStorageService.getSecrets(pageLink).subscribe(secrets => {
  console.log('List of Secrets:', secrets);
});
```

**2. saveSecret**

```javascript
const $injector = self.ctx.$scope.$injector;
const secretStorageService = $injector.get(self.ctx.servicesMap.get('secretStorageService'));
const secret = {  // SecretStorageInfo object
  // ... set the fields you need
};
secretStorageService.saveSecret(secret).subscribe(savedSecret => {
  console.log('Saved Secret:', savedSecret);
});
```

**3. updateSecretDescription**

```javascript
const $injector = self.ctx.$scope.$injector;
const secretStorageService = $injector.get(self.ctx.servicesMap.get('secretStorageService'));
const secretId = 'your-secret-id';
const description = 'your-description';
secretStorageService.updateSecretDescription(secretId, description).subscribe(savedSecretDescription => {
  console.log('Saved Secret Description:', savedSecretDescription);
});
```

**4. updateSecretValue**

```javascript
const $injector = self.ctx.$scope.$injector;
const secretStorageService = $injector.get(self.ctx.servicesMap.get('secretStorageService'));
const secretId = 'your-secret-id';
const value = 'your-value';
secretStorageService.updateSecretValue(secretId, value).subscribe(savedSecretValue => {
  console.log('Saved Secret Value:', savedSecretValue);
});
```

**5. getSecretByName**

```javascript
const $injector = self.ctx.$scope.$injector;
const secretStorageService = $injector.get(self.ctx.servicesMap.get('secretStorageService'));
const name = 'name-value';
secretStorageService.getSecretByName(name).subscribe(secretByName => {
  console.log('Get Secret By Name:', secretByName);
});
```
