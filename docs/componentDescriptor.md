# Component Descriptor

```javascript
// Service name: componentDescriptor
// File: component-descriptor.service.ts
```

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const componentDescriptor = $injector.get(self.ctx.servicesMap.get('componentDescriptor'));
```

### **1. getComponentDescriptorsByType**

```javascript
componentDescriptor.getComponentDescriptorsByType(componentType, ruleChainType).subscribe(componentDescriptors => {
  console.log('Component Descriptors:', componentDescriptors);
});
```

### **2. getComponentDescriptorsByTypes**

```javascript
componentDescriptor.getComponentDescriptorsByTypes(componentTypes, ruleChainType).subscribe(componentDescriptors => {
  console.log('Component Descriptors:', componentDescriptors);
});
```

### **3. getComponentDescriptorByClazz**

```javascript
componentDescriptor.getComponentDescriptorByClazz(componentDescriptorClazz).subscribe(componentDescriptor => {
  console.log('Component Descriptor:', componentDescriptor);
});
```
