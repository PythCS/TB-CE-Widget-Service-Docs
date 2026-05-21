# AlarmService

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const alarmService = $injector.get(self.ctx.servicesMap.get('AlarmService'));
```

**1. getAlarm**

```javascript
alarmService.getAlarm('your-alarm-id').subscribe(alarm => {
  console.log('Fetched  Alarm alarm:', alarm);
});
```

**2. getAlarmInfo**

```javascript
alarmService.getAlarmInfo('your-alarm-id').subscribe(alarm => {
  console.log('Fetched  Alarm Info alarm:', alarm);
});
```

**3. saveAlarm**

```javascript
alarmService.saveAlarm('your-alarm-value').subscribe(alarm => {
  console.log('Saved  Alarm alarm:', alarm);
});
```

**4. ackAlarm**

```javascript
alarmService.ackAlarm('your-alarm-id').subscribe(alarm => {
  console.log('ack Alarm alarm:', alarm);
});
```

**5. clearAlarm**

```javascript
alarmService.clearAlarm('your-alarm-id').subscribe(alarm => {
  console.log('clear Alarm alarm:', alarm);
});
```

**6. assignAlarm**

```javascript
alarmService.assignAlarm('your-alarm-id', 'your-assignee-id').subscribe(result => {
  console.log('Operation completed:', result);
});
```

**7. unassignAlarm**

```javascript
alarmService.unassignAlarm('your-alarm-id').subscribe(result => {
  console.log('Operation completed:', result);
});
```

**8. deleteAlarm**

```javascript
alarmService.deleteAlarm('your-alarm-id').subscribe(alarm => {
  console.log('Deleted  Alarm alarm:', alarm);
});
```

**9. getAlarms**

```javascript
alarmService.getAlarms('your-query-value').subscribe(alarm => {
  console.log('Fetched  Alarms alarm:', alarm);
});
```

**10. getAlarmsV2**

```javascript
alarmService.getAlarmsV2('your-query-value').subscribe(alarm => {
  console.log('Fetched  Alarms V2 alarm:', alarm);
});
```

**11. getAllAlarms**

```javascript
alarmService.getAllAlarms('your-query-value').subscribe(alarm => {
  console.log('Fetched  All Alarms alarm:', alarm);
});
```

**12. getAllAlarmsV2**

```javascript
alarmService.getAllAlarmsV2('your-query-value').subscribe(alarm => {
  console.log('Fetched  All Alarms V2 alarm:', alarm);
});
```

**13. getHighestAlarmSeverity**

```javascript
alarmService.getHighestAlarmSeverity('your-entity-id', 'your-alarmsearchstatus-value', 'your-alarmstatus-value').subscribe(alarm => {
  console.log('Fetched  Highest Alarm Severity alarm:', alarm);
});
```

**14. getAlarmTypes**

```javascript
alarmService.getAlarmTypes(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder')).subscribe(alarm => {
  console.log('Fetched  Alarm Types alarm:', alarm);
});
```
