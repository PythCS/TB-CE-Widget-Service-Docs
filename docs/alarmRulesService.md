# ALARM RULES SERVICE

Part of the [ThingsBoard CE Widget Services Documentation](../DOCUMENTATION.md).

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const alarmRulesService = $injector.get(self.ctx.servicesMap.get('alarmRulesService'));
```

**1. getAlarmRuleById**

```javascript
alarmRulesService.getAlarmRuleById('your-alarmrule-id').subscribe(alarmRuleById => {
  console.log('Get Alarm Rule By Id:', alarmRuleById);
});
```

**2. saveAlarmRule**

```javascript
alarmRulesService.saveAlarmRule('your-alarmrule-value').subscribe(alarmRule => {
  console.log('Save Alarm Rule:', alarmRule);
});
```

**3. deleteAlarmRule**

```javascript
alarmRulesService.deleteAlarmRule('your-alarmrule-id').subscribe(alarmRule => {
  console.log('Delete Alarm Rule:', alarmRule);
});
```

**4. getAlarmRules**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
alarmRulesService.getAlarmRules(pageLink, 'your-query-value').subscribe(alarmRules => {
  console.log('Get Alarm Rules:', alarmRules);
});
```

**5. getAlarmRulesByEntityId**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
alarmRulesService.getAlarmRulesByEntityId(pageLink).subscribe(alarmRulesByEntityId => {
  console.log('Get Alarm Rules By Entity Id:', alarmRulesByEntityId);
});
```

**6. testScript**

```javascript
alarmRulesService.testScript('your-inputparams-value').subscribe(testScript => {
  console.log('Test Script:', testScript);
});
```

**7. getLatestAlarmRuleDebugEvent**

```javascript
alarmRulesService.getLatestAlarmRuleDebugEvent('your--id').subscribe(latestAlarmRuleDebugEvent => {
  console.log('Get Latest Alarm Rule Debug Event:', latestAlarmRuleDebugEvent);
});
```

**8. getAlarmRuleNames**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
alarmRulesService.getAlarmRuleNames(pageLink).subscribe(alarmRuleNames => {
  console.log('Get Alarm Rule Names:', alarmRuleNames);
});
```
