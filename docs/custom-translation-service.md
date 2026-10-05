# CUSTOM TRANSLATION SERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const customTranslationService = $injector.get(self.ctx.servicesMap.get('customTranslationService'));
```

**1. getAvailableLocales**

```javascript
const $injector = self.ctx.$scope.$injector;
const customTranslationService = $injector.get(self.ctx.servicesMap.get('customTranslationService'));
customTranslationService.getAvailableLocales().subscribe(availableLocales => {
  console.log('Get Available Locales:', availableLocales);
});
```

**2. getAvailableJavaLocales**

```javascript
const $injector = self.ctx.$scope.$injector;
const customTranslationService = $injector.get(self.ctx.servicesMap.get('customTranslationService'));
customTranslationService.getAvailableJavaLocales().subscribe(availableJavaLocales => {
  console.log('Get Available Java Locales:', availableJavaLocales);
});
```

**3. getTranslationInfos**

```javascript
const $injector = self.ctx.$scope.$injector;
const customTranslationService = $injector.get(self.ctx.servicesMap.get('customTranslationService'));
customTranslationService.getTranslationInfos().subscribe(translationInfos => {
  console.log('List of Translation Infos:', translationInfos);
});
```

**4. getTranslationForBasicEdit**

```javascript
const $injector = self.ctx.$scope.$injector;
const customTranslationService = $injector.get(self.ctx.servicesMap.get('customTranslationService'));
const localeCode = 'your-locale-code';
customTranslationService.getTranslationForBasicEdit(localeCode).subscribe(translationForBasicEdit => {
  console.log('Get Translation For Basic Edit:', translationForBasicEdit);
});
```

**5. getFullTranslation**

```javascript
const $injector = self.ctx.$scope.$injector;
const customTranslationService = $injector.get(self.ctx.servicesMap.get('customTranslationService'));
const localeCode = 'your-locale-code';
customTranslationService.getFullTranslation(localeCode).subscribe(fullTranslation => {
  console.log('Get Full Translation:', fullTranslation);
});
```

**6. downloadFullTranslation**

```javascript
const $injector = self.ctx.$scope.$injector;
const customTranslationService = $injector.get(self.ctx.servicesMap.get('customTranslationService'));
const localeCode = 'your-locale-code';
customTranslationService.downloadFullTranslation(localeCode).subscribe(downloadFullTranslation => {
  console.log('Download Full Translation:', downloadFullTranslation);
});
```

**7. deleteCustomTranslation**

```javascript
const $injector = self.ctx.$scope.$injector;
const customTranslationService = $injector.get(self.ctx.servicesMap.get('customTranslationService'));
const localeCode = 'your-locale-code';
customTranslationService.deleteCustomTranslation(localeCode).subscribe(result => {
  console.log('Delete Custom Translation result:', result);
});
```

**8. deleteCustomTranslationKey**

```javascript
const $injector = self.ctx.$scope.$injector;
const customTranslationService = $injector.get(self.ctx.servicesMap.get('customTranslationService'));
const localesCode = 'your-locales-code';
const key = 'key-value';
customTranslationService.deleteCustomTranslationKey(localesCode, key).subscribe(result => {
  console.log('Delete Custom Translation Key result:', result);
});
```

**9. saveCustomTranslation**

```javascript
const $injector = self.ctx.$scope.$injector;
const customTranslationService = $injector.get(self.ctx.servicesMap.get('customTranslationService'));
const localeCode = 'your-locale-code';
const customTranslationValue = {  // object object
  // ... set the fields you need
};
customTranslationService.saveCustomTranslation(localeCode, customTranslationValue).subscribe(savedCustomTranslation => {
  console.log('Saved Custom Translation:', savedCustomTranslation);
});
```

**10. getCustomTranslation**

```javascript
const $injector = self.ctx.$scope.$injector;
const customTranslationService = $injector.get(self.ctx.servicesMap.get('customTranslationService'));
const localeCode = 'your-locale-code';
customTranslationService.getCustomTranslation(localeCode).subscribe(customTranslation => {
  console.log('Get Custom Translation:', customTranslation);
});
```

**11. patchCustomTranslation**

```javascript
const $injector = self.ctx.$scope.$injector;
const customTranslationService = $injector.get(self.ctx.servicesMap.get('customTranslationService'));
const localeCode = 'your-locale-code';
const newCustomTranslation = {  // object object
  // ... set the fields you need
};
customTranslationService.patchCustomTranslation(localeCode, newCustomTranslation).subscribe(patchCustomTranslation => {
  console.log('Patch Custom Translation:', patchCustomTranslation);
});
```
