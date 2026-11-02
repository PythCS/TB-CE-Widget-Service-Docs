# AGENT SERVICE

Part of the [ThingsBoard CE Widget Services Documentation](../DOCUMENTATION.md).

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
```

**1. getAgentById**

```javascript
agentService.getAgentById('your-agent-id').subscribe(agentById => {
  console.log('Get Agent By Id:', agentById);
});
```

**2. getAgentInfoById**

```javascript
agentService.getAgentInfoById('your-agent-id').subscribe(agentInfoById => {
  console.log('Get Agent Info By Id:', agentInfoById);
});
```

**3. getAgentInfosByIds**

```javascript
agentService.getAgentInfosByIds('your-agentids-value').subscribe(agentInfosByIds => {
  console.log('Get Agent Infos By Ids:', agentInfosByIds);
});
```

**4. getAgentInstallInstructions**

```javascript
agentService.getAgentInstallInstructions('your-agent-id', 'your-method-value').subscribe(agentInstallInstructions => {
  console.log('Get Agent Install Instructions:', agentInstallInstructions);
});
```

**5. getAgentProvisionInstructions**

```javascript
agentService.getAgentProvisionInstructions('your-agentprofile-id', 'your-method-value').subscribe(agentProvisionInstructions => {
  console.log('Get Agent Provision Instructions:', agentProvisionInstructions);
});
```

**6. upgradeAgent**

```javascript
agentService.upgradeAgent('your-agent-id', 'your-imageref-value').subscribe(upgradeAgent => {
  console.log('Upgrade Agent:', upgradeAgent);
});
```

**7. saveAgent**

```javascript
agentService.saveAgent('your-agent-value', 'your-entitygroupids-value').subscribe(agent => {
  console.log('Save Agent:', agent);
});
```

**8. join**

```javascript
agentService.join().subscribe(join => {
  console.log('Join:', join);
});
```

**9. deleteAgent**

```javascript
agentService.deleteAgent('your-agent-id').subscribe(result => {
  console.log('Delete Agent:', result);
});
```

**10. getTenantAgentInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
agentService.getTenantAgentInfos(pageLink).subscribe(tenantAgentInfos => {
  console.log('Get Tenant Agent Infos:', tenantAgentInfos);
});
```

**11. getCustomerAgentInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
agentService.getCustomerAgentInfos('your-customer-id', pageLink).subscribe(customerAgentInfos => {
  console.log('Get Customer Agent Infos:', customerAgentInfos);
});
```

**12. getAgentProfileById**

```javascript
agentService.getAgentProfileById('your-agentprofile-id').subscribe(agentProfileById => {
  console.log('Get Agent Profile By Id:', agentProfileById);
});
```

**13. getAgentProfileInfoById**

```javascript
agentService.getAgentProfileInfoById('your-agentprofile-id').subscribe(agentProfileInfoById => {
  console.log('Get Agent Profile Info By Id:', agentProfileInfoById);
});
```

**14. saveAgentProfile**

```javascript
agentService.saveAgentProfile('your-agentprofile-value', 'your-appprofileids-value').subscribe(agentProfile => {
  console.log('Save Agent Profile:', agentProfile);
});
```

**15. deleteAgentProfile**

```javascript
agentService.deleteAgentProfile('your-agentprofile-id').subscribe(result => {
  console.log('Delete Agent Profile:', result);
});
```

**16. setDefaultAgentProfile**

```javascript
agentService.setDefaultAgentProfile('your-agentprofile-id').subscribe(defaultAgentProfile => {
  console.log('Set Default Agent Profile:', defaultAgentProfile);
});
```

**17. getDefaultAgentProfileInfo**

```javascript
agentService.getDefaultAgentProfileInfo().subscribe(defaultAgentProfileInfo => {
  console.log('Get Default Agent Profile Info:', defaultAgentProfileInfo);
});
```

**18. getTenantAgentProfiles**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
agentService.getTenantAgentProfiles(pageLink).subscribe(tenantAgentProfiles => {
  console.log('Get Tenant Agent Profiles:', tenantAgentProfiles);
});
```

