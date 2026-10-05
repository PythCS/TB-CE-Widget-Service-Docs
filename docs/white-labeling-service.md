# WHITE LABELING SERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const whiteLabelingService = $injector.get(self.ctx.servicesMap.get('whiteLabelingService'));

// Alternative: Direct context access
const whiteLabelingService = self.ctx.wl;
```

**1. logoImageUrl**

```javascript
const whiteLabelingService = self.ctx.wl;
const result = whiteLabelingService.logoImageUrl();
console.log('Result:', result);
```

**2. logoImageHeight**

```javascript
const whiteLabelingService = self.ctx.wl;
const result = whiteLabelingService.logoImageHeight();
console.log('Result:', result);
```

**3. collapsedLogoImageUrl**

```javascript
const whiteLabelingService = self.ctx.wl;
const result = whiteLabelingService.collapsedLogoImageUrl();
console.log('Result:', result);
```

**4. appTitle**

```javascript
const whiteLabelingService = self.ctx.wl;
const result = whiteLabelingService.appTitle();
console.log('Result:', result);
```

**5. faviconUrl**

```javascript
const whiteLabelingService = self.ctx.wl;
const result = whiteLabelingService.faviconUrl();
console.log('Result:', result);
```

**6. getPrimaryPalette**

```javascript
const whiteLabelingService = self.ctx.wl;
const result = whiteLabelingService.getPrimaryPalette();
console.log('Result:', result);
```

**7. getPrimaryColor**

```javascript
const whiteLabelingService = self.ctx.wl;
const hue = 'your-hue';
const result = whiteLabelingService.getPrimaryColor(hue);
console.log('Result:', result);
```

**8. getAccentPalette**

```javascript
const whiteLabelingService = self.ctx.wl;
const result = whiteLabelingService.getAccentPalette();
console.log('Result:', result);
```

**9. getLoginPrimaryPalette**

```javascript
const whiteLabelingService = self.ctx.wl;
const result = whiteLabelingService.getLoginPrimaryPalette();
console.log('Result:', result);
```

**10. getLoginAccentPalette**

```javascript
const whiteLabelingService = self.ctx.wl;
const result = whiteLabelingService.getLoginAccentPalette();
console.log('Result:', result);
```

**11. isPrimaryColorPanels**

```javascript
const whiteLabelingService = self.ctx.wl;
const result = whiteLabelingService.isPrimaryColorPanels();
console.log('Result:', result);
```

**12. getDocsUrl**

```javascript
const whiteLabelingService = self.ctx.wl;
const result = whiteLabelingService.getDocsUrl();
console.log('Result:', result);
```

**13. getHelpLinkBaseUrl**

```javascript
const whiteLabelingService = self.ctx.wl;
const result = whiteLabelingService.getHelpLinkBaseUrl();
console.log('Result:', result);
```

**14. getUiHelpBaseUrl**

```javascript
const whiteLabelingService = self.ctx.wl;
const result = whiteLabelingService.getUiHelpBaseUrl();
console.log('Result:', result);
```

**15. isEnableHelpLinks**

```javascript
const whiteLabelingService = self.ctx.wl;
const result = whiteLabelingService.isEnableHelpLinks();
console.log('Result:', result);
```

**16. isShowVersion**

```javascript
const whiteLabelingService = self.ctx.wl;
const result = whiteLabelingService.isShowVersion();
console.log('Result:', result);
```

**17. getPlatformName**

```javascript
const whiteLabelingService = self.ctx.wl;
const result = whiteLabelingService.getPlatformName();
console.log('Result:', result);
```

**18. getTrendzName**

```javascript
const whiteLabelingService = self.ctx.wl;
const result = whiteLabelingService.getTrendzName();
console.log('Result:', result);
```

**19. getPlatformVersion**

```javascript
const whiteLabelingService = self.ctx.wl;
const result = whiteLabelingService.getPlatformVersion();
console.log('Result:', result);
```

**20. getHideConnectivityDialog**

```javascript
const whiteLabelingService = self.ctx.wl;
const result = whiteLabelingService.getHideConnectivityDialog();
console.log('Result:', result);
```

**21. loadLoginWhiteLabelingParams**

```javascript
const whiteLabelingService = self.ctx.wl;
whiteLabelingService.loadLoginWhiteLabelingParams().subscribe(loginWhiteLabelingParams => {
  console.log('Load Login White Labeling Params:', loginWhiteLabelingParams);
});
```

**22. onLoginWlParamsLoaded**

```javascript
const whiteLabelingService = self.ctx.wl;
whiteLabelingService.onLoginWlParamsLoaded().subscribe(onLoginWlParamsLoaded => {
  console.log('On Login Wl Params Loaded:', onLoginWlParamsLoaded);
});
```

**23. loadUserWhiteLabelingParams**

```javascript
const whiteLabelingService = self.ctx.wl;
whiteLabelingService.loadUserWhiteLabelingParams().subscribe(userWhiteLabelingParams => {
  console.log('Load User White Labeling Params:', userWhiteLabelingParams);
});
```

**24. onUserWlParamsLoaded**

```javascript
const whiteLabelingService = self.ctx.wl;
whiteLabelingService.onUserWlParamsLoaded().subscribe(onUserWlParamsLoaded => {
  console.log('On User Wl Params Loaded:', onUserWlParamsLoaded);
});
```

**25. whiteLabelPreview**

```javascript
const whiteLabelingService = self.ctx.wl;
const wLParams = {  // WhiteLabelingParams object
  // ... set the fields you need
};
whiteLabelingService.whiteLabelPreview(wLParams).subscribe(whiteLabelPreview => {
  console.log('White Label Preview:', whiteLabelPreview);
});
```

**26. cancelWhiteLabelPreview**

```javascript
const whiteLabelingService = self.ctx.wl;
whiteLabelingService.cancelWhiteLabelPreview().subscribe(cancelWhiteLabelPreview => {
  console.log('Cancel White Label Preview:', cancelWhiteLabelPreview);
});
```

**27. getCurrentWhiteLabelParams**

```javascript
const whiteLabelingService = self.ctx.wl;
whiteLabelingService.getCurrentWhiteLabelParams().subscribe(currentWhiteLabelParams => {
  console.log('Get Current White Label Params:', currentWhiteLabelParams);
});
```

**28. getCurrentLoginWhiteLabelParams**

```javascript
const whiteLabelingService = self.ctx.wl;
whiteLabelingService.getCurrentLoginWhiteLabelParams().subscribe(currentLoginWhiteLabelParams => {
  console.log('Get Current Login White Label Params:', currentLoginWhiteLabelParams);
});
```

**29. saveWhiteLabelParams**

```javascript
const whiteLabelingService = self.ctx.wl;
const wlParams = {  // WhiteLabelingParams object
  // ... set the fields you need
};
whiteLabelingService.saveWhiteLabelParams(wlParams).subscribe(savedWhiteLabelParams => {
  console.log('Saved White Label Params:', savedWhiteLabelParams);
});
```

**30. saveLoginWhiteLabelParams**

```javascript
const whiteLabelingService = self.ctx.wl;
const wlParams = {  // LoginWhiteLabelingParams object
  // ... set the fields you need
};
whiteLabelingService.saveLoginWhiteLabelParams(wlParams).subscribe(savedLoginWhiteLabelParams => {
  console.log('Saved Login White Label Params:', savedLoginWhiteLabelParams);
});
```

**31. deleteCurrentLoginWhiteLabelParams**

```javascript
const whiteLabelingService = self.ctx.wl;
whiteLabelingService.deleteCurrentLoginWhiteLabelParams().subscribe(result => {
  console.log('Delete Current Login White Label Params result:', result);
});
```

**32. isWhiteLabelingAllowed**

```javascript
const whiteLabelingService = self.ctx.wl;
whiteLabelingService.isWhiteLabelingAllowed().subscribe(isWhiteLabelingAllowed => {
  console.log('Is White Labeling Allowed:', isWhiteLabelingAllowed);
});
```

**33. isCustomerWhiteLabelingAllowed**

```javascript
const whiteLabelingService = self.ctx.wl;
whiteLabelingService.isCustomerWhiteLabelingAllowed().subscribe(isCustomerWhiteLabelingAllowed => {
  console.log('Is Customer White Labeling Allowed:', isCustomerWhiteLabelingAllowed);
});
```

**34. saveMailTemplates**

```javascript
const whiteLabelingService = self.ctx.wl;
const mailTemplates = {  // MailTemplatesSettings object
  // ... set the fields you need
};
whiteLabelingService.saveMailTemplates(mailTemplates).subscribe(savedMailTemplates => {
  console.log('Saved Mail Templates:', savedMailTemplates);
});
```

**35. getMailTemplates**

```javascript
const whiteLabelingService = self.ctx.wl;
whiteLabelingService.getMailTemplates().subscribe(mailTemplates => {
  console.log('Get Mail Templates:', mailTemplates);
});
```

**36. wlChanged**

```javascript
const whiteLabelingService = self.ctx.wl;
whiteLabelingService.wlChanged().subscribe(wlChanged => {
  console.log('Wl Changed:', wlChanged);
});
```

**37. getCurrentWlParams**

```javascript
const whiteLabelingService = self.ctx.wl;
const result = whiteLabelingService.getCurrentWlParams();
console.log('Result:', result);
```

**38. setLoginWlParams**

```javascript
const whiteLabelingService = self.ctx.wl;
const newWlParams = {  // LoginWhiteLabelingParams object
  // ... set the fields you need
};
const result = whiteLabelingService.setLoginWlParams(newWlParams);
console.log('Result:', result);
```

**39. applyThemePalettes**

```javascript
const whiteLabelingService = self.ctx.wl;
const paletteSettings = {  // PaletteSettings object
  // ... set the fields you need
};
whiteLabelingService.applyThemePalettes(paletteSettings).subscribe(applyThemePalettes => {
  console.log('Apply Theme Palettes:', applyThemePalettes);
});
```

**40. applyLoginThemePalettes**

```javascript
const whiteLabelingService = self.ctx.wl;
const paletteSettings = {  // PaletteSettings object
  // ... set the fields you need
};
whiteLabelingService.applyLoginThemePalettes(paletteSettings).subscribe(applyLoginThemePalettes => {
  console.log('Apply Login Theme Palettes:', applyLoginThemePalettes);
});
```

**41. configurePalette**

```javascript
const whiteLabelingService = self.ctx.wl;
const paletteConfig = {  // Palette object
  // ... set the fields you need
};
const defaultColors = {  // ColorPalette object
  // ... set the fields you need
};
const defaultType = 'your-default-type';
const defaultExtends = 'your-default-extends';
const result = whiteLabelingService.configurePalette(paletteConfig, defaultColors, defaultType, defaultExtends);
console.log('Result:', result);
```
