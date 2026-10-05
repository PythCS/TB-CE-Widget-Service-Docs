# COMPONENT DESCRIPTOR SERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const componentDescriptorService = $injector.get(self.ctx.servicesMap.get('componentDescriptorService'));
```

**1. getComponentDescriptorsByType**

```javascript
const $injector = self.ctx.$scope.$injector;
const componentDescriptorService = $injector.get(self.ctx.servicesMap.get('componentDescriptorService'));
const componentType = {  // ComponentType object
  // ... set the fields you need
};
const ruleChainType = {  // RuleChainType object
  // ... set the fields you need
};
componentDescriptorService.getComponentDescriptorsByType(componentType, ruleChainType).subscribe(componentDescriptorsByTypes => {
  console.log('List of Component Descriptors By Types:', componentDescriptorsByTypes);
});
```

**2. getComponentDescriptorsByTypes**

```javascript
const $injector = self.ctx.$scope.$injector;
const componentDescriptorService = $injector.get(self.ctx.servicesMap.get('componentDescriptorService'));
const componentTypes = [];  // e.g. array of component-types values
const ruleChainType = {  // RuleChainType object
  // ... set the fields you need
};
componentDescriptorService.getComponentDescriptorsByTypes(componentTypes, ruleChainType).subscribe(componentDescriptorsByTypes => {
  console.log('List of Component Descriptors By Types:', componentDescriptorsByTypes);
});
```

**3. getComponentDescriptorByClazz**

```javascript
const $injector = self.ctx.$scope.$injector;
const componentDescriptorService = $injector.get(self.ctx.servicesMap.get('componentDescriptorService'));
const componentDescriptorClazz = 'your-component-descriptor-clazz';
componentDescriptorService.getComponentDescriptorByClazz(componentDescriptorClazz).subscribe(componentDescriptorByClazz => {
  console.log('Get Component Descriptor By Clazz:', componentDescriptorByClazz);
});
```
