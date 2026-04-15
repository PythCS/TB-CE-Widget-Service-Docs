# Alarm Rules

```javascript
// Service name: alarmRules
// File: alarm-rules.service.ts
```

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const alarmRules = $injector.get(self.ctx.servicesMap.get('alarmRules'));
```

### **1. getAlarmRuleById**

```javascript
alarmRules.getAlarmRuleById(alarmRuleId).subscribe(alarm => {
  console.log('Alarm:', alarm);
});
```

### **2. saveAlarmRule**

```javascript
alarmRules.saveAlarmRule(alarmRule).subscribe(alarm => {
  console.log('Alarm:', alarm);
});
```

### **3. deleteAlarmRule**

```javascript
alarmRules.deleteAlarmRule(alarmRuleId).subscribe(alarm => {
  console.log('Alarm:', alarm);
});
```

### **4. getAlarmRules**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
alarmRules.getAlarmRules(pageLink).subscribe(alarms => {
  console.log('Alarms:', alarms);
});
```

### **5. getAlarmRulesByEntityId**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
alarmRules.getAlarmRulesByEntityId(pageLink).subscribe(alarms => {
  console.log('Alarms:', alarms);
});
```

### **6. testScript**

```javascript
alarmRules.testScript(inputParams).subscribe(testScript => {
  console.log('Test Script:', testScript);
});
```

### **7. getLatestAlarmRuleDebugEvent**

```javascript
alarmRules.getLatestAlarmRuleDebugEvent(id).subscribe(alarm => {
  console.log('Alarm:', alarm);
});
```

### **8. getAlarmRuleNames**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
alarmRules.getAlarmRuleNames(pageLink).subscribe(alarms => {
  console.log('Alarms:', alarms);
});
```
