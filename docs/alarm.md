# Alarm

```javascript
// Service name: alarm
// File: alarm.service.ts
```

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const alarm = $injector.get(self.ctx.servicesMap.get('alarm'));
```

### **1. getAlarm**

```javascript
alarm.getAlarm(alarmId).subscribe(alarm => {
  console.log('Alarm:', alarm);
});
```

### **2. getAlarmInfo**

```javascript
alarm.getAlarmInfo(alarmId).subscribe(alarm => {
  console.log('Alarm:', alarm);
});
```

### **3. saveAlarm**

```javascript
alarm.saveAlarm(alarm).subscribe(alarm => {
  console.log('Alarm:', alarm);
});
```

### **4. ackAlarm**

```javascript
alarm.ackAlarm(alarmId).subscribe(alarm => {
  console.log('Alarm:', alarm);
});
```

### **5. clearAlarm**

```javascript
alarm.clearAlarm(alarmId).subscribe(alarm => {
  console.log('Alarm:', alarm);
});
```

### **6. assignAlarm**

```javascript
alarm.assignAlarm(alarmId, assigneeId).subscribe(alarm => {
  console.log('Alarm:', alarm);
});
```

### **7. unassignAlarm**

```javascript
alarm.unassignAlarm(alarmId).subscribe(alarm => {
  console.log('Alarm:', alarm);
});
```

### **8. deleteAlarm**

```javascript
alarm.deleteAlarm(alarmId).subscribe(alarm => {
  console.log('Alarm:', alarm);
});
```

### **9. getAlarms**

```javascript
alarm.getAlarms(query).subscribe(alarms => {
  console.log('Alarms:', alarms);
});
```

### **10. getAlarmsV2**

```javascript
alarm.getAlarmsV2(query).subscribe(alarms => {
  console.log('Alarms:', alarms);
});
```

### **11. getAllAlarms**

```javascript
alarm.getAllAlarms(query).subscribe(alarms => {
  console.log('Alarms:', alarms);
});
```

### **12. getAllAlarmsV2**

```javascript
alarm.getAllAlarmsV2(query).subscribe(alarms => {
  console.log('Alarms:', alarms);
});
```

### **13. getHighestAlarmSeverity**

```javascript
const entityId = { id: 'your-entity-id', entityType: 1 };
alarm.getHighestAlarmSeverity(entityId).subscribe(alarm => {
  console.log('Alarm:', alarm);
});
```

### **14. getAlarmTypes**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
alarm.getAlarmTypes(pageLink).subscribe(alarms => {
  console.log('Alarms:', alarms);
});
```
