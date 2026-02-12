### **EVENT SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const eventservice = $injector.get(self.ctx.servicesMap.get('eventservice'));

```

**1. getEvents**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
eventservice.getEvents(pageLink, 'your-entity-id', eventType, 'your-tenant-id').subscribe(events => {
  console.log('Events:', events);
});
```

**2. getFilterEvents**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
eventservice.getFilterEvents(pageLink, 'your-entity-id', eventType, 'your-tenant-id', filters).subscribe(filterevents => {
  console.log('Filterevents:', filterevents);
});
```

