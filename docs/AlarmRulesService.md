# AlarmRulesService

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const alarmRulesService = $injector.get(self.ctx.servicesMap.get('AlarmRulesService'));
```

**1. getAlarmRuleById**

```javascript
alarmRulesService.getAlarmRuleById('your-alarmrule-id').subscribe(alarm => {
  console.log('Fetched  Alarm Rule By Id alarm:', alarm);
});
```

**2. saveAlarmRule**

```javascript
alarmRulesService.saveAlarmRule('your-alarmrule-value').subscribe(alarm => {
  console.log('Saved  Alarm Rule alarm:', alarm);
});
```

**3. deleteAlarmRule**

```javascript
alarmRulesService.deleteAlarmRule('your-alarmrule-id').subscribe(alarm => {
  console.log('Deleted  Alarm Rule alarm:', alarm);
});
```

**4. getAlarmRules**

```javascript
alarmRulesService.getAlarmRules(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-query-value').subscribe(alarm => {
  console.log('Fetched  Alarm Rules alarm:', alarm);
});
```

**5. getAlarmRulesByEntityId**

```javascript
alarmRulesService.getAlarmRulesByEntityId(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder')).subscribe(alarm => {
  console.log('Fetched  Alarm Rules By Entity Id alarm:', alarm);
});
```

**6. testScript**

```javascript
alarmRulesService.testScript('your-inputparams-value').subscribe(result => {
  console.log('test Script result:', result);
});
```

**7. getLatestAlarmRuleDebugEvent**

```javascript
alarmRulesService.getLatestAlarmRuleDebugEvent('your--id').subscribe(alarm => {
  console.log('Fetched  Latest Alarm Rule Debug Event alarm:', alarm);
});
```

**8. getAlarmRuleNames**

```javascript
alarmRulesService.getAlarmRuleNames(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder')).subscribe(alarm => {
  console.log('Fetched  Alarm Rule Names alarm:', alarm);
});
```
