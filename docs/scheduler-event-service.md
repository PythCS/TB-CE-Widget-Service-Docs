# SCHEDULER EVENT SERVICE

Part of the [ThingsBoard CE Widget Services Documentation](../DOCUMENTATION.md).

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const schedulerEventService = $injector.get(self.ctx.servicesMap.get('schedulerEventService'));
```

**1. getSchedulerEvents**

```javascript
schedulerEventService.getSchedulerEvents('your-type-value').subscribe(schedulerEvents => {
  console.log('Get Scheduler Events:', schedulerEvents);
});
```

**2. getSchedulerEventsByPageLink**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
schedulerEventService.getSchedulerEventsByPageLink('your-type-value', pageLink, 'your-edge-id').subscribe(schedulerEventsByPageLink => {
  console.log('Get Scheduler Events By Page Link:', schedulerEventsByPageLink);
});
```

**3. getCalendarSchedulerEvents**

```javascript
schedulerEventService.getCalendarSchedulerEvents('your-type-value', 0, 0, 'your-textsearch-value', 'your-edge-id').subscribe(calendarSchedulerEvents => {
  console.log('Get Calendar Scheduler Events:', calendarSchedulerEvents);
});
```

**4. getSchedulerEventsByIds**

```javascript
schedulerEventService.getSchedulerEventsByIds('your-schedulereventids-value').subscribe(schedulerEventsByIds => {
  console.log('Get Scheduler Events By Ids:', schedulerEventsByIds);
});
```

**5. getSchedulerEventInfo**

```javascript
schedulerEventService.getSchedulerEventInfo('your-schedulerevent-id').subscribe(schedulerEventInfo => {
  console.log('Get Scheduler Event Info:', schedulerEventInfo);
});
```

**6. getSchedulerEvent**

```javascript
schedulerEventService.getSchedulerEvent('your-schedulerevent-id').subscribe(schedulerEvent => {
  console.log('Get Scheduler Event:', schedulerEvent);
});
```

**7. saveSchedulerEvent**

```javascript
schedulerEventService.saveSchedulerEvent('your-schedulerevent-value').subscribe(schedulerEvent => {
  console.log('Save Scheduler Event:', schedulerEvent);
});
```

**8. getEdgeSchedulerEvents**

```javascript
schedulerEventService.getEdgeSchedulerEvents('your-edge-id').subscribe(edgeSchedulerEvents => {
  console.log('Get Edge Scheduler Events:', edgeSchedulerEvents);
});
```

**9. assignSchedulerEventToEdge**

```javascript
schedulerEventService.assignSchedulerEventToEdge('your-edge-id', 'your-schedulerevent-id').subscribe(schedulerEventToEdge => {
  console.log('Assign Scheduler Event To Edge:', schedulerEventToEdge);
});
```

**10. getScheduledReports**

```javascript
schedulerEventService.getScheduledReports('your-query-value').subscribe(scheduledReports => {
  console.log('Get Scheduled Reports:', scheduledReports);
});
```
