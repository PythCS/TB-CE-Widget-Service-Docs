### **ALARM SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const alarmservice = $injector.get(self.ctx.servicesMap.get('alarmservice'));

```

**1. getAlarm**

```javascript
alarmservice.getAlarm('your-alarm-id').subscribe(alarm => {
  console.log('Alarm:', alarm);
});
```

**2. getAlarmInfo**

```javascript
alarmservice.getAlarmInfo('your-alarm-id').subscribe(alarminfo => {
  console.log('Alarminfo:', alarminfo);
});
```

**3. saveAlarm**

```javascript
alarmservice.saveAlarm(alarm).subscribe(savealarm => {
  console.log('Savealarm:', savealarm);
});
```

**4. ackAlarm**

```javascript
alarmservice.ackAlarm('your-alarm-id').subscribe(ackalarm => {
  console.log('Ackalarm:', ackalarm);
});
```

**5. clearAlarm**

```javascript
alarmservice.clearAlarm('your-alarm-id').subscribe(clearalarm => {
  console.log('Clearalarm:', clearalarm);
});
```

**6. assignAlarm**

```javascript
alarmservice.assignAlarm('your-alarm-id', 'your-assignee-id').subscribe(assignalarm => {
  console.log('Assignalarm:', assignalarm);
});
```

**7. unassignAlarm**

```javascript
alarmservice.unassignAlarm('your-alarm-id').subscribe(unassignalarm => {
  console.log('Unassignalarm:', unassignalarm);
});
```

**8. deleteAlarm**

```javascript
alarmservice.deleteAlarm('your-alarm-id').subscribe(deletealarm => {
  console.log('Deletealarm:', deletealarm);
});
```

**9. getAlarms**

```javascript
alarmservice.getAlarms(query).subscribe(alarms => {
  console.log('Alarms:', alarms);
});
```

**10. getAlarmsV2**

```javascript
alarmservice.getAlarmsV2(query).subscribe(alarmsv2 => {
  console.log('Alarmsv2:', alarmsv2);
});
```

**11. getAllAlarms**

```javascript
alarmservice.getAllAlarms(query).subscribe(allalarms => {
  console.log('Allalarms:', allalarms);
});
```

**12. getAllAlarmsV2**

```javascript
alarmservice.getAllAlarmsV2(query).subscribe(allalarmsv2 => {
  console.log('Allalarmsv2:', allalarmsv2);
});
```

**13. getHighestAlarmSeverity**

```javascript
alarmservice.getHighestAlarmSeverity('your-entity-id', alarmSearchStatus, alarmStatus).subscribe(highestalarmseverity => {
  console.log('Highestalarmseverity:', highestalarmseverity);
});
```

**14. getAlarmTypes**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
alarmservice.getAlarmTypes(pageLink).subscribe(alarmtypes => {
  console.log('Alarmtypes:', alarmtypes);
});
```

