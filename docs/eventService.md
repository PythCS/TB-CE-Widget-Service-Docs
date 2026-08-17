# EVENT SERVICE

Part of the [ThingsBoard CE Widget Services Documentation](../DOCUMENTATION.md).

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const eventService = $injector.get(self.ctx.servicesMap.get('eventService'));
```

**1. getEvents**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
eventService.getEvents('your-entity-id', 'your-eventtype-value', 'your-tenant-id', pageLink).subscribe(events => {
  console.log('Get Events:', events);
});
```

**2. getFilterEvents**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
eventService.getFilterEvents('your-entity-id', 'your-eventtype-value', 'your-tenant-id', 'your-filters-value', pageLink).subscribe(filterEvents => {
  console.log('Get Filter Events:', filterEvents);
});
```
