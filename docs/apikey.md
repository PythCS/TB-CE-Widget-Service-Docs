### **API KEY SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const apikeyservice = $injector.get(self.ctx.servicesMap.get('apikeyservice'));

```

**1. saveApiKey**

```javascript
apikeyservice.saveApiKey(apiKey).subscribe(saveapikey => {
  console.log('Saveapikey:', saveapikey);
});
```

**2. deleteApiKey**

```javascript
apikeyservice.deleteApiKey('your-id-id').subscribe(deleteapikey => {
  console.log('Deleteapikey:', deleteapikey);
});
```

**3. updateApiKeyDescription**

```javascript
apikeyservice.updateApiKeyDescription('your-id-id', 'your-description').subscribe(updateapikeydescription => {
  console.log('Updateapikeydescription:', updateapikeydescription);
});
```

**4. enableApiKey**

```javascript
apikeyservice.enableApiKey('your-id-id', true).subscribe(enableapikey => {
  console.log('Enableapikey:', enableapikey);
});
```

**5. getUserApiKeys**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
apikeyservice.getUserApiKeys(pageLink, 'your-user-id').subscribe(userapikeys => {
  console.log('Userapikeys:', userapikeys);
});
```

