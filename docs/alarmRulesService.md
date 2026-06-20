# ALARM RULES SERVICE

Part of [ThingsBoard CE Widget Service Documentation](../DOCUMENTATION.md)

### **ALARM RULES SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const alarmRulesService = $injector.get(self.ctx.servicesMap.get('alarmRulesService'));
```

**1. getAlarmRuleById**

```javascript
alarmRulesService.getAlarmRuleById('your-alarm-rule-id').subscribe(alarmRuleById => {
  console.log('Get Alarm Rule By Id: alarmRuleById');
});
```

**2. saveAlarmRule**

```javascript
const alarmRule = alarmRule;
alarmRulesService.saveAlarmRule(alarmRule).subscribe(savedAlarmRule => {
  console.log('Save Alarm Rule: savedAlarmRule');
});
```

**3. deleteAlarmRule**

```javascript
alarmRulesService.deleteAlarmRule('your-alarm-rule-id').subscribe(result => {
  console.log('Delete Alarm Rule: result');
});
```

**4. getAlarmRules**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const query = query;
alarmRulesService.getAlarmRules(pageLink, query).subscribe(alarmrules => {
  console.log('Get Alarm Rules: alarmrules');
});
```

**5. getAlarmRulesByEntityId**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
alarmRulesService.getAlarmRulesByEntityId(pageLink).subscribe(alarmRulesByEntityId => {
  console.log('Get Alarm Rules By Entity Id: alarmRulesByEntityId');
});
```

**6. testScript**

```javascript
const inputParams = inputParams;
alarmRulesService.testScript(inputParams).subscribe(result => {
  console.log('Test Script: result');
});
```

**7. getLatestAlarmRuleDebugEvent**

```javascript
alarmRulesService.getLatestAlarmRuleDebugEvent('your-id').subscribe(latestAlarmRuleDebugEvent => {
  console.log('Get Latest Alarm Rule Debug Event:latestAlarmRuleDebugEvent');
});
```

**8. getAlarmRuleNames**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
alarmRulesService.getAlarmRuleNames(pageLink).subscribe(alarmrulenames => {
  console.log('Get Alarm Rule Names: alarmrulenames');
});
```
