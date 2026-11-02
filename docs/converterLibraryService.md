# CONVERTER LIBRARY SERVICE

Part of the [ThingsBoard CE Widget Services Documentation](../DOCUMENTATION.md).

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const converterLibraryService = $injector.get(self.ctx.servicesMap.get('converterLibraryService'));
```

**1. getVendors**

```javascript
converterLibraryService.getVendors('your-integrationtype-value', 'your-convertertype-value').subscribe(vendors => {
  console.log('Get Vendors:', vendors);
});
```

**2. getModels**

```javascript
converterLibraryService.getModels('your-integrationtype-value', 'your-vendorname-value', 'your-convertertype-value').subscribe(models => {
  console.log('Get Models:', models);
});
```

**3. getConverter**

```javascript
converterLibraryService.getConverter('your-integrationtype-value', 'your-vendorname-value', 'your-modelname-value', 'your-convertertype-value').subscribe(converter => {
  console.log('Get Converter:', converter);
});
```

**4. getConverterMetaData**

```javascript
converterLibraryService.getConverterMetaData('your-integrationtype-value', 'your-vendorname-value', 'your-modelname-value', 'your-convertertype-value').subscribe(converterMetaData => {
  console.log('Get Converter Meta Data:', converterMetaData);
});
```

**5. getConverterPayload**

```javascript
converterLibraryService.getConverterPayload('your-integrationtype-value', 'your-vendorname-value', 'your-modelname-value', 'your-convertertype-value').subscribe(converterPayload => {
  console.log('Get Converter Payload:', converterPayload);
});
```
