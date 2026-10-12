# WHITE LABELING SERVICE

Part of the [ThingsBoard CE Widget Services Documentation](../DOCUMENTATION.md).

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const whiteLabelingService = $injector.get(self.ctx.servicesMap.get('whiteLabelingService'));

// Alternative: Direct context access
const whiteLabelingService = self.ctx.wl;
```

**1. logoImageUrl**

```javascript
self.ctx.wl.logoImageUrl().subscribe(logoImageUrl => {
  console.log('Logo Image Url:', logoImageUrl);
});
```

**2. logoImageHeight**

```javascript
self.ctx.wl.logoImageHeight().subscribe(logoImageHeight => {
  console.log('Logo Image Height:', logoImageHeight);
});
```

**3. collapsedLogoImageUrl**

```javascript
self.ctx.wl.collapsedLogoImageUrl().subscribe(collapsedLogoImageUrl => {
  console.log('Collapsed Logo Image Url:', collapsedLogoImageUrl);
});
```

**4. appTitle**

```javascript
self.ctx.wl.appTitle().subscribe(appTitle => {
  console.log('App Title:', appTitle);
});
```

**5. faviconUrl**

```javascript
self.ctx.wl.faviconUrl().subscribe(faviconUrl => {
  console.log('Favicon Url:', faviconUrl);
});
```

**6. getPrimaryPalette**

```javascript
self.ctx.wl.getPrimaryPalette().subscribe(primaryPalette => {
  console.log('Get Primary Palette:', primaryPalette);
});
```

**7. getPrimaryColor**

```javascript
self.ctx.wl.getPrimaryColor('your-hue-value').subscribe(primaryColor => {
  console.log('Get Primary Color:', primaryColor);
});
```

**8. getAccentPalette**

```javascript
self.ctx.wl.getAccentPalette().subscribe(accentPalette => {
  console.log('Get Accent Palette:', accentPalette);
});
```

**9. getLoginPrimaryPalette**

```javascript
self.ctx.wl.getLoginPrimaryPalette().subscribe(loginPrimaryPalette => {
  console.log('Get Login Primary Palette:', loginPrimaryPalette);
});
```

**10. getLoginAccentPalette**

```javascript
self.ctx.wl.getLoginAccentPalette().subscribe(loginAccentPalette => {
  console.log('Get Login Accent Palette:', loginAccentPalette);
});
```

**11. isPrimaryColorPanels**

```javascript
self.ctx.wl.isPrimaryColorPanels().subscribe(isPrimaryColorPanels => {
  console.log('Is Primary Color Panels:', isPrimaryColorPanels);
});
```

**12. getDocsUrl**

```javascript
self.ctx.wl.getDocsUrl().subscribe(docsUrl => {
  console.log('Get Docs Url:', docsUrl);
});
```

**13. getHelpLinkBaseUrl**

```javascript
self.ctx.wl.getHelpLinkBaseUrl().subscribe(helpLinkBaseUrl => {
  console.log('Get Help Link Base Url:', helpLinkBaseUrl);
});
```

**14. getUiHelpBaseUrl**

```javascript
self.ctx.wl.getUiHelpBaseUrl().subscribe(uiHelpBaseUrl => {
  console.log('Get Ui Help Base Url:', uiHelpBaseUrl);
});
```

**15. isEnableHelpLinks**

```javascript
self.ctx.wl.isEnableHelpLinks().subscribe(isEnableHelpLinks => {
  console.log('Is Enable Help Links:', isEnableHelpLinks);
});
```

**16. isShowVersion**

```javascript
self.ctx.wl.isShowVersion().subscribe(isShowVersion => {
  console.log('Is Show Version:', isShowVersion);
});
```

**17. getPlatformName**

```javascript
self.ctx.wl.getPlatformName().subscribe(platformName => {
  console.log('Get Platform Name:', platformName);
});
```

**18. getTrendzName**

```javascript
self.ctx.wl.getTrendzName().subscribe(trendzName => {
  console.log('Get Trendz Name:', trendzName);
});
```

**19. getPlatformVersion**

```javascript
self.ctx.wl.getPlatformVersion().subscribe(platformVersion => {
  console.log('Get Platform Version:', platformVersion);
});
```

**20. getHideConnectivityDialog**

```javascript
self.ctx.wl.getHideConnectivityDialog().subscribe(hideConnectivityDialog => {
  console.log('Get Hide Connectivity Dialog:', hideConnectivityDialog);
});
```

**21. loadLoginWhiteLabelingParams**

```javascript
self.ctx.wl.loadLoginWhiteLabelingParams().subscribe(loadLoginWhiteLabelingParams => {
  console.log('Load Login White Labeling Params:', loadLoginWhiteLabelingParams);
});
```

**22. onLoginWlParamsLoaded**

```javascript
self.ctx.wl.onLoginWlParamsLoaded().subscribe(onLoginWlParamsLoaded => {
  console.log('On Login Wl Params Loaded:', onLoginWlParamsLoaded);
});
```

**23. loadUserWhiteLabelingParams**

```javascript
self.ctx.wl.loadUserWhiteLabelingParams().subscribe(loadUserWhiteLabelingParams => {
  console.log('Load User White Labeling Params:', loadUserWhiteLabelingParams);
});
```

**24. onUserWlParamsLoaded**

```javascript
self.ctx.wl.onUserWlParamsLoaded().subscribe(onUserWlParamsLoaded => {
  console.log('On User Wl Params Loaded:', onUserWlParamsLoaded);
});
```

**25. whiteLabelPreview**

```javascript
self.ctx.wl.whiteLabelPreview('your-wlparams-value').subscribe(whiteLabelPreview => {
  console.log('White Label Preview:', whiteLabelPreview);
});
```

**26. cancelWhiteLabelPreview**

```javascript
self.ctx.wl.cancelWhiteLabelPreview().subscribe(cancelWhiteLabelPreview => {
  console.log('Cancel White Label Preview:', cancelWhiteLabelPreview);
});
```

**27. getCurrentWhiteLabelParams**

```javascript
self.ctx.wl.getCurrentWhiteLabelParams().subscribe(currentWhiteLabelParams => {
  console.log('Get Current White Label Params:', currentWhiteLabelParams);
});
```

**28. getCurrentLoginWhiteLabelParams**

```javascript
self.ctx.wl.getCurrentLoginWhiteLabelParams().subscribe(currentLoginWhiteLabelParams => {
  console.log('Get Current Login White Label Params:', currentLoginWhiteLabelParams);
});
```

**29. saveWhiteLabelParams**

```javascript
self.ctx.wl.saveWhiteLabelParams('your-wlparams-value').subscribe(whiteLabelParams => {
  console.log('Save White Label Params:', whiteLabelParams);
});
```

**30. saveLoginWhiteLabelParams**

```javascript
self.ctx.wl.saveLoginWhiteLabelParams('your-wlparams-value').subscribe(loginWhiteLabelParams => {
  console.log('Save Login White Label Params:', loginWhiteLabelParams);
});
```

**31. deleteCurrentLoginWhiteLabelParams**

```javascript
self.ctx.wl.deleteCurrentLoginWhiteLabelParams().subscribe(result => {
  console.log('Delete Current Login White Label Params:', result);
});
```

**32. isWhiteLabelingAllowed**

```javascript
self.ctx.wl.isWhiteLabelingAllowed().subscribe(isWhiteLabelingAllowed => {
  console.log('Is White Labeling Allowed:', isWhiteLabelingAllowed);
});
```

**33. isCustomerWhiteLabelingAllowed**

```javascript
self.ctx.wl.isCustomerWhiteLabelingAllowed().subscribe(isCustomerWhiteLabelingAllowed => {
  console.log('Is Customer White Labeling Allowed:', isCustomerWhiteLabelingAllowed);
});
```

**34. saveMailTemplates**

```javascript
self.ctx.wl.saveMailTemplates('your-email@example.com').subscribe(mailTemplates => {
  console.log('Save Mail Templates:', mailTemplates);
});
```

**35. getMailTemplates**

```javascript
self.ctx.wl.getMailTemplates().subscribe(mailTemplates => {
  console.log('Get Mail Templates:', mailTemplates);
});
```

**36. wlChanged**

```javascript
self.ctx.wl.wlChanged().subscribe(wlChanged => {
  console.log('Wl Changed:', wlChanged);
});
```

**37. getCurrentWlParams**

```javascript
self.ctx.wl.getCurrentWlParams().subscribe(currentWlParams => {
  console.log('Get Current Wl Params:', currentWlParams);
});
```

**38. setLoginWlParams**

```javascript
self.ctx.wl.setLoginWlParams('your-newwlparams-value').subscribe(loginWlParams => {
  console.log('Set Login Wl Params:', loginWlParams);
});
```

**39. applyThemePalettes**

```javascript
self.ctx.wl.applyThemePalettes('your-palettesettings-value').subscribe(applyThemePalettes => {
  console.log('Apply Theme Palettes:', applyThemePalettes);
});
```

**40. applyLoginThemePalettes**

```javascript
self.ctx.wl.applyLoginThemePalettes('your-palettesettings-value').subscribe(applyLoginThemePalettes => {
  console.log('Apply Login Theme Palettes:', applyLoginThemePalettes);
});
```

**41. configurePalette**

```javascript
self.ctx.wl.configurePalette('your-paletteconfig-value', 'your-defaultcolors-value', 'your-defaulttype-value', 'your-defaultextends-value').subscribe(configurePalette => {
  console.log('Configure Palette:', configurePalette);
});
```
