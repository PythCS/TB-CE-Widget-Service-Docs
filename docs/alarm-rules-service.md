# ALARM RULES SERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const alarmRulesService = $injector.get(self.ctx.servicesMap.get('alarmRulesService'));
```

**1. getAlarmRuleById**

```javascript
const $injector = self.ctx.$scope.$injector;
const alarmRulesService = $injector.get(self.ctx.servicesMap.get('alarmRulesService'));
const alarmRuleId = 'your-alarm-rule-id';
alarmRulesService.getAlarmRuleById(alarmRuleId).subscribe(alarmRuleBy => {
  console.log('Get Alarm Rule By Id:', alarmRuleBy);
});
```

**2. saveAlarmRule**

```javascript
const $injector = self.ctx.$scope.$injector;
const alarmRulesService = $injector.get(self.ctx.servicesMap.get('alarmRulesService'));
const alarmRule = {  // CalculatedFieldAlarmRule object
  // ... set the fields you need
};
alarmRulesService.saveAlarmRule(alarmRule).subscribe(savedAlarmRule => {
  console.log('Saved Alarm Rule:', savedAlarmRule);
});
```

**3. deleteAlarmRule**

```javascript
const $injector = self.ctx.$scope.$injector;
const alarmRulesService = $injector.get(self.ctx.servicesMap.get('alarmRulesService'));
const alarmRuleId = 'your-alarm-rule-id';
alarmRulesService.deleteAlarmRule(alarmRuleId).subscribe(result => {
  console.log('Delete Alarm Rule result:', result);
});
```

**4. getAlarmRules**

```javascript
const $injector = self.ctx.$scope.$injector;
const alarmRulesService = $injector.get(self.ctx.servicesMap.get('alarmRulesService'));
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const query = {  // CalculatedFieldsQuery object
  // ... set the fields you need
};
alarmRulesService.getAlarmRules(pageLink, query).subscribe(alarmRules => {
  console.log('List of Alarm Rules:', alarmRules);
});
```

**5. getAlarmRulesByEntityId**

```javascript
const $injector = self.ctx.$scope.$injector;
const alarmRulesService = $injector.get(self.ctx.servicesMap.get('alarmRulesService'));
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
alarmRulesService.getAlarmRulesByEntityId(pageLink).subscribe(alarmRulesByEntitys => {
  console.log('List of Alarm Rules By Entity Ids:', alarmRulesByEntitys);
});
```

**6. testScript**

```javascript
const $injector = self.ctx.$scope.$injector;
const alarmRulesService = $injector.get(self.ctx.servicesMap.get('alarmRulesService'));
const inputParams = {  // CalculatedFieldTestScriptInputParams object
  // ... set the fields you need
};
alarmRulesService.testScript(inputParams).subscribe(testScript => {
  console.log('Test Script:', testScript);
});
```

**7. getLatestAlarmRuleDebugEvent**

```javascript
const $injector = self.ctx.$scope.$injector;
const alarmRulesService = $injector.get(self.ctx.servicesMap.get('alarmRulesService'));
const id = 'your-id';
alarmRulesService.getLatestAlarmRuleDebugEvent(id).subscribe(latestAlarmRuleDebugEvent => {
  console.log('Get Latest Alarm Rule Debug Event:', latestAlarmRuleDebugEvent);
});
```

**8. getAlarmRuleNames**

```javascript
const $injector = self.ctx.$scope.$injector;
const alarmRulesService = $injector.get(self.ctx.servicesMap.get('alarmRulesService'));
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
alarmRulesService.getAlarmRuleNames(pageLink).subscribe(alarmRuleNames => {
  console.log('List of Alarm Rule Names:', alarmRuleNames);
});
```
