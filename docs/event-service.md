# EVENT SERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const eventService = $injector.get(self.ctx.servicesMap.get('eventService'));
```

**1. getEvents**

```javascript
const $injector = self.ctx.$scope.$injector;
const eventService = $injector.get(self.ctx.servicesMap.get('eventService'));
const entityId = {  // EntityId object
  // ... set the fields you need
};
const eventType = 'eventType';  // e.g. one of the allowed EventType
const tenantId = 'your-tenant-id';
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
eventService.getEvents(entityId, eventType, tenantId, pageLink).subscribe(events => {
  console.log('List of Events:', events);
});
```

**2. getFilterEvents**

```javascript
const $injector = self.ctx.$scope.$injector;
const eventService = $injector.get(self.ctx.servicesMap.get('eventService'));
const entityId = {  // EntityId object
  // ... set the fields you need
};
const eventType = 'eventType';  // e.g. one of the allowed EventType
const tenantId = 'your-tenant-id';
const filters = {  // FilterEventBody object
  // ... set the fields you need
};
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
eventService.getFilterEvents(entityId, eventType, tenantId, filters, pageLink).subscribe(filterEvents => {
  console.log('List of Filter Events:', filterEvents);
});
```
