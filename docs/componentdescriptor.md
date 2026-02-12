### **COMPONENT DESCRIPTOR SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const componentdescriptorservice = $injector.get(self.ctx.servicesMap.get('componentdescriptorservice'));

```

**1. getComponentDescriptorsByType**

```javascript
componentdescriptorservice.getComponentDescriptorsByType(componentType, ruleChainType).subscribe(componentdescriptorsbytype => {
  console.log('Componentdescriptorsbytype:', componentdescriptorsbytype);
});
```

**2. getComponentDescriptorsByTypes**

```javascript
componentdescriptorservice.getComponentDescriptorsByTypes(componentTypes, ruleChainType).subscribe(componentdescriptorsbytypes => {
  console.log('Componentdescriptorsbytypes:', componentdescriptorsbytypes);
});
```

**3. getComponentDescriptorByClazz**

```javascript
componentdescriptorservice.getComponentDescriptorByClazz('your-componentdescriptorclazz').subscribe(componentdescriptorbyclazz => {
  console.log('Componentdescriptorbyclazz:', componentdescriptorbyclazz);
});
```

