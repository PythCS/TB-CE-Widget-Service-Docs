# ALARM SERVICE

Part of the [ThingsBoard CE Widget Services Documentation](../DOCUMENTATION.md).

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const alarmService = $injector.get(self.ctx.servicesMap.get('alarmService'));
```

**1. getAlarm**

```javascript
alarmService.getAlarm('your-alarm-id').subscribe(alarm => {
  console.log('Get Alarm:', alarm);
});
```

**2. getAlarmInfo**

```javascript
alarmService.getAlarmInfo('your-alarm-id').subscribe(alarmInfo => {
  console.log('Get Alarm Info:', alarmInfo);
});
```

**3. saveAlarm**

```javascript
alarmService.saveAlarm('your-alarm-value').subscribe(alarm => {
  console.log('Save Alarm:', alarm);
});
```

**4. ackAlarm**

```javascript
alarmService.ackAlarm('your-alarm-id').subscribe(alarm => {
  console.log('Ack Alarm:', alarm);
});
```

**5. clearAlarm**

```javascript
alarmService.clearAlarm('your-alarm-id').subscribe(alarm => {
  console.log('Clear Alarm:', alarm);
});
```

**6. assignAlarm**

```javascript
alarmService.assignAlarm('your-alarm-id', 'your-assignee-id').subscribe(result => {
  console.log('Assign Alarm:', result);
});
```

**7. unassignAlarm**

```javascript
alarmService.unassignAlarm('your-alarm-id').subscribe(result => {
  console.log('Unassign Alarm:', result);
});
```

**8. deleteAlarm**

```javascript
alarmService.deleteAlarm('your-alarm-id').subscribe(alarm => {
  console.log('Delete Alarm:', alarm);
});
```

**9. getAlarms**

```javascript
alarmService.getAlarms('your-query-value').subscribe(alarms => {
  console.log('Get Alarms:', alarms);
});
```

**10. getAlarmsV2**

```javascript
alarmService.getAlarmsV2('your-query-value').subscribe(alarmsV2 => {
  console.log('Get Alarms V 2:', alarmsV2);
});
```

**11. getAllAlarms**

```javascript
alarmService.getAllAlarms('your-query-value').subscribe(allAlarms => {
  console.log('Get All Alarms:', allAlarms);
});
```

**12. getAllAlarmsV2**

```javascript
alarmService.getAllAlarmsV2('your-query-value').subscribe(allAlarmsV2 => {
  console.log('Get All Alarms V 2:', allAlarmsV2);
});
```

**13. getHighestAlarmSeverity**

```javascript
alarmService.getHighestAlarmSeverity('your-entity-id', 'your-alarmsearchstatus-value', 'your-alarmstatus-value').subscribe(highestAlarmSeverity => {
  console.log('Get Highest Alarm Severity:', highestAlarmSeverity);
});
```

**14. getAlarmTypes**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
alarmService.getAlarmTypes(pageLink).subscribe(alarmTypes => {
  console.log('Get Alarm Types:', alarmTypes);
});
```