**19. getTenantAgentProfileInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
agentService.getTenantAgentProfileInfos(pageLink).subscribe(tenantAgentProfileInfos => {
  console.log('Get Tenant Agent Profile Infos:', tenantAgentProfileInfos);
});
```

**20. getAgentProfileAppProfileInfos**

```javascript
agentService.getAgentProfileAppProfileInfos('your-agentprofile-id').subscribe(agentProfileAppProfileInfos => {
  console.log('Get Agent Profile App Profile Infos:', agentProfileAppProfileInfos);
});
```

**21. assignAppProfileToAgentProfile**

```javascript
agentService.assignAppProfileToAgentProfile('your-agentprofile-id', 'your-applicationprofile-id').subscribe(result => {
  console.log('Assign App Profile To Agent Profile:', result);
});
```

**22. assignAppProfilesToAgentProfile**

```javascript
agentService.assignAppProfilesToAgentProfile('your-agentprofile-id', 'your-appprofileids-value').subscribe(result => {
  console.log('Assign App Profiles To Agent Profile:', result);
});
```

**23. join**

```javascript
agentService.join().subscribe(join => {
  console.log('Join:', join);
});
```

**24. setAppProfileRelatesOnAutoDiscovery**

```javascript
agentService.setAppProfileRelatesOnAutoDiscovery('your-agentprofile-id', 'your-applicationprofile-id', true).subscribe(result => {
  console.log('Set App Profile Relates On Auto Discovery:', result);
});
```

**25. previewBulkOperation**

```javascript
agentService.previewBulkOperation('your-agentprofile-id', 'your-applicationprofile-id', 'your-request-value').subscribe(previewBulkOperation => {
  console.log('Preview Bulk Operation:', previewBulkOperation);
});
```

**26. bulkOperation**

```javascript
agentService.bulkOperation('your-agentprofile-id', 'your-applicationprofile-id', 'your-request-value').subscribe(bulkOperation => {
  console.log('Bulk Operation:', bulkOperation);
});
```

**27. getAgentApplicationInfoById**

```javascript
agentService.getAgentApplicationInfoById('your-application-id').subscribe(agentApplicationInfoById => {
  console.log('Get Agent Application Info By Id:', agentApplicationInfoById);
});
```

**28. getAgentApplicationsByAgentId**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
agentService.getAgentApplicationsByAgentId('your-agent-id', pageLink).subscribe(agentApplicationsByAgentId => {
  console.log('Get Agent Applications By Agent Id:', agentApplicationsByAgentId);
});
```

**29. getAgentApplicationByRelatedEntity**

```javascript
agentService.getAgentApplicationByRelatedEntity('your-entitytype-value', 'your-entity-id').subscribe(agentApplicationByRelatedEntity => {
  console.log('Get Agent Application By Related Entity:', agentApplicationByRelatedEntity);
});
```

**30. updateAgentApplication**

```javascript
agentService.updateAgentApplication('your-application-value').subscribe(agentApplication => {
  console.log('Update Agent Application:', agentApplication);
});
```

**31. installAgentApp**

```javascript
agentService.installAgentApp('your-request-value').subscribe(installAgentApp => {
  console.log('Install Agent App:', installAgentApp);
});
```

**32. createAgentAppEvent**

```javascript
agentService.createAgentAppEvent('your-application-id', 'your-request-value').subscribe(agentAppEvent => {
  console.log('Create Agent App Event:', agentAppEvent);
});
```

**33. cancelAgentAppEvent**

```javascript
agentService.cancelAgentAppEvent('your-application-id', 'your-event-id').subscribe(result => {
  console.log('Cancel Agent App Event:', result);
});
```

**34. getAgentAppEventById**

```javascript
agentService.getAgentAppEventById('your-event-id').subscribe(agentAppEventById => {
  console.log('Get Agent App Event By Id:', agentAppEventById);
});
```

**35. getAgentAppEvents**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
agentService.getAgentAppEvents('your-application-id', pageLink, 'your-actiontype-value', 'your-processingstatus-value').subscribe(agentAppEvents => {
  console.log('Get Agent App Events:', agentAppEvents);
});
```

**36. getAgentAppEventsByAgentId**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
agentService.getAgentAppEventsByAgentId('your-agent-id', pageLink).subscribe(agentAppEventsByAgentId => {
  console.log('Get Agent App Events By Agent Id:', agentAppEventsByAgentId);
});
```

