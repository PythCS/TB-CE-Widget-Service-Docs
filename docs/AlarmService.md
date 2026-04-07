# AlarmService

### **ALARMSERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const alarmService = $injector.get(self.ctx.servicesMap.get('alarmService'));
```

**1. getAlarm**

```javascript
alarmService.getAlarm('your-alarm-id', { /* your config */ }).subscribe(alarm => {
  console.log('Alarm:', alarm);
});
```

**2. getAlarmInfo**

```javascript
alarmService.getAlarmInfo('your-alarm-id', { /* your config */ }).subscribe(alarminfo => {
  console.log('Alarm Info:', alarminfo);
});
```

**3. saveAlarm**

```javascript
alarmService.saveAlarm({ /* your alarm object */ }, { /* your config */ }).subscribe(savedAlarm => {
  console.log('Saved Alarm:', savedAlarm);
});
```

**4. ackAlarm**

```javascript
alarmService.ackAlarm('your-alarm-id', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**5. clearAlarm**

```javascript
alarmService.clearAlarm('your-alarm-id', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**6. assignAlarm**

```javascript
alarmService.assignAlarm('your-alarm-id', 'your-assignee-id', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**7. unassignAlarm**

```javascript
alarmService.unassignAlarm('your-alarm-id', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**8. deleteAlarm**

```javascript
alarmService.deleteAlarm('your-alarm-id', { /* your config */ }).subscribe(result => {
  console.log('Delete Result:', result);
});
```

**9. getAlarms**

```javascript
alarmService.getAlarms({ /* your query */ }, { /* your config */ }).subscribe(alarm => {
  console.log('Alarms:', alarm);
});
```

**10. getAlarmsV2**

```javascript
alarmService.getAlarmsV2({ /* your query */ }, { /* your config */ }).subscribe(alarmsv2 => {
  console.log('Alarms V2:', alarmsv2);
});
```

**11. getAllAlarms**

```javascript
alarmService.getAllAlarms({ /* your query */ }, { /* your config */ }).subscribe(allalarm => {
  console.log('All Alarms:', allalarm);
});
```

**12. getAllAlarmsV2**

```javascript
alarmService.getAllAlarmsV2({ /* your query */ }, { /* your config */ }).subscribe(allalarmsv2 => {
  console.log('All Alarms V2:', allalarmsv2);
});
```

**13. getHighestAlarmSeverity**

```javascript
alarmService.getHighestAlarmSeverity('your-entity-id', { /* your alarmSearchStatus */ }, { /* your alarmStatus */ }, { /* your config */ }).subscribe(highestalarmseverity => {
  console.log('Highest Alarm Severity:', highestalarmseverity);
});
```

**14. getAlarmTypes**

```javascript
alarmService.getAlarmTypes(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), { /* your config */ }).subscribe(alarmtype => {
  console.log('Alarm Types:', alarmtype);
});
```
