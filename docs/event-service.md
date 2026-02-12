# EVENT

## Service Injection

```javascript
const $injector = self.ctx.$scope.$injector;
const eventService = $injector.get(self.ctx.servicesMap.get('eventService'));
```

## Methods

### getEvents

```javascript
const entityId = { entityType: 'DEVICE', id: 'your-entity-id' };
const eventType = {
  // your eventType object
};
const tenantId = 'your-tenant-id';
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');

eventService.getEvents(entityId, eventType, tenantId, pageLink).subscribe(result => {
  console.log('Events:', result);
});
```

### getFilterEvents

```javascript
const entityId = { entityType: 'DEVICE', id: 'your-entity-id' };
const eventType = {
  // your eventType object
};
const tenantId = 'your-tenant-id';
const filters = {
  // your filters object
};
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');

eventService.getFilterEvents(entityId, eventType, tenantId, filters, pageLink).subscribe(result => {
  console.log('FilterEvents:', result);
});
```

