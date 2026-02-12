# COMPONENT DESCRIPTOR

## Service Injection

```javascript
const $injector = self.ctx.$scope.$injector;
const componentDescriptorService = $injector.get(self.ctx.servicesMap.get('componentDescriptorService'));
```

## Methods

### getComponentDescriptorsByType

```javascript
const componentType = {
  // your componentType object
};
const ruleChainType = {
  // your ruleChainType object
};

componentDescriptorService.getComponentDescriptorsByType(componentType, ruleChainType).subscribe(result => {
  console.log('ComponentDescriptorsByType:', result);
});
```

### getComponentDescriptorsByTypes

```javascript
const componentTypes = {
  // your componentTypes object
};
const ruleChainType = {
  // your ruleChainType object
};

componentDescriptorService.getComponentDescriptorsByTypes(componentTypes, ruleChainType).subscribe(result => {
  console.log('ComponentDescriptorsByTypes:', result);
});
```

### getComponentDescriptorByClazz

```javascript
const componentDescriptorClazz = 'your-componentdescriptorclazz';

componentDescriptorService.getComponentDescriptorByClazz(componentDescriptorClazz).subscribe(result => {
  console.log('ComponentDescriptorByClazz:', result);
});
```

