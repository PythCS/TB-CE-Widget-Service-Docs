# ALARM SERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const alarmService = $injector.get(self.ctx.servicesMap.get('alarmService'));
```

**1. getAlarm**

```javascript
const $injector = self.ctx.$scope.$injector;
const alarmService = $injector.get(self.ctx.servicesMap.get('alarmService'));
const alarmId = 'your-alarm-id';
alarmService.getAlarm(alarmId).subscribe(alarm => {
  console.log('Get Alarm:', alarm);
});
```

**2. getAlarmInfo**

```javascript
const $injector = self.ctx.$scope.$injector;
const alarmService = $injector.get(self.ctx.servicesMap.get('alarmService'));
const alarmId = 'your-alarm-id';
alarmService.getAlarmInfo(alarmId).subscribe(alarmInfo => {
  console.log('Get Alarm Info:', alarmInfo);
});
```

**3. saveAlarm**

```javascript
const $injector = self.ctx.$scope.$injector;
const alarmService = $injector.get(self.ctx.servicesMap.get('alarmService'));
const alarm = {  // Alarm object
  // ... set the fields you need
};
alarmService.saveAlarm(alarm).subscribe(savedAlarm => {
  console.log('Saved Alarm:', savedAlarm);
});
```

**4. ackAlarm**

```javascript
const $injector = self.ctx.$scope.$injector;
const alarmService = $injector.get(self.ctx.servicesMap.get('alarmService'));
const alarmId = 'your-alarm-id';
alarmService.ackAlarm(alarmId).subscribe(ackAlarm => {
  console.log('Ack Alarm:', ackAlarm);
});
```

**5. clearAlarm**

```javascript
const $injector = self.ctx.$scope.$injector;
const alarmService = $injector.get(self.ctx.servicesMap.get('alarmService'));
const alarmId = 'your-alarm-id';
alarmService.clearAlarm(alarmId).subscribe(clearAlarm => {
  console.log('Clear Alarm:', clearAlarm);
});
```

**6. assignAlarm**

```javascript
const $injector = self.ctx.$scope.$injector;
const alarmService = $injector.get(self.ctx.servicesMap.get('alarmService'));
const alarmId = 'your-alarm-id';
const assigneeId = 'your-assignee-id';
alarmService.assignAlarm(alarmId, assigneeId).subscribe(assignAlarm => {
  console.log('Assign Alarm:', assignAlarm);
});
```

**7. unassignAlarm**

```javascript
const $injector = self.ctx.$scope.$injector;
const alarmService = $injector.get(self.ctx.servicesMap.get('alarmService'));
const alarmId = 'your-alarm-id';
alarmService.unassignAlarm(alarmId).subscribe(unassignAlarm => {
  console.log('Unassign Alarm:', unassignAlarm);
});
```

**8. deleteAlarm**

```javascript
const $injector = self.ctx.$scope.$injector;
const alarmService = $injector.get(self.ctx.servicesMap.get('alarmService'));
const alarmId = 'your-alarm-id';
alarmService.deleteAlarm(alarmId).subscribe(result => {
  console.log('Delete Alarm result:', result);
});
```

**9. getAlarms**

```javascript
const $injector = self.ctx.$scope.$injector;
const alarmService = $injector.get(self.ctx.servicesMap.get('alarmService'));
const query = {  // AlarmQuery object
  // ... set the fields you need
};
alarmService.getAlarms(query).subscribe(alarms => {
  console.log('List of Alarms:', alarms);
});
```

**10. getAlarmsV2**

```javascript
const $injector = self.ctx.$scope.$injector;
const alarmService = $injector.get(self.ctx.servicesMap.get('alarmService'));
const query = {  // AlarmQueryV2 object
  // ... set the fields you need
};
alarmService.getAlarmsV2(query).subscribe(alarmsV2s => {
  console.log('List of Alarms V2s:', alarmsV2s);
});
```

**11. getAllAlarms**

```javascript
const $injector = self.ctx.$scope.$injector;
const alarmService = $injector.get(self.ctx.servicesMap.get('alarmService'));
const query = {  // AlarmQuery object
  // ... set the fields you need
};
alarmService.getAllAlarms(query).subscribe(allAlarms => {
  console.log('List of All Alarms:', allAlarms);
});
```

**12. getAllAlarmsV2**

```javascript
const $injector = self.ctx.$scope.$injector;
const alarmService = $injector.get(self.ctx.servicesMap.get('alarmService'));
const query = {  // AlarmQueryV2 object
  // ... set the fields you need
};
alarmService.getAllAlarmsV2(query).subscribe(allAlarmsV2s => {
  console.log('List of All Alarms V2s:', allAlarmsV2s);
});
```

**13. getHighestAlarmSeverity**

```javascript
const $injector = self.ctx.$scope.$injector;
const alarmService = $injector.get(self.ctx.servicesMap.get('alarmService'));
const entityId = {  // EntityId object
  // ... set the fields you need
};
const alarmSearchStatus = {  // AlarmSearchStatus object
  // ... set the fields you need
};
const alarmStatus = {  // AlarmStatus object
  // ... set the fields you need
};
alarmService.getHighestAlarmSeverity(entityId, alarmSearchStatus, alarmStatus).subscribe(highestAlarmSeverity => {
  console.log('Get Highest Alarm Severity:', highestAlarmSeverity);
});
```

**14. getAlarmTypes**

```javascript
const $injector = self.ctx.$scope.$injector;
const alarmService = $injector.get(self.ctx.servicesMap.get('alarmService'));
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
alarmService.getAlarmTypes(pageLink).subscribe(alarmTypes => {
  console.log('List of Alarm Types:', alarmTypes);
});
```
