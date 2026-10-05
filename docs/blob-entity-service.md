# BLOB ENTITY SERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const blobEntityService = $injector.get(self.ctx.servicesMap.get('blobEntityService'));
```

**1. getBlobEntityInfo**

```javascript
const $injector = self.ctx.$scope.$injector;
const blobEntityService = $injector.get(self.ctx.servicesMap.get('blobEntityService'));
const blobEntityId = 'your-blob-entity-id';
blobEntityService.getBlobEntityInfo(blobEntityId).subscribe(blobEntityInfo => {
  console.log('Get Blob Entity Info:', blobEntityInfo);
});
```

**2. getBlobEntities**

```javascript
const $injector = self.ctx.$scope.$injector;
const blobEntityService = $injector.get(self.ctx.servicesMap.get('blobEntityService'));
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const type = 'value';
blobEntityService.getBlobEntities(pageLink, type).subscribe(blobEntities => {
  console.log('List of Blob Entities:', blobEntities);
});
```

**3. getBlobEntitiesByIds**

```javascript
const $injector = self.ctx.$scope.$injector;
const blobEntityService = $injector.get(self.ctx.servicesMap.get('blobEntityService'));
const blobEntityIds = ['your-blob-entity-i-1', 'your-blob-entity-i-2'];
blobEntityService.getBlobEntitiesByIds(blobEntityIds).subscribe(blobEntitiesBys => {
  console.log('List of Blob Entities By Ids:', blobEntitiesBys);
});
```

**4. downloadBlobEntity**

```javascript
const $injector = self.ctx.$scope.$injector;
const blobEntityService = $injector.get(self.ctx.servicesMap.get('blobEntityService'));
const blobEntityId = 'your-blob-entity-id';
blobEntityService.downloadBlobEntity(blobEntityId).subscribe(downloadBlobEntity => {
  console.log('Download Blob Entity:', downloadBlobEntity);
});
```
