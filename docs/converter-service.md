# CONVERTER SERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const converterService = $injector.get(self.ctx.servicesMap.get('converterService'));
```

**1. getConverters**

```javascript
const $injector = self.ctx.$scope.$injector;
const converterService = $injector.get(self.ctx.servicesMap.get('converterService'));
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
converterService.getConverters(pageLink).subscribe(converters => {
  console.log('List of Converters:', converters);
});
```

**2. getConvertersByEdgeTemplate**

```javascript
const $injector = self.ctx.$scope.$injector;
const converterService = $injector.get(self.ctx.servicesMap.get('converterService'));
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const isEdgeTemplate = true;
const integrationType = {  // IntegrationType object
  // ... set the fields you need
};
converterService.getConvertersByEdgeTemplate(pageLink, isEdgeTemplate, integrationType).subscribe(convertersByEdgeTemplates => {
  console.log('List of Converters By Edge Templates:', convertersByEdgeTemplates);
});
```

**3. getConvertersByIds**

```javascript
const $injector = self.ctx.$scope.$injector;
const converterService = $injector.get(self.ctx.servicesMap.get('converterService'));
const converterIds = ['your-converter-i-1', 'your-converter-i-2'];
converterService.getConvertersByIds(converterIds).subscribe(convertersBys => {
  console.log('List of Converters By Ids:', convertersBys);
});
```

**4. getConverter**

```javascript
const $injector = self.ctx.$scope.$injector;
const converterService = $injector.get(self.ctx.servicesMap.get('converterService'));
const converterId = 'your-converter-id';
converterService.getConverter(converterId).subscribe(converter => {
  console.log('Get Converter:', converter);
});
```

**5. saveConverter**

```javascript
const $injector = self.ctx.$scope.$injector;
const converterService = $injector.get(self.ctx.servicesMap.get('converterService'));
const converter = {  // Converter object
  // ... set the fields you need
};
converterService.saveConverter(converter).subscribe(savedConverter => {
  console.log('Saved Converter:', savedConverter);
});
```

**6. testUpLink**

```javascript
const $injector = self.ctx.$scope.$injector;
const converterService = $injector.get(self.ctx.servicesMap.get('converterService'));
const inputParams = {  // TestUpLinkInputParams object
  // ... set the fields you need
};
const scriptLang = {  // ScriptLanguage object
  // ... set the fields you need
};
converterService.testUpLink(inputParams, scriptLang).subscribe(testUpLink => {
  console.log('Test Up Link:', testUpLink);
});
```

**7. testDownLink**

```javascript
const $injector = self.ctx.$scope.$injector;
const converterService = $injector.get(self.ctx.servicesMap.get('converterService'));
const inputParams = {  // TestDownLinkInputParams object
  // ... set the fields you need
};
const scriptLang = {  // ScriptLanguage object
  // ... set the fields you need
};
converterService.testDownLink(inputParams, scriptLang).subscribe(testDownLink => {
  console.log('Test Down Link:', testDownLink);
});
```

**8. getLatestConverterDebugInput**

```javascript
const $injector = self.ctx.$scope.$injector;
const converterService = $injector.get(self.ctx.servicesMap.get('converterService'));
const converterId = 'your-converter-id';
const parameters = {  // LatestConverterParameters object
  // ... set the fields you need
};
converterService.getLatestConverterDebugInput(converterId, parameters).subscribe(latestConverterDebugInput => {
  console.log('Get Latest Converter Debug Input:', latestConverterDebugInput);
});
```

**9. unwrapRawPayload**

```javascript
const $injector = self.ctx.$scope.$injector;
const converterService = $injector.get(self.ctx.servicesMap.get('converterService'));
const integrationType = {  // IntegrationType object
  // ... set the fields you need
};
const msg = {  // ConvertedInputMsgParams object
  // ... set the fields you need
};
converterService.unwrapRawPayload(integrationType, msg).subscribe(unwrapRawPayload => {
  console.log('Unwrap Raw Payload:', unwrapRawPayload);
});
```
