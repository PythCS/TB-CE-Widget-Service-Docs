# ALARM

Alarm handling and notifications.

## Service Injection

```javascript
const $injector = self.ctx.$scope.$injector;
const alarmService = $injector.get(self.ctx.servicesMap.get('alarmService'));
```

## Methods

### getAlarm

```javascript
const alarmId = 'your-alarm-id';

alarmService.getAlarm(alarmId).subscribe(alarm => {
  console.log('Alarm:', alarm);
});
```

### getAlarmInfo

```javascript
const alarmId = 'your-alarm-id';

alarmService.getAlarmInfo(alarmId).subscribe(alarm => {
  console.log('Alarm:', alarm);
});
```

### saveAlarm

```javascript
const alarm = {
  // your alarm object
};

alarmService.saveAlarm(alarm).subscribe(alarm => {
  console.log('Alarm:', alarm);
});
```

### ackAlarm

```javascript
const alarmId = 'your-alarm-id';

alarmService.ackAlarm(alarmId).subscribe(alarm => {
  console.log('Alarm:', alarm);
});
```

### clearAlarm

```javascript
const alarmId = 'your-alarm-id';

alarmService.clearAlarm(alarmId).subscribe(alarm => {
  console.log('Alarm:', alarm);
});
```

### assignAlarm

```javascript
const alarmId = 'your-alarm-id';
const assigneeId = 'your-assignee-id';

alarmService.assignAlarm(alarmId, assigneeId).subscribe(result => {
  console.log('Result:', result);
});
```

### unassignAlarm

```javascript
const alarmId = 'your-alarm-id';

alarmService.unassignAlarm(alarmId).subscribe(result => {
  console.log('Result:', result);
});
```

### deleteAlarm

```javascript
const alarmId = 'your-alarm-id';

alarmService.deleteAlarm(alarmId).subscribe(result => {
  console.log('Result:', result);
});
```

### getAlarms

```javascript
const query = {
  // your query object
};

alarmService.getAlarms(query).subscribe(alarms => {
  console.log('Alarms:', alarms);
});
```

### getAlarmsV2

```javascript
const query = {
  // your query object
};

alarmService.getAlarmsV2(query).subscribe(alarms => {
  console.log('Alarms:', alarms);
});
```

### getAllAlarms

```javascript
const query = {
  // your query object
};

alarmService.getAllAlarms(query).subscribe(alarms => {
  console.log('Alarms:', alarms);
});
```

### getAllAlarmsV2

```javascript
const query = {
  // your query object
};

alarmService.getAllAlarmsV2(query).subscribe(alarms => {
  console.log('Alarms:', alarms);
});
```

### getHighestAlarmSeverity

```javascript
const entityId = { entityType: 'DEVICE', id: 'your-entity-id' };
const alarmSearchStatus = {
  // your alarmSearchStatus object
};
const alarmStatus = {
  // your alarmStatus object
};

alarmService.getHighestAlarmSeverity(entityId, alarmSearchStatus, alarmStatus).subscribe(alarm => {
  console.log('Alarm:', alarm);
});
```

### getAlarmTypes

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');

alarmService.getAlarmTypes(pageLink).subscribe(result => {
  console.log('AlarmTypes:', result);
});
```

