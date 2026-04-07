# AlarmRulesService

### **ALARMRULESSERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const alarmRulesService = $injector.get(self.ctx.servicesMap.get('alarmRulesService'));
```

**1. getAlarmRuleById**

```javascript
alarmRulesService.getAlarmRuleById('your-alarmrule-id', { /* your config */ }).subscribe(alarmrulebyid => {
  console.log('Alarm Rule By Id:', alarmrulebyid);
});
```

**2. saveAlarmRule**

```javascript
alarmRulesService.saveAlarmRule({ /* your alarmRule */ }, { /* your config */ }).subscribe(savedAlarmRule => {
  console.log('Saved AlarmRule:', savedAlarmRule);
});
```

**3. deleteAlarmRule**

```javascript
alarmRulesService.deleteAlarmRule('your-alarmrule-id', { /* your config */ }).subscribe(result => {
  console.log('Delete Result:', result);
});
```

**4. getAlarmRules**

```javascript
alarmRulesService.getAlarmRules(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), { /* your query */ }, { /* your config */ }).subscribe(alarmrule => {
  console.log('Alarm Rules:', alarmrule);
});
```

**5. getAlarmRulesByEntityId**

```javascript
alarmRulesService.getAlarmRulesByEntityId(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), { /* your config */ }).subscribe(alarmrulesbyentityid => {
  console.log('Alarm Rules By Entity Id:', alarmrulesbyentityid);
});
```

**6. testScript**

```javascript
alarmRulesService.testScript({ /* your inputParams */ }, { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**7. getLatestAlarmRuleDebugEvent**

```javascript
alarmRulesService.getLatestAlarmRuleDebugEvent('your-id', { /* your config */ }).subscribe(latestalarmruledebugevent => {
  console.log('Latest Alarm Rule Debug Event:', latestalarmruledebugevent);
});
```

**8. getAlarmRuleNames**

```javascript
alarmRulesService.getAlarmRuleNames(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), { /* your config */ }).subscribe(alarmrulename => {
  console.log('Alarm Rule Names:', alarmrulename);
});
```
