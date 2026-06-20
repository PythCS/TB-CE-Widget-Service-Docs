# EVENT SERVICE

Part of [ThingsBoard CE Widget Service Documentation](../DOCUMENTATION.md)

### **EVENT SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const eventService = $injector.get(self.ctx.servicesMap.get('eventService'));
```

**1. getEvents**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
eventService.getEvents('your-entity-id', 'type', 'your-tenant-id', pageLink).subscribe(events => {
  console.log('Get Events: events');
});
```

**2. getFilterEvents**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const filters = filters;
eventService.getFilterEvents('your-entity-id', 'type', 'your-tenant-id', filters, pageLink).subscribe(filterevents => {
  console.log('Get Filter Events: filterevents');
});
```
