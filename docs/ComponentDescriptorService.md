# ComponentDescriptorService

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const componentDescriptorService = $injector.get(self.ctx.servicesMap.get('ComponentDescriptorService'));
```

**1. getComponentDescriptorsByType**

```javascript
componentDescriptorService.getComponentDescriptorsByType('your-componenttype-value', 'your-rulechaintype-value').subscribe(result => {
  console.log('Fetched  Component Descriptors By Type result:', result);
});
```

**2. getComponentDescriptorsByTypes**

```javascript
componentDescriptorService.getComponentDescriptorsByTypes('your-componenttypes-value', 'your-rulechaintype-value').subscribe(result => {
  console.log('Fetched  Component Descriptors By Types result:', result);
});
```

**3. getComponentDescriptorByClazz**

```javascript
componentDescriptorService.getComponentDescriptorByClazz('your-componentdescriptorclazz-value').subscribe(result => {
  console.log('Fetched  Component Descriptor By Clazz result:', result);
});
```
