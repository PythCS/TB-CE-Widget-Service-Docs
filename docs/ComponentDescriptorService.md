# ComponentDescriptorService

### **COMPONENTDESCRIPTORSERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const componentDescriptorService = $injector.get(self.ctx.servicesMap.get('componentDescriptorService'));
```

**1. getComponentDescriptorsByType**

```javascript
componentDescriptorService.getComponentDescriptorsByType('your-componenttype', 'your-rulechaintype', { /* your config */ }).subscribe(componentdescriptorsbytype => {
  console.log('Component Descriptors By Type:', componentdescriptorsbytype);
});
```

**2. getComponentDescriptorsByTypes**

```javascript
componentDescriptorService.getComponentDescriptorsByTypes('your-componenttypes', 'your-rulechaintype', { /* your config */ }).subscribe(componentdecriptorbytype => {
  console.log('Component Descriptors By Types:', componentdecriptorbytype);
});
```

**3. getComponentDescriptorByClazz**

```javascript
componentDescriptorService.getComponentDescriptorByClazz('your-componentDescriptorClazz', { /* your config */ }).subscribe(componentdescriptorbyclazz => {
  console.log('Component Descriptor By Clazz:', componentdescriptorbyclazz);
});
```
