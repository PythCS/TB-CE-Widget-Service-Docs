# Event

```javascript
// Service name: event
// File: event.service.ts
```

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const event = $injector.get(self.ctx.servicesMap.get('event'));
```

### **1. getEvents**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
event.getEvents(pageLink).subscribe(events => {
  console.log('Events:', events);
});
```

### **2. getFilterEvents**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
event.getFilterEvents(pageLink).subscribe(events => {
  console.log('Events:', events);
});
```
