# EventService

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const eventService = $injector.get(self.ctx.servicesMap.get('EventService'));
```

**1. getEvents**

```javascript
eventService.getEvents('your-entity-id', 'your-eventtype-value', 'your-tenant-id', self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder')).subscribe(result => {
  console.log('Fetched  Events result:', result);
});
```

**2. getFilterEvents**

```javascript
eventService.getFilterEvents('your-entity-id', 'your-eventtype-value', 'your-tenant-id', 'your-filters-value', self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder')).subscribe(result => {
  console.log('Fetched  Filter Events result:', result);
});
```
