# SYSTEM SETUP SERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const systemSetupService = $injector.get(self.ctx.servicesMap.get('systemSetupService'));
```

**1. checkSetupState**

```javascript
const $injector = self.ctx.$scope.$injector;
const systemSetupService = $injector.get(self.ctx.servicesMap.get('systemSetupService'));
systemSetupService.checkSetupState().subscribe(checkSetupState => {
  console.log('Check Setup State:', checkSetupState);
});
```

**2. readableState**

```javascript
const $injector = self.ctx.$scope.$injector;
const systemSetupService = $injector.get(self.ctx.servicesMap.get('systemSetupService'));
const setupInfo = {  // SetupInfo object
  // ... set the fields you need
};
const result = systemSetupService.readableState(setupInfo);
console.log('Result:', result);
```

**3. handleSetupState**

```javascript
const $injector = self.ctx.$scope.$injector;
const systemSetupService = $injector.get(self.ctx.servicesMap.get('systemSetupService'));
const state = {  // SystemSetupState object
  // ... set the fields you need
};
const result = systemSetupService.handleSetupState(state);
console.log('Result:', result);
```

**4. finishSetup**

```javascript
const $injector = self.ctx.$scope.$injector;
const systemSetupService = $injector.get(self.ctx.servicesMap.get('systemSetupService'));
const result = systemSetupService.finishSetup();
console.log('Result:', result);
```

**5. makeStartUpHandOff**

```javascript
const $injector = self.ctx.$scope.$injector;
const systemSetupService = $injector.get(self.ctx.servicesMap.get('systemSetupService'));
const gotoDefaultPlace = true;
const result = systemSetupService.makeStartUpHandOff(gotoDefaultPlace);
console.log('Result:', result);
```

**6. getState**

```javascript
const $injector = self.ctx.$scope.$injector;
const systemSetupService = $injector.get(self.ctx.servicesMap.get('systemSetupService'));
const result = systemSetupService.getState();
console.log('Result:', result);
```

**7. getSetupState**

```javascript
const $injector = self.ctx.$scope.$injector;
const systemSetupService = $injector.get(self.ctx.servicesMap.get('systemSetupService'));
systemSetupService.getSetupState().subscribe(setupState => {
  console.log('Get Setup State:', setupState);
});
```

**8. getClaimInfo**

```javascript
const $injector = self.ctx.$scope.$injector;
const systemSetupService = $injector.get(self.ctx.servicesMap.get('systemSetupService'));
const claimToken = 'your-claim-token';
systemSetupService.getClaimInfo(claimToken).subscribe(claimInfo => {
  console.log('Get Claim Info:', claimInfo);
});
```

**9. requestClaim**

```javascript
const $injector = self.ctx.$scope.$injector;
const systemSetupService = $injector.get(self.ctx.servicesMap.get('systemSetupService'));
systemSetupService.requestClaim().subscribe(requestClaim => {
  console.log('Request Claim:', requestClaim);
});
```

**10. applyLicenseKey**

```javascript
const $injector = self.ctx.$scope.$injector;
const systemSetupService = $injector.get(self.ctx.servicesMap.get('systemSetupService'));
const secret = 'your-secret';
systemSetupService.applyLicenseKey(secret).subscribe(applyLicenseKey => {
  console.log('Apply License Key:', applyLicenseKey);
});
```

**11. changeLicenseKey**

```javascript
const $injector = self.ctx.$scope.$injector;
const systemSetupService = $injector.get(self.ctx.servicesMap.get('systemSetupService'));
const secret = 'your-secret';
systemSetupService.changeLicenseKey(secret).subscribe(changeLicenseKey => {
  console.log('Change License Key:', changeLicenseKey);
});
```

**12. previewLicenseKey**

```javascript
const $injector = self.ctx.$scope.$injector;
const systemSetupService = $injector.get(self.ctx.servicesMap.get('systemSetupService'));
const secret = 'your-secret';
systemSetupService.previewLicenseKey(secret).subscribe(previewLicenseKey => {
  console.log('Preview License Key:', previewLicenseKey);
});
```

**13. completeSetup**

```javascript
const $injector = self.ctx.$scope.$injector;
const systemSetupService = $injector.get(self.ctx.servicesMap.get('systemSetupService'));
const request = {  // SystemSetupRequest object
  // ... set the fields you need
};
systemSetupService.completeSetup(request).subscribe(completeSetup => {
  console.log('Complete Setup:', completeSetup);
});
```

**14. confirmNonProduction**

```javascript
const $injector = self.ctx.$scope.$injector;
const systemSetupService = $injector.get(self.ctx.servicesMap.get('systemSetupService'));
systemSetupService.confirmNonProduction().subscribe(confirmNonProduction => {
  console.log('Confirm Non Production:', confirmNonProduction);
});
```

**15. initTranslate**

```javascript
const $injector = self.ctx.$scope.$injector;
const systemSetupService = $injector.get(self.ctx.servicesMap.get('systemSetupService'));
const setupCompleted = true;
systemSetupService.initTranslate(setupCompleted).subscribe(initTranslate => {
  console.log('Init Translate:', initTranslate);
});
```
