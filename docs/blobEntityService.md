# BLOB ENTITY SERVICE

Part of the [ThingsBoard CE Widget Services Documentation](../DOCUMENTATION.md).

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const blobEntityService = $injector.get(self.ctx.servicesMap.get('blobEntityService'));
```

**1. getBlobEntityInfo**

```javascript
blobEntityService.getBlobEntityInfo('your-blobentity-id').subscribe(blobEntityInfo => {
  console.log('Get Blob Entity Info:', blobEntityInfo);
});
```

**2. getBlobEntities**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
blobEntityService.getBlobEntities(pageLink, 'your-type-value').subscribe(blobEntities => {
  console.log('Get Blob Entities:', blobEntities);
});
```

**3. getBlobEntitiesByIds**

```javascript
blobEntityService.getBlobEntitiesByIds('your-blobentityids-value').subscribe(blobEntitiesByIds => {
  console.log('Get Blob Entities By Ids:', blobEntitiesByIds);
});
```

**4. downloadBlobEntity**

```javascript
blobEntityService.downloadBlobEntity('your-blobentity-id').subscribe(downloadBlobEntity => {
  console.log('Download Blob Entity:', downloadBlobEntity);
});
```
