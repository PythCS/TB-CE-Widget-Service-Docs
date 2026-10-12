# CUSTOM TRANSLATION SERVICE

Part of the [ThingsBoard CE Widget Services Documentation](../DOCUMENTATION.md).

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const customTranslationService = $injector.get(self.ctx.servicesMap.get('customTranslationService'));
```

**1. getAvailableLocales**

```javascript
customTranslationService.getAvailableLocales().subscribe(availableLocales => {
  console.log('Get Available Locales:', availableLocales);
});
```

**2. getAvailableJavaLocales**

```javascript
customTranslationService.getAvailableJavaLocales().subscribe(availableJavaLocales => {
  console.log('Get Available Java Locales:', availableJavaLocales);
});
```

**3. getTranslationInfos**

```javascript
customTranslationService.getTranslationInfos().subscribe(translationInfos => {
  console.log('Get Translation Infos:', translationInfos);
});
```

**4. getTranslationForBasicEdit**

```javascript
customTranslationService.getTranslationForBasicEdit('your-localecode-value').subscribe(translationForBasicEdit => {
  console.log('Get Translation For Basic Edit:', translationForBasicEdit);
});
```

**5. getFullTranslation**

```javascript
customTranslationService.getFullTranslation('your-localecode-value').subscribe(fullTranslation => {
  console.log('Get Full Translation:', fullTranslation);
});
```

**6. downloadFullTranslation**

```javascript
customTranslationService.downloadFullTranslation('your-localecode-value').subscribe(downloadFullTranslation => {
  console.log('Download Full Translation:', downloadFullTranslation);
});
```

**7. deleteCustomTranslation**

```javascript
customTranslationService.deleteCustomTranslation('your-localecode-value').subscribe(result => {
  console.log('Delete Custom Translation:', result);
});
```

**8. deleteCustomTranslationKey**

```javascript
customTranslationService.deleteCustomTranslationKey('your-localescode-value', 'your-key-value').subscribe(result => {
  console.log('Delete Custom Translation Key:', result);
});
```

**9. saveCustomTranslation**

```javascript
customTranslationService.saveCustomTranslation('your-localecode-value', 'your-customtranslationvalue-value').subscribe(result => {
  console.log('Save Custom Translation:', result);
});
```

**10. getCustomTranslation**

```javascript
customTranslationService.getCustomTranslation('your-localecode-value').subscribe(customTranslation => {
  console.log('Get Custom Translation:', customTranslation);
});
```

**11. patchCustomTranslation**

```javascript
customTranslationService.patchCustomTranslation('your-localecode-value', 'your-newcustomtranslation-value').subscribe(result => {
  console.log('Patch Custom Translation:', result);
});
```
