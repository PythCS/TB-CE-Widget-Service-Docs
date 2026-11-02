# CONVERTER SERVICE

Part of the [ThingsBoard CE Widget Services Documentation](../DOCUMENTATION.md).

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const converterService = $injector.get(self.ctx.servicesMap.get('converterService'));
```

**1. getConverters**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
converterService.getConverters(pageLink).subscribe(converters => {
  console.log('Get Converters:', converters);
});
```

**2. getConvertersByEdgeTemplate**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
converterService.getConvertersByEdgeTemplate(pageLink, true, 'your-integrationtype-value').subscribe(convertersByEdgeTemplate => {
  console.log('Get Converters By Edge Template:', convertersByEdgeTemplate);
});
```

**3. getConvertersByIds**

```javascript
converterService.getConvertersByIds('your-converterids-value').subscribe(convertersByIds => {
  console.log('Get Converters By Ids:', convertersByIds);
});
```

**4. getConverter**

```javascript
converterService.getConverter('your-converter-id').subscribe(converter => {
  console.log('Get Converter:', converter);
});
```

**5. saveConverter**

```javascript
converterService.saveConverter('your-converter-value').subscribe(converter => {
  console.log('Save Converter:', converter);
});
```

**6. testUpLink**

```javascript
converterService.testUpLink('your-inputparams-value', 'your-scriptlang-value').subscribe(testUpLink => {
  console.log('Test Up Link:', testUpLink);
});
```

**7. testDownLink**

```javascript
converterService.testDownLink('your-inputparams-value', 'your-scriptlang-value').subscribe(testDownLink => {
  console.log('Test Down Link:', testDownLink);
});
```

**8. getLatestConverterDebugInput**

```javascript
converterService.getLatestConverterDebugInput('your-converter-id', 'your-parameters-value').subscribe(latestConverterDebugInput => {
  console.log('Get Latest Converter Debug Input:', latestConverterDebugInput);
});
```

**9. unwrapRawPayload**

```javascript
converterService.unwrapRawPayload('your-integrationtype-value', 'your-msg-value').subscribe(unwrapRawPayload => {
  console.log('Unwrap Raw Payload:', unwrapRawPayload);
});
```