**37. getAgentAppEventInfosByAgentId**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
agentService.getAgentAppEventInfosByAgentId('your-agent-id', pageLink, 'your-actiontype-value', 'your-processingstatus-value').subscribe(agentAppEventInfosByAgentId => {
  console.log('Get Agent App Event Infos By Agent Id:', agentAppEventInfosByAgentId);
});
```

**38. mergeForPreview**

```javascript
agentService.mergeForPreview('your-templateversion-value', 'your-apptype-value', 'your-application-value', 'your-composetype-value', 'your-relatedentity-id', 'your-actiontype-value', true).subscribe(mergeForPreview => {
  console.log('Merge For Preview:', mergeForPreview);
});
```

**39. assignRelatedEntity**

```javascript
agentService.assignRelatedEntity('your-application-id', 'your-relatedentity-id').subscribe(relatedEntity => {
  console.log('Assign Related Entity:', relatedEntity);
});
```

**40. unassignRelatedEntity**

```javascript
agentService.unassignRelatedEntity('your-application-id').subscribe(relatedEntity => {
  console.log('Unassign Related Entity:', relatedEntity);
});
```

**41. detachFromProfile**

```javascript
agentService.detachFromProfile('your-application-id').subscribe(result => {
  console.log('Detach From Profile:', result);
});
```

**42. attachToProfile**

```javascript
agentService.attachToProfile('your-application-id', 'your-profile-id').subscribe(result => {
  console.log('Attach To Profile:', result);
});
```

**43. getLatestAgentAppTemplate**

```javascript
agentService.getLatestAgentAppTemplate('your-apptype-value', 'your-configtype-value').subscribe(latestAgentAppTemplate => {
  console.log('Get Latest Agent App Template:', latestAgentAppTemplate);
});
```

**44. getAgentAppTemplateByVersion**

```javascript
agentService.getAgentAppTemplateByVersion('your-apptype-value', 'your-configtype-value', 'your-version-value').subscribe(agentAppTemplateByVersion => {
  console.log('Get Agent App Template By Version:', agentAppTemplateByVersion);
});
```

**45. getAgentAppTemplates**

```javascript
agentService.getAgentAppTemplates().subscribe(agentAppTemplates => {
  console.log('Get Agent App Templates:', agentAppTemplates);
});
```

**46. getAgentAppProfilesByAppType**

```javascript
agentService.getAgentAppProfilesByAppType('your-apptype-value').subscribe(agentAppProfilesByAppType => {
  console.log('Get Agent App Profiles By App Type:', agentAppProfilesByAppType);
});
```

**47. getAgentAppTemplatesByAppType**

```javascript
agentService.getAgentAppTemplatesByAppType('your-apptype-value', 'your-configtype-value').subscribe(agentAppTemplatesByAppType => {
  console.log('Get Agent App Templates By App Type:', agentAppTemplatesByAppType);
});
```

**48. getAgentAppProfileById**

```javascript
agentService.getAgentAppProfileById('your-profile-id').subscribe(agentAppProfileById => {
  console.log('Get Agent App Profile By Id:', agentAppProfileById);
});
```

**49. getAgentAppProfileInfoById**

```javascript
agentService.getAgentAppProfileInfoById('your-profile-id').subscribe(agentAppProfileInfoById => {
  console.log('Get Agent App Profile Info By Id:', agentAppProfileInfoById);
});
```

**50. saveAgentAppProfile**

```javascript
agentService.saveAgentAppProfile('your-profile-value').subscribe(agentAppProfile => {
  console.log('Save Agent App Profile:', agentAppProfile);
});
```

**51. deleteAgentAppProfile**

```javascript
agentService.deleteAgentAppProfile('your-profile-id').subscribe(result => {
  console.log('Delete Agent App Profile:', result);
});
```

**52. getTenantAgentAppProfiles**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
agentService.getTenantAgentAppProfiles(pageLink).subscribe(tenantAgentAppProfiles => {
  console.log('Get Tenant Agent App Profiles:', tenantAgentAppProfiles);
});
```

**53. getAgentAppProfilesByIds**

```javascript
agentService.getAgentAppProfilesByIds('your-profileids-value').subscribe(agentAppProfilesByIds => {
  console.log('Get Agent App Profiles By Ids:', agentAppProfilesByIds);
});
```

**54. materializeAgentAppProfile**

```javascript
agentService.materializeAgentAppProfile('your-apptype-value', 'your-templateversion-value', 'your-composetype-value').subscribe(materializeAgentAppProfile => {
  console.log('Materialize Agent App Profile:', materializeAgentAppProfile);
});
```

**55. mergeProfileForPreview**

```javascript
agentService.mergeProfileForPreview('your-templateversion-value', 'your-profile-value', 'your-composetype-value', 'your-actiontype-value', true).subscribe(mergeProfileForPreview => {
  console.log('Merge Profile For Preview:', mergeProfileForPreview);
});
```

**56. getAgentAppUnits**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
agentService.getAgentAppUnits('your-application-id', pageLink, 'your-type-value').subscribe(agentAppUnits => {
  console.log('Get Agent App Units:', agentAppUnits);
});
```

**57. getAgentBulkAction**

```javascript
agentService.getAgentBulkAction('your-bulkaction-id').subscribe(agentBulkAction => {
  console.log('Get Agent Bulk Action:', agentBulkAction);
});
```

**58. getAgentProfileBulkActions**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
agentService.getAgentProfileBulkActions('your-agentprofile-id', pageLink).subscribe(agentProfileBulkActions => {
  console.log('Get Agent Profile Bulk Actions:', agentProfileBulkActions);
});
```

**59. getAgentProfileAppProfileBulkActions**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
agentService.getAgentProfileAppProfileBulkActions('your-agentprofile-id', 'your-applicationprofile-id', pageLink).subscribe(agentProfileAppProfileBulkActions => {
  console.log('Get Agent Profile App Profile Bulk Actions:', agentProfileAppProfileBulkActions);
});
```

**60. getAgentBulkActionEventStats**

```javascript
agentService.getAgentBulkActionEventStats('your-bulkaction-id').subscribe(agentBulkActionEventStats => {
  console.log('Get Agent Bulk Action Event Stats:', agentBulkActionEventStats);
});
```

**61. getAgentBulkActionEvents**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
agentService.getAgentBulkActionEvents('your-bulkaction-id', pageLink, 'your-actiontype-value', 'your-processingstatus-value').subscribe(agentBulkActionEvents => {
  console.log('Get Agent Bulk Action Events:', agentBulkActionEvents);
});
```

**62. getRelatedEntityCandidates**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
agentService.getRelatedEntityCandidates('your-entitytype-value', pageLink, 'your-currententity-id').subscribe(relatedEntityCandidates => {
  console.log('Get Related Entity Candidates:', relatedEntityCandidates);
});
```
