# EventService

### **EVENTSERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const eventService = $injector.get(self.ctx.servicesMap.get('eventService'));
```

**1. getEvents**

```javascript
eventService.getEvents('your-entity-id', 'your-eventtype', 'your-tenant-id', self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), { /* your config */ }).subscribe(event => {
  console.log('Events:', event);
});
```

**2. getFilterEvents**

```javascript
eventService.getFilterEvents('your-entity-id', 'your-eventtype', 'your-tenant-id', { /* your filters */ }, self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), { /* your config */ }).subscribe(filterevent => {
  console.log('Filter Events:', filterevent);
});
```
