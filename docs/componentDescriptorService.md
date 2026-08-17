# COMPONENT DESCRIPTOR SERVICE

Part of the [ThingsBoard CE Widget Services Documentation](../DOCUMENTATION.md).

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const componentDescriptorService = $injector.get(self.ctx.servicesMap.get('componentDescriptorService'));
```

**1. getComponentDescriptorsByType**

```javascript
componentDescriptorService.getComponentDescriptorsByType('your-componenttype-value', 'your-rulechaintype-value').subscribe(componentDescriptorsByType => {
  console.log('Get Component Descriptors By Type:', componentDescriptorsByType);
});
```

**2. getComponentDescriptorsByTypes**

```javascript
componentDescriptorService.getComponentDescriptorsByTypes('your-componenttypes-value', 'your-rulechaintype-value').subscribe(componentDescriptorsByTypes => {
  console.log('Get Component Descriptors By Types:', componentDescriptorsByTypes);
});
```

**3. getComponentDescriptorByClazz**

```javascript
componentDescriptorService.getComponentDescriptorByClazz('your-componentdescriptorclazz-value').subscribe(componentDescriptorByClazz => {
  console.log('Get Component Descriptor By Clazz:', componentDescriptorByClazz);
});
```
