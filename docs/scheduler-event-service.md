# SCHEDULER EVENT SERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const schedulerEventService = $injector.get(self.ctx.servicesMap.get('schedulerEventService'));
```

**1. getSchedulerEvents**

```javascript
const $injector = self.ctx.$scope.$injector;
const schedulerEventService = $injector.get(self.ctx.servicesMap.get('schedulerEventService'));
const type = 'value';
schedulerEventService.getSchedulerEvents(type).subscribe(schedulerEvents => {
  console.log('List of Scheduler Events:', schedulerEvents);
});
```

**2. getSchedulerEventsByPageLink**

```javascript
const $injector = self.ctx.$scope.$injector;
const schedulerEventService = $injector.get(self.ctx.servicesMap.get('schedulerEventService'));
const type = 'type-value';
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const edgeId = 'your-edge-id';
schedulerEventService.getSchedulerEventsByPageLink(type, pageLink, edgeId).subscribe(schedulerEventsByPageLinks => {
  console.log('List of Scheduler Events By Page Links:', schedulerEventsByPageLinks);
});
```

**3. getCalendarSchedulerEvents**

```javascript
const $injector = self.ctx.$scope.$injector;
const schedulerEventService = $injector.get(self.ctx.servicesMap.get('schedulerEventService'));
const type = 'type-value';
const startTime = 10;
const endTime = 10;
const textSearch = 'your-text-search';
const edgeId = 'your-edge-id';
schedulerEventService.getCalendarSchedulerEvents(type, startTime, endTime, textSearch, edgeId).subscribe(calendarSchedulerEvents => {
  console.log('List of Calendar Scheduler Events:', calendarSchedulerEvents);
});
```

**4. getSchedulerEventsByIds**

```javascript
const $injector = self.ctx.$scope.$injector;
const schedulerEventService = $injector.get(self.ctx.servicesMap.get('schedulerEventService'));
const schedulerEventIds = ['your-scheduler-event-i-1', 'your-scheduler-event-i-2'];
schedulerEventService.getSchedulerEventsByIds(schedulerEventIds).subscribe(schedulerEventsBys => {
  console.log('List of Scheduler Events By Ids:', schedulerEventsBys);
});
```

**5. getSchedulerEventInfo**

```javascript
const $injector = self.ctx.$scope.$injector;
const schedulerEventService = $injector.get(self.ctx.servicesMap.get('schedulerEventService'));
const schedulerEventId = 'your-scheduler-event-id';
schedulerEventService.getSchedulerEventInfo(schedulerEventId).subscribe(schedulerEventInfo => {
  console.log('Get Scheduler Event Info:', schedulerEventInfo);
});
```

**6. getSchedulerEvent**

```javascript
const $injector = self.ctx.$scope.$injector;
const schedulerEventService = $injector.get(self.ctx.servicesMap.get('schedulerEventService'));
const schedulerEventId = 'your-scheduler-event-id';
schedulerEventService.getSchedulerEvent(schedulerEventId).subscribe(schedulerEvent => {
  console.log('Get Scheduler Event:', schedulerEvent);
});
```

**7. saveSchedulerEvent**

```javascript
const $injector = self.ctx.$scope.$injector;
const schedulerEventService = $injector.get(self.ctx.servicesMap.get('schedulerEventService'));
const schedulerEvent = {  // SchedulerEvent object
  // ... set the fields you need
};
schedulerEventService.saveSchedulerEvent(schedulerEvent).subscribe(savedSchedulerEvent => {
  console.log('Saved Scheduler Event:', savedSchedulerEvent);
});
```

**8. getEdgeSchedulerEvents**

```javascript
const $injector = self.ctx.$scope.$injector;
const schedulerEventService = $injector.get(self.ctx.servicesMap.get('schedulerEventService'));
const edgeId = 'your-edge-id';
schedulerEventService.getEdgeSchedulerEvents(edgeId).subscribe(edgeSchedulerEvents => {
  console.log('List of Edge Scheduler Events:', edgeSchedulerEvents);
});
```

**9. assignSchedulerEventToEdge**

```javascript
const $injector = self.ctx.$scope.$injector;
const schedulerEventService = $injector.get(self.ctx.servicesMap.get('schedulerEventService'));
const edgeId = 'your-edge-id';
const schedulerEventId = 'your-scheduler-event-id';
schedulerEventService.assignSchedulerEventToEdge(edgeId, schedulerEventId).subscribe(assignSchedulerEventToEdge => {
  console.log('Assign Scheduler Event To Edge:', assignSchedulerEventToEdge);
});
```

**10. getScheduledReports**

```javascript
const $injector = self.ctx.$scope.$injector;
const schedulerEventService = $injector.get(self.ctx.servicesMap.get('schedulerEventService'));
const query = {  // ReportQuery object
  // ... set the fields you need
};
schedulerEventService.getScheduledReports(query).subscribe(scheduledReports => {
  console.log('List of Scheduled Reports:', scheduledReports);
});
```
