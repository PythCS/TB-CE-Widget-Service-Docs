# SYSTEM SETUP SERVICE

Part of the [ThingsBoard CE Widget Services Documentation](../DOCUMENTATION.md).

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const systemSetupService = $injector.get(self.ctx.servicesMap.get('systemSetupService'));
```

**1. checkSetupState**

```javascript
systemSetupService.checkSetupState().subscribe(setupState => {
  console.log('Check Setup State:', setupState);
});
```

**2. readableState**

```javascript
systemSetupService.readableState('your-setupinfo-value').subscribe(readableState => {
  console.log('Readable State:', readableState);
});
```

**3. handleSetupState**

```javascript
systemSetupService.handleSetupState('your-state-value').subscribe(handleSetupState => {
  console.log('Handle Setup State:', handleSetupState);
});
```

**4. finishSetup**

```javascript
systemSetupService.finishSetup().subscribe(finishSetup => {
  console.log('Finish Setup:', finishSetup);
});
```

**5. makeStartUpHandOff**

```javascript
systemSetupService.makeStartUpHandOff(true).subscribe(makeStartUpHandOff => {
  console.log('Make Start Up Hand Off:', makeStartUpHandOff);
});
```

**6. getState**

```javascript
systemSetupService.getState().subscribe(state => {
  console.log('Get State:', state);
});
```

**7. getSetupState**

```javascript
systemSetupService.getSetupState().subscribe(setupState => {
  console.log('Get Setup State:', setupState);
});
```

**8. getClaimInfo**

```javascript
systemSetupService.getClaimInfo('your-access-token').subscribe(claimInfo => {
  console.log('Get Claim Info:', claimInfo);
});
```

**9. requestClaim**

```javascript
systemSetupService.requestClaim().subscribe(requestClaim => {
  console.log('Request Claim:', requestClaim);
});
```

**10. applyLicenseKey**

```javascript
systemSetupService.applyLicenseKey('your-secret-value').subscribe(applyLicenseKey => {
  console.log('Apply License Key:', applyLicenseKey);
});
```

**11. changeLicenseKey**

```javascript
systemSetupService.changeLicenseKey('your-secret-value').subscribe(changeLicenseKey => {
  console.log('Change License Key:', changeLicenseKey);
});
```

**12. previewLicenseKey**

```javascript
systemSetupService.previewLicenseKey('your-secret-value').subscribe(previewLicenseKey => {
  console.log('Preview License Key:', previewLicenseKey);
});
```

**13. completeSetup**

```javascript
systemSetupService.completeSetup('your-request-value').subscribe(result => {
  console.log('Complete Setup:', result);
});
```

**14. confirmNonProduction**

```javascript
systemSetupService.confirmNonProduction().subscribe(result => {
  console.log('Confirm Non Production:', result);
});
```

**15. initTranslate**

```javascript
systemSetupService.initTranslate(true).subscribe(initTranslate => {
  console.log('Init Translate:', initTranslate);
});
```
