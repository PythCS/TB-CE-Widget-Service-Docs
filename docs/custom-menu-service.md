# CUSTOM MENU SERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const customMenuService = $injector.get(self.ctx.servicesMap.get('customMenuService'));
```

**1. getCustomMenu**

```javascript
const $injector = self.ctx.$scope.$injector;
const customMenuService = $injector.get(self.ctx.servicesMap.get('customMenuService'));
const result = customMenuService.getCustomMenu();
console.log('Result:', result);
```

**2. loadCustomMenu**

```javascript
const $injector = self.ctx.$scope.$injector;
const customMenuService = $injector.get(self.ctx.servicesMap.get('customMenuService'));
customMenuService.loadCustomMenu().subscribe(customMenu => {
  console.log('Load Custom Menu:', customMenu);
});
```

**3. getCustomMenuInfos**

```javascript
const $injector = self.ctx.$scope.$injector;
const customMenuService = $injector.get(self.ctx.servicesMap.get('customMenuService'));
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const scope = {  // CMScope object
  // ... set the fields you need
};
const assigneeType = {  // CMAssigneeType object
  // ... set the fields you need
};
customMenuService.getCustomMenuInfos(pageLink, scope, assigneeType).subscribe(customMenuInfos => {
  console.log('List of Custom Menu Infos:', customMenuInfos);
});
```

**4. getCustomMenuInfo**

```javascript
const $injector = self.ctx.$scope.$injector;
const customMenuService = $injector.get(self.ctx.servicesMap.get('customMenuService'));
const customMenuId = 'your-custom-menu-id';
customMenuService.getCustomMenuInfo(customMenuId).subscribe(customMenuInfo => {
  console.log('Get Custom Menu Info:', customMenuInfo);
});
```

**5. getCustomMenuConfig**

```javascript
const $injector = self.ctx.$scope.$injector;
const customMenuService = $injector.get(self.ctx.servicesMap.get('customMenuService'));
const customMenuId = 'your-custom-menu-id';
customMenuService.getCustomMenuConfig(customMenuId).subscribe(customMenuConfig => {
  console.log('Get Custom Menu Config:', customMenuConfig);
});
```

**6. getCustomMenuAssigneeList**

```javascript
const $injector = self.ctx.$scope.$injector;
const customMenuService = $injector.get(self.ctx.servicesMap.get('customMenuService'));
const customMenuId = 'your-custom-menu-id';
customMenuService.getCustomMenuAssigneeList(customMenuId).subscribe(customMenuAssigneeLists => {
  console.log('List of Custom Menu Assignee Lists:', customMenuAssigneeLists);
});
```

**7. updateCustomMenuConfig**

```javascript
const $injector = self.ctx.$scope.$injector;
const customMenuService = $injector.get(self.ctx.servicesMap.get('customMenuService'));
const customMenuId = 'your-custom-menu-id';
const customMenuConfig = {  // CustomMenuConfig object
  // ... set the fields you need
};
customMenuService.updateCustomMenuConfig(customMenuId, customMenuConfig).subscribe(savedCustomMenuConfig => {
  console.log('Saved Custom Menu Config:', savedCustomMenuConfig);
});
```

**8. updateCustomMenuName**

```javascript
const $injector = self.ctx.$scope.$injector;
const customMenuService = $injector.get(self.ctx.servicesMap.get('customMenuService'));
const customMenuId = 'your-custom-menu-id';
const name = 'name-value';
customMenuService.updateCustomMenuName(customMenuId, name).subscribe(savedCustomMenuName => {
  console.log('Saved Custom Menu Name:', savedCustomMenuName);
});
```

**9. assignCustomMenu**

```javascript
const $injector = self.ctx.$scope.$injector;
const customMenuService = $injector.get(self.ctx.servicesMap.get('customMenuService'));
const customMenuId = 'your-custom-menu-id';
const assigneeType = {  // CMAssigneeType object
  // ... set the fields you need
};
const entityIds = ['your-entity-i-1', 'your-entity-i-2'];
customMenuService.assignCustomMenu(customMenuId, assigneeType, entityIds).subscribe(assignCustomMenu => {
  console.log('Assign Custom Menu:', assignCustomMenu);
});
```

**10. saveCustomMenu**

```javascript
const $injector = self.ctx.$scope.$injector;
const customMenuService = $injector.get(self.ctx.servicesMap.get('customMenuService'));
const customMenuInfo = {  // CustomMenuInfo object
  // ... set the fields you need
};
const assignToList = [];  // e.g. array of assign-to-list values
customMenuService.saveCustomMenu(customMenuInfo, assignToList).subscribe(savedCustomMenu => {
  console.log('Saved Custom Menu:', savedCustomMenu);
});
```

**11. deleteCustomMenu**

```javascript
const $injector = self.ctx.$scope.$injector;
const customMenuService = $injector.get(self.ctx.servicesMap.get('customMenuService'));
const customMenuId = 'your-custom-menu-id';
customMenuService.deleteCustomMenu(customMenuId).subscribe(result => {
  console.log('Delete Custom Menu result:', result);
});
```
