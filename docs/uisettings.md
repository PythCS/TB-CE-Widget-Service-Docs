### **UI SETTINGS SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const uisettingsservice = $injector.get(self.ctx.servicesMap.get('uisettingsservice'));

```

**1. getHelpBaseUrl**

```javascript
uisettingsservice.getHelpBaseUrl().subscribe(helpbaseurl => {
  console.log('Helpbaseurl:', helpbaseurl);
});
```

