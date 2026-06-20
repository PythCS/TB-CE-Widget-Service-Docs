# ALARM SERVICE

Part of [ThingsBoard CE Widget Service Documentation](../DOCUMENTATION.md)

### **ALARM SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const alarmService = $injector.get(self.ctx.servicesMap.get('alarmService'));
```

**1. getAlarm**

```javascript
alarmService.getAlarm('your-alarm-id').subscribe(alarm => {
  console.log('Get Alarm: alarm');
});
```

**2. getAlarmInfo**

```javascript
alarmService.getAlarmInfo('your-alarm-id').subscribe(alarmInfo => {
  console.log('Get Alarm Info: alarmInfo');
});
```

**3. saveAlarm**

```javascript
const alarm = alarm;
alarmService.saveAlarm(alarm).subscribe(savedAlarm => {
  console.log('Save Alarm: savedAlarm');
});
```

**4. ackAlarm**

```javascript
alarmService.ackAlarm('your-alarm-id').subscribe(result => {
  console.log('Ack Alarm: result');
});
```

**5. clearAlarm**

```javascript
alarmService.clearAlarm('your-alarm-id').subscribe(result => {
  console.log('Clear Alarm: result');
});
```

**6. assignAlarm**

```javascript
alarmService.assignAlarm('your-alarm-id', 'your-assignee-id').subscribe(result => {
  console.log('Assign Alarm: result');
});
```

**7. unassignAlarm**

```javascript
alarmService.unassignAlarm('your-alarm-id').subscribe(result => {
  console.log('Unassign Alarm: result');
});
```

**8. deleteAlarm**

```javascript
alarmService.deleteAlarm('your-alarm-id').subscribe(result => {
  console.log('Delete Alarm: result');
});
```

**9. getAlarms**

```javascript
const query = query;
alarmService.getAlarms(query).subscribe(alarms => {
  console.log('Get Alarms: alarms');
});
```

**10. getAlarmsV2**

```javascript
const query = query;
alarmService.getAlarmsV2(query).subscribe(alarmsV2 => {
  console.log('Get Alarms V: alarmsV2');
});
```

**11. getAllAlarms**

```javascript
const query = query;
alarmService.getAllAlarms(query).subscribe(allalarms => {
  console.log('Get All Alarms: allalarms');
});
```

**12. getAllAlarmsV2**

```javascript
const query = query;
alarmService.getAllAlarmsV2(query).subscribe(allAlarmsV2 => {
  console.log('Get All Alarms V: allAlarmsV2');
});
```

**13. getHighestAlarmSeverity**

```javascript
const alarmSearchStatus = alarmSearchStatus;
const alarmStatus = alarmStatus;
alarmService.getHighestAlarmSeverity('your-entity-id', alarmSearchStatus, alarmStatus).subscribe(highestAlarmSeverity => {
  console.log('Get Highest Alarm Severity: highestAlarmSeverity');
});
```

**14. getAlarmTypes**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
alarmService.getAlarmTypes(pageLink).subscribe(alarmtypes => {
  console.log('Get Alarm Types: alarmtypes');
});
```
