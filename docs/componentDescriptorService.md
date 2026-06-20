# COMPONENT DESCRIPTOR SERVICE

Part of [ThingsBoard CE Widget Service Documentation](../DOCUMENTATION.md)

### **COMPONENT DESCRIPTOR SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const componentDescriptorService = $injector.get(self.ctx.servicesMap.get('componentDescriptorService'));
```

**1. getComponentDescriptorsByType**

```javascript
componentDescriptorService.getComponentDescriptorsByType('type', 'type').subscribe(componentDescriptorsByType => {
  console.log('Get Component Descriptors By Type:componentDescriptorsByType');
});
```

**2. getComponentDescriptorsByTypes**

```javascript
componentDescriptorService.getComponentDescriptorsByTypes('type', 'type').subscribe(componentdescriptorsbytypes => {
  console.log('Get Component Descriptors By Types:componentdescriptorsbytypes');
});
```

**3. getComponentDescriptorByClazz**

```javascript
const componentDescriptorClazz = componentDescriptorClazz;
componentDescriptorService.getComponentDescriptorByClazz(componentDescriptorClazz).subscribe(componentDescriptorByClazz => {
  console.log('Get Component Descriptor By Clazz:componentDescriptorByClazz');
});
```
