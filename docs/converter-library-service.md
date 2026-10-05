# CONVERTER LIBRARY SERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const converterLibraryService = $injector.get(self.ctx.servicesMap.get('converterLibraryService'));
```

**1. getVendors**

```javascript
const $injector = self.ctx.$scope.$injector;
const converterLibraryService = $injector.get(self.ctx.servicesMap.get('converterLibraryService'));
const integrationType = {  // IntegrationType object
  // ... set the fields you need
};
const converterType = {  // ConverterType object
  // ... set the fields you need
};
converterLibraryService.getVendors(integrationType, converterType).subscribe(vendors => {
  console.log('Get Vendors:', vendors);
});
```

**2. getModels**

```javascript
const $injector = self.ctx.$scope.$injector;
const converterLibraryService = $injector.get(self.ctx.servicesMap.get('converterLibraryService'));
const integrationType = {  // IntegrationType object
  // ... set the fields you need
};
const vendorName = 'your-vendor-name';
const converterType = {  // ConverterType object
  // ... set the fields you need
};
converterLibraryService.getModels(integrationType, vendorName, converterType).subscribe(models => {
  console.log('Get Models:', models);
});
```

**3. getConverter**

```javascript
const $injector = self.ctx.$scope.$injector;
const converterLibraryService = $injector.get(self.ctx.servicesMap.get('converterLibraryService'));
const integrationType = {  // IntegrationType object
  // ... set the fields you need
};
const vendorName = 'your-vendor-name';
const modelName = 'your-model-name';
const converterType = {  // ConverterType object
  // ... set the fields you need
};
converterLibraryService.getConverter(integrationType, vendorName, modelName, converterType).subscribe(converter => {
  console.log('Get Converter:', converter);
});
```

**4. getConverterMetaData**

```javascript
const $injector = self.ctx.$scope.$injector;
const converterLibraryService = $injector.get(self.ctx.servicesMap.get('converterLibraryService'));
const integrationType = {  // IntegrationType object
  // ... set the fields you need
};
const vendorName = 'your-vendor-name';
const modelName = 'your-model-name';
const converterType = {  // ConverterType object
  // ... set the fields you need
};
converterLibraryService.getConverterMetaData(integrationType, vendorName, modelName, converterType).subscribe(converterMetaData => {
  console.log('Get Converter Meta Data:', converterMetaData);
});
```

**5. getConverterPayload**

```javascript
const $injector = self.ctx.$scope.$injector;
const converterLibraryService = $injector.get(self.ctx.servicesMap.get('converterLibraryService'));
const integrationType = {  // IntegrationType object
  // ... set the fields you need
};
const vendorName = 'your-vendor-name';
const modelName = 'your-model-name';
const converterType = {  // ConverterType object
  // ... set the fields you need
};
converterLibraryService.getConverterPayload(integrationType, vendorName, modelName, converterType).subscribe(converterPayload => {
  console.log('Get Converter Payload:', converterPayload);
});
```
