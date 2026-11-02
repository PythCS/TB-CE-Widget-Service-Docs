# CUSTOM MENU SERVICE

Part of the [ThingsBoard CE Widget Services Documentation](../DOCUMENTATION.md).

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const customMenuService = $injector.get(self.ctx.servicesMap.get('customMenuService'));
```

**1. getCustomMenu**

```javascript
customMenuService.getCustomMenu().subscribe(customMenu => {
  console.log('Get Custom Menu:', customMenu);
});
```

**2. loadCustomMenu**

```javascript
customMenuService.loadCustomMenu().subscribe(loadCustomMenu => {
  console.log('Load Custom Menu:', loadCustomMenu);
});
```

**3. getCustomMenuInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
customMenuService.getCustomMenuInfos(pageLink, 'your-scope-value', 'your-assigneetype-value').subscribe(customMenuInfos => {
  console.log('Get Custom Menu Infos:', customMenuInfos);
});
```

**4. getCustomMenuInfo**

```javascript
customMenuService.getCustomMenuInfo('your-custommenu-id').subscribe(customMenuInfo => {
  console.log('Get Custom Menu Info:', customMenuInfo);
});
```

**5. getCustomMenuConfig**

```javascript
customMenuService.getCustomMenuConfig('your-custommenu-id').subscribe(customMenuConfig => {
  console.log('Get Custom Menu Config:', customMenuConfig);
});
```

**6. getCustomMenuAssigneeList**

```javascript
customMenuService.getCustomMenuAssigneeList('your-custommenu-id').subscribe(customMenuAssigneeList => {
  console.log('Get Custom Menu Assignee List:', customMenuAssigneeList);
});
```

**7. updateCustomMenuConfig**

```javascript
customMenuService.updateCustomMenuConfig('your-custommenu-id', 'your-custommenuconfig-value').subscribe(customMenuConfig => {
  console.log('Update Custom Menu Config:', customMenuConfig);
});
```

**8. updateCustomMenuName**

```javascript
customMenuService.updateCustomMenuName('your-custommenu-id', 'your-name-value').subscribe(result => {
  console.log('Update Custom Menu Name:', result);
});
```

**9. assignCustomMenu**

```javascript
customMenuService.assignCustomMenu('your-custommenu-id', 'your-assigneetype-value', 'your-entityids-value').subscribe(result => {
  console.log('Assign Custom Menu:', result);
});
```

**10. saveCustomMenu**

```javascript
customMenuService.saveCustomMenu('your-custommenuinfo-value', 'your-assigntolist-value').subscribe(customMenu => {
  console.log('Save Custom Menu:', customMenu);
});
```

**11. deleteCustomMenu**

```javascript
customMenuService.deleteCustomMenu('your-custommenu-id').subscribe(customMenu => {
  console.log('Delete Custom Menu:', customMenu);
});
```
