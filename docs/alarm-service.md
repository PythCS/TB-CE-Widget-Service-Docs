# Alarm Service

Manage alarms, acknowledgments, and alarm-related operations in ThingsBoard.

## Injection

```javascript
const $injector = self.ctx.$scope.$injector;
const alarmService = $injector.get(self.ctx.servicesMap.get('alarmService'));
```

## Methods

**1. getAlarm**

```javascript
const alarmId = 'your-alarm-id';

alarmService.getAlarm(alarmId).subscribe(alarm => {
  console.log('Alarm:', alarm);
});
```

**2. getAlarmInfo**

```javascript
const alarmId = 'your-alarm-id';

alarmService.getAlarmInfo(alarmId).subscribe(alarmInfo => {
  console.log('Alarm Information:', alarmInfo);
});
```

**3. saveAlarm**

```javascript
const alarm = {
  type: 'Temperature',
  severity: 'CRITICAL',
  originator: { entityType: 'DEVICE', id: 'your-device-id' }
};

alarmService.saveAlarm(alarm).subscribe(savedAlarm => {
  console.log('Saved Alarm:', savedAlarm);
});
```

**4. ackAlarm**

```javascript
const alarmId = 'your-alarm-id';

alarmService.ackAlarm(alarmId).subscribe(alarmInfo => {
  console.log('Acknowledged Alarm:', alarmInfo);
});
```

**5. clearAlarm**

```javascript
const alarmId = 'your-alarm-id';

alarmService.clearAlarm(alarmId).subscribe(alarmInfo => {
  console.log('Cleared Alarm:', alarmInfo);
});
```

**6. assignAlarm**

```javascript
const alarmId = 'your-alarm-id';
const assigneeId = 'your-user-id';

alarmService.assignAlarm(alarmId, assigneeId).subscribe(() => {
  console.log('Alarm assigned successfully');
});
```

**7. unassignAlarm**

```javascript
const alarmId = 'your-alarm-id';

alarmService.unassignAlarm(alarmId).subscribe(() => {
  console.log('Alarm unassigned successfully');
});
```

**8. deleteAlarm**

```javascript
const alarmId = 'your-alarm-id';

alarmService.deleteAlarm(alarmId).subscribe(success => {
  console.log('Alarm deleted:', success);
});
```

**9. getAlarms**

```javascript
const query = {
  entityFilter: {
    type: 'singleEntity',
    singleEntity: { entityType: 'DEVICE', id: 'your-device-id' }
  },
  pageLink: self.ctx.pageLink(10, 0)
};

alarmService.getAlarms(query).subscribe(response => {
  console.log('Alarms:', response.data);
});
```

**10. getAlarmsV2**

```javascript
const query = {
  entityFilter: {
    type: 'singleEntity',
    singleEntity: { entityType: 'DEVICE', id: 'your-device-id' }
  },
  pageLink: self.ctx.pageLink(10, 0)
};

alarmService.getAlarmsV2(query).subscribe(response => {
  console.log('Alarms V2:', response.data);
});
```

**11. getAllAlarms**

```javascript
const query = {
  entityFilter: {
    type: 'entitiesByType',
    entityType: 'DEVICE'
  },
  pageLink: self.ctx.pageLink(10, 0)
};

alarmService.getAllAlarms(query).subscribe(response => {
  console.log('All Alarms:', response.data);
});
```

**12. getAllAlarmsV2**

```javascript
const query = {
  entityFilter: {
    type: 'entitiesByType',
    entityType: 'DEVICE'
  },
  pageLink: self.ctx.pageLink(10, 0)
};

alarmService.getAllAlarmsV2(query).subscribe(response => {
  console.log('All Alarms V2:', response.data);
});
```

**13. getHighestAlarmSeverity**

```javascript
const entityId = { entityType: 'DEVICE', id: 'your-device-id' };
const alarmSearchStatus = 'ACTIVE';
const alarmStatus = 'ACTIVE_UNACK';

alarmService.getHighestAlarmSeverity(entityId, alarmSearchStatus, alarmStatus).subscribe(severity => {
  console.log('Highest Alarm Severity:', severity);
});
```

**14. getAlarmTypes**

```javascript
const pageLink = self.ctx.pageLink(10, 0);

alarmService.getAlarmTypes(pageLink).subscribe(response => {
  console.log('Alarm Types:', response.data);
});
```