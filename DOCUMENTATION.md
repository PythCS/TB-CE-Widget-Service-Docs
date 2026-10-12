# ThingsBoard CE Widget Services Documentation

*Generated from ThingsBoard CE source code. Copy-paste ready examples.*

---

## Using Services in Widgets/Custom Actions

Using services in custom actions is slightly different than in custom widget development.

In custom actions you use `widgetContext` — in widget development you use `self.ctx`. Same services, different context variable.

**Example Custom Action:**

```javascript
const $injector = widgetContext.$scope.$injector;
const userService = $injector.get(widgetContext.servicesMap.get('userService'));
```

**Example Widget Development:**

```javascript
const $injector = self.ctx.$scope.$injector;
const userService = $injector.get(self.ctx.servicesMap.get('userService'));
```

---

## Using Page Links

PageLinks are pagination helpers that prevent overloading the ThingsBoard server when you have 1000+ results. They specify page size and offset.

Create a page link using `self.ctx.pageLink`:

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
```

- `pageSize` (10) — results per page
- `pageNumber` (0) — zero-based page index
- `searchText` — optional text filter
- `sortProperty` — field to sort by
- `sortOrder` — 'ASC' or 'DESC'

---

## Table of Contents

- [ADMIN SERVICE](#admin-service)
- [AGENT SERVICE](#agent-service)
- [AI CHAT SERVICE](#ai-chat-service)
- [AI MODEL SERVICE](#ai-model-service)
- [ALARM COMMENT SERVICE](#alarm-comment-service)
- [ALARM RULES SERVICE](#alarm-rules-service)
- [ALARM SERVICE](#alarm-service)
- [API KEY SERVICE](#api-key-service)
- [ASSET PROFILE SERVICE](#asset-profile-service)
- [ASSET SERVICE](#asset-service)
- [ATTRIBUTE SERVICE](#attribute-service)
- [AUDIT LOG SERVICE](#audit-log-service)
- [BLOB ENTITY SERVICE](#blob-entity-service)
- [CALCULATED FIELDS SERVICE](#calculated-fields-service)
- [COMPONENT DESCRIPTOR SERVICE](#component-descriptor-service)
- [CONVERTER LIBRARY SERVICE](#converter-library-service)
- [CONVERTER SERVICE](#converter-service)
- [CUSTOM MENU SERVICE](#custom-menu-service)
- [CUSTOM TRANSLATION SERVICE](#custom-translation-service)
- [CUSTOMER SERVICE](#customer-service)
- [DASHBOARD REPORT SERVICE](#dashboard-report-service)
- [DASHBOARD SERVICE](#dashboard-service)
- [DEVICE PROFILE SERVICE](#device-profile-service)
- [DEVICE SERVICE](#device-service)
- [DOMAIN SERVICE](#domain-service)
- [EDGE SERVICE](#edge-service)
- [ENTITIES VERSION CONTROL SERVICE](#entities-version-control-service)
- [ENTITY GROUP SERVICE](#entity-group-service)
- [ENTITY RELATION SERVICE](#entity-relation-service)
- [ENTITY SERVICE](#entity-service)
- [ENTITY VIEW SERVICE](#entity-view-service)
- [EVENT SERVICE](#event-service)
- [GIT HUB SERVICE](#git-hub-service)
- [IMAGE SERVICE](#image-service)
- [INTEGRATION SERVICE](#integration-service)
- [JOB SERVICE](#job-service)
- [MOBILE APP SERVICE](#mobile-app-service)
- [MOBILE APPLICATION SERVICE](#mobile-application-service)
- [NOTIFICATION SERVICE](#notification-service)
- [O AUTH 2 SERVICE](#o-auth-2-service)
- [OTA PACKAGE SERVICE](#ota-package-service)
- [QUEUE SERVICE](#queue-service)
- [REPORT SERVICE](#report-service)
- [REPORT TEMPLATE SERVICE](#report-template-service)
- [RESOURCE SERVICE](#resource-service)
- [ROLE SERVICE](#role-service)
- [RULE CHAIN SERVICE](#rule-chain-service)
- [SCHEDULER EVENT SERVICE](#scheduler-event-service)
- [SECRET STORAGE SERVICE](#secret-storage-service)
- [SELF REGISTRATION SERVICE](#self-registration-service)
- [SIGNUP SERVICE](#signup-service)
- [SOLUTIONS CREATOR SERVICE](#solutions-creator-service)
- [SYSTEM SETUP SERVICE](#system-setup-service)
- [TENANT PROFILE SERVICE](#tenant-profile-service)
- [TENANT SERVICE](#tenant-service)
- [TRENDZ SERVICE](#trendz-service)
- [TRENDZ SETTINGS SERVICE](#trendz-settings-service)
- [TWO FACTOR AUTHENTICATION SERVICE](#two-factor-authentication-service)
- [UI SETTINGS SERVICE](#ui-settings-service)
- [USAGE INFO SERVICE](#usage-info-service)
- [USER PERMISSIONS SERVICE](#user-permissions-service)
- [USER SERVICE](#user-service)
- [USER SETTINGS SERVICE](#user-settings-service)
- [WHITE LABELING SERVICE](#white-labeling-service)
- [WIDGET SERVICE](#widget-service)

---

### **ADMIN SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const adminService = $injector.get(self.ctx.servicesMap.get('adminService'));
```

**1. sendTestMail**

```javascript
adminService.sendTestMail('your-adminsettings-value').subscribe(result => {
  console.log('Send Test Mail:', result);
});
```

**2. sendTestSms**

```javascript
adminService.sendTestSms('your-testsmsrequest-value').subscribe(result => {
  console.log('Send Test Sms:', result);
});
```

**3. getSecuritySettings**

```javascript
adminService.getSecuritySettings().subscribe(securitySettings => {
  console.log('Get Security Settings:', securitySettings);
});
```

**4. saveSecuritySettings**

```javascript
adminService.saveSecuritySettings('your-securitysettings-value').subscribe(securitySettings => {
  console.log('Save Security Settings:', securitySettings);
});
```

**5. getJwtSettings**

```javascript
adminService.getJwtSettings().subscribe(jwtSettings => {
  console.log('Get Jwt Settings:', jwtSettings);
});
```

**6. saveJwtSettings**

```javascript
adminService.saveJwtSettings('your-jwtsettings-value').subscribe(jwtSettings => {
  console.log('Save Jwt Settings:', jwtSettings);
});
```

**7. getRepositorySettings**

```javascript
adminService.getRepositorySettings().subscribe(repositorySettings => {
  console.log('Get Repository Settings:', repositorySettings);
});
```

**8. saveRepositorySettings**

```javascript
adminService.saveRepositorySettings('your-repositorysettings-value').subscribe(repositorySettings => {
  console.log('Save Repository Settings:', repositorySettings);
});
```

**9. checkRepositoryAccess**

```javascript
adminService.checkRepositoryAccess('your-repositorysettings-value').subscribe(result => {
  console.log('Check Repository Access:', result);
});
```

**10. getRepositorySettingsInfo**

```javascript
adminService.getRepositorySettingsInfo().subscribe(repositorySettingsInfo => {
  console.log('Get Repository Settings Info:', repositorySettingsInfo);
});
```

**11. getAutoCommitSettings**

```javascript
adminService.getAutoCommitSettings().subscribe(autoCommitSettings => {
  console.log('Get Auto Commit Settings:', autoCommitSettings);
});
```

**12. autoCommitSettingsExists**

```javascript
adminService.autoCommitSettingsExists().subscribe(autoCommitSettingsExists => {
  console.log('Auto Commit Settings Exists:', autoCommitSettingsExists);
});
```

**13. saveAutoCommitSettings**

```javascript
adminService.saveAutoCommitSettings('your-autocommitsettings-value').subscribe(autoCommitSettings => {
  console.log('Save Auto Commit Settings:', autoCommitSettings);
});
```

**14. checkUpdates**

```javascript
adminService.checkUpdates().subscribe(updates => {
  console.log('Check Updates:', updates);
});
```

**15. getFeaturesInfo**

```javascript
adminService.getFeaturesInfo().subscribe(featuresInfo => {
  console.log('Get Features Info:', featuresInfo);
});
```

**16. getLicenseUsageInfo**

```javascript
adminService.getLicenseUsageInfo().subscribe(licenseUsageInfo => {
  console.log('Get License Usage Info:', licenseUsageInfo);
});
```

**17. getSubscriptionInfo**

```javascript
adminService.getSubscriptionInfo().subscribe(subscriptionInfo => {
  console.log('Get Subscription Info:', subscriptionInfo);
});
```

**18. refreshLicense**

```javascript
adminService.refreshLicense().subscribe(refreshLicense => {
  console.log('Refresh License:', refreshLicense);
});
```

**19. getLoginProcessingUrl**

```javascript
adminService.getLoginProcessingUrl().subscribe(loginProcessingUrl => {
  console.log('Get Login Processing Url:', loginProcessingUrl);
});
```

**20. generateAccessToken**

```javascript
adminService.generateAccessToken().subscribe(accessToken => {
  console.log('Generate Access Token:', accessToken);
});
```

**21. getMailConfigTemplate**

```javascript
adminService.getMailConfigTemplate().subscribe(mailConfigTemplate => {
  console.log('Get Mail Config Template:', mailConfigTemplate);
});
```

---

### **AGENT SERVICE**

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

---

### **AI CHAT SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const aiChatService = $injector.get(self.ctx.servicesMap.get('aiChatService'));
```

**1. listChats**

```javascript
aiChatService.listChats().subscribe(chats => {
  console.log('List Chats:', chats);
});
```

**2. createChat**

```javascript
aiChatService.createChat('your-chat-value').subscribe(chat => {
  console.log('Create Chat:', chat);
});
```

**3. updatedChat**

```javascript
aiChatService.updatedChat('your-chat-id', 'your-chat-value').subscribe(result => {
  console.log('Updated Chat:', result);
});
```

**4. deleteChat**

```javascript
aiChatService.deleteChat('your-chat-id').subscribe(result => {
  console.log('Delete Chat:', result);
});
```

**5. getChatMessages**

```javascript
aiChatService.getChatMessages('your-chat-id').subscribe(chatMessages => {
  console.log('Get Chat Messages:', chatMessages);
});
```

**6. generateDashboard**

```javascript
aiChatService.generateDashboard('your-device-id', 'your-timeserieskeys-value').subscribe(dashboard => {
  console.log('Generate Dashboard:', dashboard);
});
```

**7. resolveToolApproval**

```javascript
aiChatService.resolveToolApproval('your-result-value').subscribe(resolveToolApproval => {
  console.log('Resolve Tool Approval:', resolveToolApproval);
});
```

**8. sendChatMessage**

```javascript
aiChatService.sendChatMessage('your-chat-id', 'your-request-value').subscribe(chatMessage => {
  console.log('Send Chat Message:', chatMessage);
});
```

**9. parseEventStrings**

```javascript
aiChatService.parseEventStrings('your-input-value').subscribe(parseEventStrings => {
  console.log('Parse Event Strings:', parseEventStrings);
});
```

**10. parseSingleEvent**

```javascript
aiChatService.parseSingleEvent('your-input-value').subscribe(parseSingleEvent => {
  console.log('Parse Single Event:', parseSingleEvent);
});
```

---

### **AI MODEL SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const aiModelService = $injector.get(self.ctx.servicesMap.get('aiModelService'));
```

**1. saveAiModel**

```javascript
aiModelService.saveAiModel('your-aimodel-value').subscribe(aiModel => {
  console.log('Save Ai Model:', aiModel);
});
```

**2. getAiModels**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
aiModelService.getAiModels(pageLink).subscribe(aiModels => {
  console.log('Get Ai Models:', aiModels);
});
```

**3. getAiModelById**

```javascript
aiModelService.getAiModelById('your-aimodel-id').subscribe(aiModelById => {
  console.log('Get Ai Model By Id:', aiModelById);
});
```

**4. checkConnectivity**

```javascript
aiModelService.checkConnectivity('your-aimodelwithusermsg-value').subscribe(connectivity => {
  console.log('Check Connectivity:', connectivity);
});
```

---

### **ALARM COMMENT SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const alarmCommentService = $injector.get(self.ctx.servicesMap.get('alarmCommentService'));
```

**1. saveAlarmComment**

```javascript
alarmCommentService.saveAlarmComment('your-alarm-id', 'your-alarmcomment-value').subscribe(alarmComment => {
  console.log('Save Alarm Comment:', alarmComment);
});
```

**2. getAlarmComments**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
alarmCommentService.getAlarmComments('your-alarm-id', pageLink).subscribe(alarmComments => {
  console.log('Get Alarm Comments:', alarmComments);
});
```

**3. deleteAlarmComments**

```javascript
alarmCommentService.deleteAlarmComments('your-alarm-id', 'your-comment-id').subscribe(result => {
  console.log('Delete Alarm Comments:', result);
});
```

---

### **ALARM RULES SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const alarmRulesService = $injector.get(self.ctx.servicesMap.get('alarmRulesService'));
```

**1. getAlarmRuleById**

```javascript
alarmRulesService.getAlarmRuleById('your-alarmrule-id').subscribe(alarmRuleById => {
  console.log('Get Alarm Rule By Id:', alarmRuleById);
});
```

**2. saveAlarmRule**

```javascript
alarmRulesService.saveAlarmRule('your-alarmrule-value').subscribe(alarmRule => {
  console.log('Save Alarm Rule:', alarmRule);
});
```

**3. deleteAlarmRule**

```javascript
alarmRulesService.deleteAlarmRule('your-alarmrule-id').subscribe(alarmRule => {
  console.log('Delete Alarm Rule:', alarmRule);
});
```

**4. getAlarmRules**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
alarmRulesService.getAlarmRules(pageLink, 'your-query-value').subscribe(alarmRules => {
  console.log('Get Alarm Rules:', alarmRules);
});
```

**5. getAlarmRulesByEntityId**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
alarmRulesService.getAlarmRulesByEntityId(pageLink).subscribe(alarmRulesByEntityId => {
  console.log('Get Alarm Rules By Entity Id:', alarmRulesByEntityId);
});
```

**6. testScript**

```javascript
alarmRulesService.testScript('your-inputparams-value').subscribe(testScript => {
  console.log('Test Script:', testScript);
});
```

**7. getLatestAlarmRuleDebugEvent**

```javascript
alarmRulesService.getLatestAlarmRuleDebugEvent('your--id').subscribe(latestAlarmRuleDebugEvent => {
  console.log('Get Latest Alarm Rule Debug Event:', latestAlarmRuleDebugEvent);
});
```

**8. getAlarmRuleNames**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
alarmRulesService.getAlarmRuleNames(pageLink).subscribe(alarmRuleNames => {
  console.log('Get Alarm Rule Names:', alarmRuleNames);
});
```

---

### **ALARM SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const alarmService = $injector.get(self.ctx.servicesMap.get('alarmService'));
```

**1. getAlarm**

```javascript
alarmService.getAlarm('your-alarm-id').subscribe(alarm => {
  console.log('Get Alarm:', alarm);
});
```

**2. getAlarmInfo**

```javascript
alarmService.getAlarmInfo('your-alarm-id').subscribe(alarmInfo => {
  console.log('Get Alarm Info:', alarmInfo);
});
```

**3. saveAlarm**

```javascript
alarmService.saveAlarm('your-alarm-value').subscribe(alarm => {
  console.log('Save Alarm:', alarm);
});
```

**4. ackAlarm**

```javascript
alarmService.ackAlarm('your-alarm-id').subscribe(alarm => {
  console.log('Ack Alarm:', alarm);
});
```

**5. clearAlarm**

```javascript
alarmService.clearAlarm('your-alarm-id').subscribe(alarm => {
  console.log('Clear Alarm:', alarm);
});
```

**6. assignAlarm**

```javascript
alarmService.assignAlarm('your-alarm-id', 'your-assignee-id').subscribe(result => {
  console.log('Assign Alarm:', result);
});
```

**7. unassignAlarm**

```javascript
alarmService.unassignAlarm('your-alarm-id').subscribe(result => {
  console.log('Unassign Alarm:', result);
});
```

**8. deleteAlarm**

```javascript
alarmService.deleteAlarm('your-alarm-id').subscribe(alarm => {
  console.log('Delete Alarm:', alarm);
});
```

**9. getAlarms**

```javascript
alarmService.getAlarms('your-query-value').subscribe(alarms => {
  console.log('Get Alarms:', alarms);
});
```

**10. getAlarmsV2**

```javascript
alarmService.getAlarmsV2('your-query-value').subscribe(alarmsV2 => {
  console.log('Get Alarms V 2:', alarmsV2);
});
```

**11. getAllAlarms**

```javascript
alarmService.getAllAlarms('your-query-value').subscribe(allAlarms => {
  console.log('Get All Alarms:', allAlarms);
});
```

**12. getAllAlarmsV2**

```javascript
alarmService.getAllAlarmsV2('your-query-value').subscribe(allAlarmsV2 => {
  console.log('Get All Alarms V 2:', allAlarmsV2);
});
```

**13. getHighestAlarmSeverity**

```javascript
alarmService.getHighestAlarmSeverity('your-entity-id', 'your-alarmsearchstatus-value', 'your-alarmstatus-value').subscribe(highestAlarmSeverity => {
  console.log('Get Highest Alarm Severity:', highestAlarmSeverity);
});
```

**14. getAlarmTypes**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
alarmService.getAlarmTypes(pageLink).subscribe(alarmTypes => {
  console.log('Get Alarm Types:', alarmTypes);
});
```

---

### **API KEY SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const apiKeyService = $injector.get(self.ctx.servicesMap.get('apiKeyService'));
```

**1. saveApiKey**

```javascript
apiKeyService.saveApiKey('your-api-key').subscribe(apiKey => {
  console.log('Save Api Key:', apiKey);
});
```

**2. deleteApiKey**

```javascript
apiKeyService.deleteApiKey('your--id').subscribe(result => {
  console.log('Delete Api Key:', result);
});
```

**3. updateApiKeyDescription**

```javascript
apiKeyService.updateApiKeyDescription('your--id', 'your-description-value').subscribe(apiKeyDescription => {
  console.log('Update Api Key Description:', apiKeyDescription);
});
```

**4. enableApiKey**

```javascript
apiKeyService.enableApiKey('your--id', true).subscribe(enableApiKey => {
  console.log('Enable Api Key:', enableApiKey);
});
```

**5. getUserApiKeys**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
apiKeyService.getUserApiKeys('your-user-id', pageLink).subscribe(userApiKeys => {
  console.log('Get User Api Keys:', userApiKeys);
});
```

---

### **ASSET PROFILE SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const assetProfileService = $injector.get(self.ctx.servicesMap.get('assetProfileService'));
```

**1. getAssetProfiles**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
assetProfileService.getAssetProfiles(pageLink).subscribe(assetProfiles => {
  console.log('Get Asset Profiles:', assetProfiles);
});
```

**2. getAssetProfile**

```javascript
assetProfileService.getAssetProfile('your-assetprofile-id').subscribe(assetProfile => {
  console.log('Get Asset Profile:', assetProfile);
});
```

**3. exportAssetProfile**

```javascript
assetProfileService.exportAssetProfile('your-assetprofile-id').subscribe(assetProfile => {
  console.log('Export Asset Profile:', assetProfile);
});
```

**4. saveAssetProfile**

```javascript
assetProfileService.saveAssetProfile('your-assetprofile-value').subscribe(assetProfile => {
  console.log('Save Asset Profile:', assetProfile);
});
```

**5. setDefaultAssetProfile**

```javascript
assetProfileService.setDefaultAssetProfile('your-assetprofile-id').subscribe(defaultAssetProfile => {
  console.log('Set Default Asset Profile:', defaultAssetProfile);
});
```

**6. getDefaultAssetProfileInfo**

```javascript
assetProfileService.getDefaultAssetProfileInfo().subscribe(defaultAssetProfileInfo => {
  console.log('Get Default Asset Profile Info:', defaultAssetProfileInfo);
});
```

**7. getAssetProfileInfo**

```javascript
assetProfileService.getAssetProfileInfo('your-assetprofile-id').subscribe(assetProfileInfo => {
  console.log('Get Asset Profile Info:', assetProfileInfo);
});
```

**8. getAssetProfileInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
assetProfileService.getAssetProfileInfos(pageLink).subscribe(assetProfileInfos => {
  console.log('Get Asset Profile Infos:', assetProfileInfos);
});
```

**9. getAssetProfilesByIds**

```javascript
assetProfileService.getAssetProfilesByIds('your-assetprofileids-value').subscribe(assetProfilesByIds => {
  console.log('Get Asset Profiles By Ids:', assetProfilesByIds);
});
```

**10. getAssetProfileNames**

```javascript
assetProfileService.getAssetProfileNames('your-activeonly-value').subscribe(assetProfileNames => {
  console.log('Get Asset Profile Names:', assetProfileNames);
});
```

---

### **ASSET SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const assetService = $injector.get(self.ctx.servicesMap.get('assetService'));

// Alternative: Direct context access
const assetService = self.ctx.assetService;
```

**1. getTenantAssets**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.assetService.getTenantAssets(pageLink, 'your-type-value').subscribe(tenantAssets => {
  console.log('Get Tenant Assets:', tenantAssets);
});
```

**2. getCustomerAssets**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.assetService.getCustomerAssets('your-customer-id', pageLink, 'your-type-value').subscribe(customerAssets => {
  console.log('Get Customer Assets:', customerAssets);
});
```

**3. getAsset**

```javascript
self.ctx.assetService.getAsset('your-asset-id').subscribe(asset => {
  console.log('Get Asset:', asset);
});
```

**4. getAssets**

```javascript
self.ctx.assetService.getAssets('your-assetids-value').subscribe(assets => {
  console.log('Get Assets:', assets);
});
```

**5. getUserAssets**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.assetService.getUserAssets(pageLink, 'your-type-value').subscribe(userAssets => {
  console.log('Get User Assets:', userAssets);
});
```

**6. getAllAssetInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.assetService.getAllAssetInfos(true, pageLink, 'your-assetprofile-id').subscribe(allAssetInfos => {
  console.log('Get All Asset Infos:', allAssetInfos);
});
```

**7. getCustomerAssetInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.assetService.getCustomerAssetInfos(true, 'your-customer-id', pageLink, 'your-assetprofile-id').subscribe(customerAssetInfos => {
  console.log('Get Customer Asset Infos:', customerAssetInfos);
});
```

**8. getAssetInfo**

```javascript
self.ctx.assetService.getAssetInfo('your-asset-id').subscribe(assetInfo => {
  console.log('Get Asset Info:', assetInfo);
});
```

**9. saveAsset**

```javascript
self.ctx.assetService.saveAsset('your-asset-value', 'your-entitygroupids-value').subscribe(asset => {
  console.log('Save Asset:', asset);
});
```

**10. getAssetTypes**

```javascript
self.ctx.assetService.getAssetTypes().subscribe(assetTypes => {
  console.log('Get Asset Types:', assetTypes);
});
```

**11. findByQuery**

```javascript
self.ctx.assetService.findByQuery('your-query-value').subscribe(byQuery => {
  console.log('Find By Query:', byQuery);
});
```

**12. findByName**

```javascript
self.ctx.assetService.findByName('your-assetname-value').subscribe(byName => {
  console.log('Find By Name:', byName);
});
```

**13. bulkImportAssets**

```javascript
self.ctx.assetService.bulkImportAssets('your-entitiesdata-value').subscribe(bulkImportAssets => {
  console.log('Bulk Import Assets:', bulkImportAssets);
});
```

---

### **ATTRIBUTE SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const attributeService = $injector.get(self.ctx.servicesMap.get('attributeService'));

// Alternative: Direct context access
const attributeService = self.ctx.attributeService;
```

**1. getEntityAttributes**

```javascript
self.ctx.attributeService.getEntityAttributes('your-entity-id', 'your-attributescope-value', 'your-keys-value').subscribe(entityAttributes => {
  console.log('Get Entity Attributes:', entityAttributes);
});
```

**2. deleteEntityAttributes**

```javascript
self.ctx.attributeService.deleteEntityAttributes('your-entity-id', 'your-attributescope-value', 'your-attributes-value').subscribe(entityAttributes => {
  console.log('Delete Entity Attributes:', entityAttributes);
});
```

**3. deleteEntityTimeseries**

```javascript
self.ctx.attributeService.deleteEntityTimeseries('your-entity-id', 'your-timeseries-value', 0, 0).subscribe(entityTimeseries => {
  console.log('Delete Entity Timeseries:', entityTimeseries);
});
```

**4. saveEntityAttributes**

```javascript
self.ctx.attributeService.saveEntityAttributes('your-entity-id', 'your-attributescope-value', 'your-attributes-value').subscribe(entityAttributes => {
  console.log('Save Entity Attributes:', entityAttributes);
});
```

**5. saveEntityTimeseries**

```javascript
self.ctx.attributeService.saveEntityTimeseries('your-entity-id', 'your-timeseriesscope-value', 'your-timeseries-value').subscribe(entityTimeseries => {
  console.log('Save Entity Timeseries:', entityTimeseries);
});
```

**6. getEntityTimeseries**

```javascript
self.ctx.attributeService.getEntityTimeseries('your-entity-id', 'your-keys-value', 0, 0, 'your-limit-value', 'your-agg-value', 0, 'your-orderby-value', 'your-usestrictdatatypes-value').subscribe(entityTimeseries => {
  console.log('Get Entity Timeseries:', entityTimeseries);
});
```

**7. getEntityTimeseriesLatest**

```javascript
self.ctx.attributeService.getEntityTimeseriesLatest('your-entity-id', 'your-keys-value').subscribe(entityTimeseriesLatest => {
  console.log('Get Entity Timeseries Latest:', entityTimeseriesLatest);
});
```

---

### **AUDIT LOG SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const auditLogService = $injector.get(self.ctx.servicesMap.get('auditLogService'));
```

**1. getAuditLogs**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
auditLogService.getAuditLogs(pageLink).subscribe(auditLogs => {
  console.log('Get Audit Logs:', auditLogs);
});
```

**2. getAuditLogsByCustomerId**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
auditLogService.getAuditLogsByCustomerId('your-customer-id', pageLink).subscribe(auditLogsByCustomerId => {
  console.log('Get Audit Logs By Customer Id:', auditLogsByCustomerId);
});
```

**3. getAuditLogsByUserId**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
auditLogService.getAuditLogsByUserId('your-user-id', pageLink).subscribe(auditLogsByUserId => {
  console.log('Get Audit Logs By User Id:', auditLogsByUserId);
});
```

**4. getAuditLogsByEntityId**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
auditLogService.getAuditLogsByEntityId('your-entity-id', pageLink).subscribe(auditLogsByEntityId => {
  console.log('Get Audit Logs By Entity Id:', auditLogsByEntityId);
});
```

---

### **BLOB ENTITY SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const blobEntityService = $injector.get(self.ctx.servicesMap.get('blobEntityService'));
```

**1. getBlobEntityInfo**

```javascript
blobEntityService.getBlobEntityInfo('your-blobentity-id').subscribe(blobEntityInfo => {
  console.log('Get Blob Entity Info:', blobEntityInfo);
});
```

**2. getBlobEntities**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
blobEntityService.getBlobEntities(pageLink, 'your-type-value').subscribe(blobEntities => {
  console.log('Get Blob Entities:', blobEntities);
});
```

**3. getBlobEntitiesByIds**

```javascript
blobEntityService.getBlobEntitiesByIds('your-blobentityids-value').subscribe(blobEntitiesByIds => {
  console.log('Get Blob Entities By Ids:', blobEntitiesByIds);
});
```

**4. downloadBlobEntity**

```javascript
blobEntityService.downloadBlobEntity('your-blobentity-id').subscribe(downloadBlobEntity => {
  console.log('Download Blob Entity:', downloadBlobEntity);
});
```

---

### **CALCULATED FIELDS SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const calculatedFieldsService = $injector.get(self.ctx.servicesMap.get('calculatedFieldsService'));
```

**1. getCalculatedFieldById**

```javascript
calculatedFieldsService.getCalculatedFieldById('your-calculatedfield-id').subscribe(field => {
  console.log('Get Calculated Field By Id:', field);
});
```

**2. saveCalculatedField**

```javascript
calculatedFieldsService.saveCalculatedField('your-calculatedfield-value').subscribe(calculatedField => {
  console.log('Save Calculated Field:', calculatedField);
});
```

**3. deleteCalculatedField**

```javascript
calculatedFieldsService.deleteCalculatedField('your-calculatedfield-id').subscribe(calculatedField => {
  console.log('Delete Calculated Field:', calculatedField);
});
```

**4. getCalculatedFields**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
calculatedFieldsService.getCalculatedFields(pageLink, 'your-query-value').subscribe(fields => {
  console.log('Get Calculated Fields:', fields);
});
```

**5. getCalculatedFieldsByEntityId**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
calculatedFieldsService.getCalculatedFieldsByEntityId(pageLink, 'your-type-value').subscribe(calculatedFieldsByEntityId => {
  console.log('Get Calculated Fields By Entity Id:', calculatedFieldsByEntityId);
});
```

**6. testScript**

```javascript
calculatedFieldsService.testScript('your-inputparams-value').subscribe(testScript => {
  console.log('Test Script:', testScript);
});
```

**7. getLatestCalculatedFieldDebugEvent**

```javascript
calculatedFieldsService.getLatestCalculatedFieldDebugEvent('your--id').subscribe(latestCalculatedFieldDebugEvent => {
  console.log('Get Latest Calculated Field Debug Event:', latestCalculatedFieldDebugEvent);
});
```

**8. getCalculatedFieldNames**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
calculatedFieldsService.getCalculatedFieldNames(pageLink, 'your-type-value').subscribe(calculatedFieldNames => {
  console.log('Get Calculated Field Names:', calculatedFieldNames);
});
```

**9. reprocessCalculatedField**

```javascript
calculatedFieldsService.reprocessCalculatedField('your--id', 0, 0).subscribe(reprocessCalculatedField => {
  console.log('Reprocess Calculated Field:', reprocessCalculatedField);
});
```

**10. getLastCalculatedFieldReprocessingJob**

```javascript
calculatedFieldsService.getLastCalculatedFieldReprocessingJob('your--id').subscribe(lastCalculatedFieldReprocessingJob => {
  console.log('Get Last Calculated Field Reprocessing Job:', lastCalculatedFieldReprocessingJob);
});
```

**11. validateCalculatedFieldReprocessing**

```javascript
calculatedFieldsService.validateCalculatedFieldReprocessing('your--id').subscribe(validateCalculatedFieldReprocessing => {
  console.log('Validate Calculated Field Reprocessing:', validateCalculatedFieldReprocessing);
});
```

---

### **COMPONENT DESCRIPTOR SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const componentDescriptorService = $injector.get(self.ctx.servicesMap.get('componentDescriptorService'));
```

**1. getComponentDescriptorsByType**

```javascript
componentDescriptorService.getComponentDescriptorsByType('your-componenttype-value', 'your-rulechaintype-value').subscribe(componentDescriptorsByType => {
  console.log('Get Component Descriptors By Type:', componentDescriptorsByType);
});
```

**2. getComponentDescriptorsByTypes**

```javascript
componentDescriptorService.getComponentDescriptorsByTypes('your-componenttypes-value', 'your-rulechaintype-value').subscribe(componentDescriptorsByTypes => {
  console.log('Get Component Descriptors By Types:', componentDescriptorsByTypes);
});
```

**3. getComponentDescriptorByClazz**

```javascript
componentDescriptorService.getComponentDescriptorByClazz('your-componentdescriptorclazz-value').subscribe(componentDescriptorByClazz => {
  console.log('Get Component Descriptor By Clazz:', componentDescriptorByClazz);
});
```

---

### **CONVERTER LIBRARY SERVICE**

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

---

### **CONVERTER SERVICE**

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

---

### **CUSTOM MENU SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const customMenuService = $injector.get(self.ctx.servicesMap.get('customMenuService'));
```

**1. getCustomMenu**

```javascript
customMenuService.getCustomMenu().subscribe(customMenu => {
  console.log('Get Custom Menu:', customMenu);
});
```

**2. loadCustomMenu**

```javascript
customMenuService.loadCustomMenu().subscribe(loadCustomMenu => {
  console.log('Load Custom Menu:', loadCustomMenu);
});
```

**3. getCustomMenuInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
customMenuService.getCustomMenuInfos(pageLink, 'your-scope-value', 'your-assigneetype-value').subscribe(customMenuInfos => {
  console.log('Get Custom Menu Infos:', customMenuInfos);
});
```

**4. getCustomMenuInfo**

```javascript
customMenuService.getCustomMenuInfo('your-custommenu-id').subscribe(customMenuInfo => {
  console.log('Get Custom Menu Info:', customMenuInfo);
});
```

**5. getCustomMenuConfig**

```javascript
customMenuService.getCustomMenuConfig('your-custommenu-id').subscribe(customMenuConfig => {
  console.log('Get Custom Menu Config:', customMenuConfig);
});
```

**6. getCustomMenuAssigneeList**

```javascript
customMenuService.getCustomMenuAssigneeList('your-custommenu-id').subscribe(customMenuAssigneeList => {
  console.log('Get Custom Menu Assignee List:', customMenuAssigneeList);
});
```

**7. updateCustomMenuConfig**

```javascript
customMenuService.updateCustomMenuConfig('your-custommenu-id', 'your-custommenuconfig-value').subscribe(customMenuConfig => {
  console.log('Update Custom Menu Config:', customMenuConfig);
});
```

**8. updateCustomMenuName**

```javascript
customMenuService.updateCustomMenuName('your-custommenu-id', 'your-name-value').subscribe(result => {
  console.log('Update Custom Menu Name:', result);
});
```

**9. assignCustomMenu**

```javascript
customMenuService.assignCustomMenu('your-custommenu-id', 'your-assigneetype-value', 'your-entityids-value').subscribe(result => {
  console.log('Assign Custom Menu:', result);
});
```

**10. saveCustomMenu**

```javascript
customMenuService.saveCustomMenu('your-custommenuinfo-value', 'your-assigntolist-value').subscribe(customMenu => {
  console.log('Save Custom Menu:', customMenu);
});
```

**11. deleteCustomMenu**

```javascript
customMenuService.deleteCustomMenu('your-custommenu-id').subscribe(customMenu => {
  console.log('Delete Custom Menu:', customMenu);
});
```

---

### **CUSTOM TRANSLATION SERVICE**

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

---

### **CUSTOMER SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const customerService = $injector.get(self.ctx.servicesMap.get('customerService'));

// Alternative: Direct context access
const customerService = self.ctx.customerService;
```

**1. getCustomers**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.customerService.getCustomers(pageLink).subscribe(customers => {
  console.log('Get Customers:', customers);
});
```

**2. getCustomer**

```javascript
self.ctx.customerService.getCustomer('your-customer-id').subscribe(customer => {
  console.log('Get Customer:', customer);
});
```

**3. getCustomerInfo**

```javascript
self.ctx.customerService.getCustomerInfo('your-customer-id').subscribe(customerInfo => {
  console.log('Get Customer Info:', customerInfo);
});
```

**4. saveCustomer**

```javascript
self.ctx.customerService.saveCustomer('your-customer-value', 'your-entitygroupids-value').subscribe(customer => {
  console.log('Save Customer:', customer);
});
```

**5. getCustomersByIds**

```javascript
self.ctx.customerService.getCustomersByIds('your-customerids-value').subscribe(customersByIds => {
  console.log('Get Customers By Ids:', customersByIds);
});
```

**6. getUserCustomers**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.customerService.getUserCustomers(pageLink).subscribe(userCustomers => {
  console.log('Get User Customers:', userCustomers);
});
```

**7. getAllCustomerInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.customerService.getAllCustomerInfos(true, pageLink).subscribe(allCustomerInfos => {
  console.log('Get All Customer Infos:', allCustomerInfos);
});
```

**8. getCustomerCustomerInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.customerService.getCustomerCustomerInfos(true, 'your-customer-id', pageLink).subscribe(customerCustomerInfos => {
  console.log('Get Customer Customer Infos:', customerCustomerInfos);
});
```

**9. getShortCustomerInfo**

```javascript
self.ctx.customerService.getShortCustomerInfo('your-customer-id').subscribe(shortCustomerInfo => {
  console.log('Get Short Customer Info:', shortCustomerInfo);
});
```

---

### **DASHBOARD REPORT SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const dashboardReportService = $injector.get(self.ctx.servicesMap.get('dashboardReportService'));

// Alternative: Direct context access
const dashboardReportService = self.ctx.reportService;
```

**1. loadReportParams**

```javascript
self.ctx.reportService.loadReportParams().subscribe(loadReportParams => {
  console.log('Load Report Params:', loadReportParams);
});
```

**2. onWaitForMap**

```javascript
self.ctx.reportService.onWaitForMap().subscribe(onWaitForMap => {
  console.log('On Wait For Map:', onWaitForMap);
});
```

**3. onWaitForWidget**

```javascript
self.ctx.reportService.onWaitForWidget().subscribe(onWaitForWidget => {
  console.log('On Wait For Widget:', onWaitForWidget);
});
```

**4. onMapLoaded**

```javascript
self.ctx.reportService.onMapLoaded('your-uu-id').subscribe(onMapLoaded => {
  console.log('On Map Loaded:', onMapLoaded);
});
```

**5. onWidgetLoaded**

```javascript
self.ctx.reportService.onWidgetLoaded('your-uu-id').subscribe(onWidgetLoaded => {
  console.log('On Widget Loaded:', onWidgetLoaded);
});
```

**6. downloadDashboardReport**

```javascript
self.ctx.reportService.downloadDashboardReport('your-dashboard-id', 'your-reporttype-value', 'your-state-value', 'your-timewindow-value').subscribe(downloadDashboardReport => {
  console.log('Download Dashboard Report:', downloadDashboardReport);
});
```

**7. downloadTestReport**

```javascript
self.ctx.reportService.downloadTestReport('your-reportconfig-value', 'your-reportsserverendpointurl-value').subscribe(downloadTestReport => {
  console.log('Download Test Report:', downloadTestReport);
});
```

**8. openReport**

```javascript
self.ctx.reportService.openReport('your-openreportmessage-value').subscribe(openReport => {
  console.log('Open Report:', openReport);
});
```

**9. pageHeight**

```javascript
self.ctx.reportService.pageHeight().subscribe(pageHeight => {
  console.log('Page Height:', pageHeight);
});
```

**10. waitForLayoutReady**

```javascript
self.ctx.reportService.waitForLayoutReady().subscribe(waitForLayoutReady => {
  console.log('Wait For Layout Ready:', waitForLayoutReady);
});
```

**11. waitForReportPage**

```javascript
self.ctx.reportService.waitForReportPage().subscribe(waitForReportPage => {
  console.log('Wait For Report Page:', waitForReportPage);
});
```

**12. waitForWebsocketData**

```javascript
self.ctx.reportService.waitForWebsocketData().subscribe(waitForWebsocketData => {
  console.log('Wait For Websocket Data:', waitForWebsocketData);
});
```

**13. waitWidgets**

```javascript
self.ctx.reportService.waitWidgets().subscribe(waitWidgets => {
  console.log('Wait Widgets:', waitWidgets);
});
```

**14. waitForWidgetsLoaded**

```javascript
self.ctx.reportService.waitForWidgetsLoaded().subscribe(waitForWidgetsLoaded => {
  console.log('Wait For Widgets Loaded:', waitForWidgetsLoaded);
});
```

**15. isReportPageDomReady**

```javascript
self.ctx.reportService.isReportPageDomReady().subscribe(isReportPageDomReady => {
  console.log('Is Report Page Dom Ready:', isReportPageDomReady);
});
```

**16. clearReport**

```javascript
self.ctx.reportService.clearReport().subscribe(report => {
  console.log('Clear Report:', report);
});
```

**17. loadUser**

```javascript
self.ctx.reportService.loadUser('your-access-token', 'your-public-id').subscribe(loadUser => {
  console.log('Load User:', loadUser);
});
```

**18. downloadReport**

```javascript
self.ctx.reportService.downloadReport('your-url-value', 'your-reportparams-value', 'your-params-value').subscribe(downloadReport => {
  console.log('Download Report:', downloadReport);
});
```

---

### **DASHBOARD SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const dashboardService = $injector.get(self.ctx.servicesMap.get('dashboardService'));

// Alternative: Direct context access
const dashboardService = self.ctx.dashboardService;
```

**1. getTenantDashboards**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.dashboardService.getTenantDashboards(pageLink).subscribe(tenantDashboards => {
  console.log('Get Tenant Dashboards:', tenantDashboards);
});
```

**2. getTenantDashboardsByTenantId**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.dashboardService.getTenantDashboardsByTenantId('your-tenant-id', pageLink).subscribe(tenantDashboardsByTenantId => {
  console.log('Get Tenant Dashboards By Tenant Id:', tenantDashboardsByTenantId);
});
```

**3. getDashboards**

```javascript
self.ctx.dashboardService.getDashboards('your-dashboardids-value').subscribe(dashboards => {
  console.log('Get Dashboards:', dashboards);
});
```

**4. getUserDashboards**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.dashboardService.getUserDashboards('your-user-id', 'your-operation-value', pageLink).subscribe(userDashboards => {
  console.log('Get User Dashboards:', userDashboards);
});
```

**5. getAllDashboards**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.dashboardService.getAllDashboards(true, pageLink).subscribe(allDashboards => {
  console.log('Get All Dashboards:', allDashboards);
});
```

**6. getCustomerDashboards**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.dashboardService.getCustomerDashboards(true, 'your-customer-id', pageLink).subscribe(customerDashboards => {
  console.log('Get Customer Dashboards:', customerDashboards);
});
```

**7. getGroupDashboards**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.dashboardService.getGroupDashboards('your-group-id', pageLink).subscribe(groupDashboards => {
  console.log('Get Group Dashboards:', groupDashboards);
});
```

**8. getDashboard**

```javascript
self.ctx.dashboardService.getDashboard('your-dashboard-id').subscribe(dashboard => {
  console.log('Get Dashboard:', dashboard);
});
```

**9. exportDashboard**

```javascript
self.ctx.dashboardService.exportDashboard('your-dashboard-id').subscribe(dashboard => {
  console.log('Export Dashboard:', dashboard);
});
```

**10. getDashboardInfo**

```javascript
self.ctx.dashboardService.getDashboardInfo('your-dashboard-id').subscribe(dashboardInfo => {
  console.log('Get Dashboard Info:', dashboardInfo);
});
```

**11. saveDashboard**

```javascript
self.ctx.dashboardService.saveDashboard('your-dashboard-value', 'your-entitygroupids-value').subscribe(dashboard => {
  console.log('Save Dashboard:', dashboard);
});
```

**12. getPublicDashboardLink**

```javascript
self.ctx.dashboardService.getPublicDashboardLink('your-dashboard-value', 'your-entitygroup-value').subscribe(publicDashboardLink => {
  console.log('Get Public Dashboard Link:', publicDashboardLink);
});
```

---

### **DEVICE PROFILE SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const deviceProfileService = $injector.get(self.ctx.servicesMap.get('deviceProfileService'));
```

**1. getDeviceProfiles**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
deviceProfileService.getDeviceProfiles(pageLink).subscribe(deviceProfiles => {
  console.log('Get Device Profiles:', deviceProfiles);
});
```

**2. getDeviceProfile**

```javascript
deviceProfileService.getDeviceProfile('your-deviceprofile-id').subscribe(deviceProfile => {
  console.log('Get Device Profile:', deviceProfile);
});
```

**3. exportDeviceProfile**

```javascript
deviceProfileService.exportDeviceProfile('your-deviceprofile-id').subscribe(deviceProfile => {
  console.log('Export Device Profile:', deviceProfile);
});
```

**4. getLwm2mObjects**

```javascript
deviceProfileService.getLwm2mObjects('your-sortorder-value', 'your-objectids-value', 'your-searchtext-value').subscribe(lwm2mObjects => {
  console.log('Get Lwm 2 m Objects:', lwm2mObjects);
});
```

**5. getLwm2mBootstrapSecurityInfo**

```javascript
deviceProfileService.getLwm2mBootstrapSecurityInfo(true).subscribe(lwm2mBootstrapSecurityInfo => {
  console.log('Get Lwm 2 m Bootstrap Security Info:', lwm2mBootstrapSecurityInfo);
});
```

**6. getLwm2mBootstrapSecurityInfoBySecurityType**

```javascript
deviceProfileService.getLwm2mBootstrapSecurityInfoBySecurityType(true).subscribe(lwm2mBootstrapSecurityInfoBySecurityType => {
  console.log('Get Lwm 2 m Bootstrap Security Info By Security Type:', lwm2mBootstrapSecurityInfoBySecurityType);
});
```

**7. getLwm2mObjectsPage**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
deviceProfileService.getLwm2mObjectsPage(pageLink).subscribe(lwm2mObjectsPage => {
  console.log('Get Lwm 2 m Objects Page:', lwm2mObjectsPage);
});
```

**8. saveDeviceProfileAndConfirmOtaChange**

```javascript
deviceProfileService.saveDeviceProfileAndConfirmOtaChange('your-origindeviceprofile-value', 'your-deviceprofile-value').subscribe(deviceProfileAndConfirmOtaChange => {
  console.log('Save Device Profile And Confirm Ota Change:', deviceProfileAndConfirmOtaChange);
});
```

**9. saveDeviceProfile**

```javascript
deviceProfileService.saveDeviceProfile().subscribe(deviceProfile => {
  console.log('Save Device Profile:', deviceProfile);
});
```

**10. setDefaultDeviceProfile**

```javascript
deviceProfileService.setDefaultDeviceProfile('your-deviceprofile-id').subscribe(defaultDeviceProfile => {
  console.log('Set Default Device Profile:', defaultDeviceProfile);
});
```

**11. getDefaultDeviceProfileInfo**

```javascript
deviceProfileService.getDefaultDeviceProfileInfo().subscribe(defaultDeviceProfileInfo => {
  console.log('Get Default Device Profile Info:', defaultDeviceProfileInfo);
});
```

**12. getDeviceProfileInfo**

```javascript
deviceProfileService.getDeviceProfileInfo('your-deviceprofile-id').subscribe(info => {
  console.log('Get Device Profile Info:', info);
});
```

**13. getDeviceProfileInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
deviceProfileService.getDeviceProfileInfos(pageLink, 'your-transporttype-value').subscribe(deviceProfileInfos => {
  console.log('Get Device Profile Infos:', deviceProfileInfos);
});
```

**14. getDeviceProfilesByIds**

```javascript
deviceProfileService.getDeviceProfilesByIds('your-deviceprofileids-value').subscribe(deviceProfilesByIds => {
  console.log('Get Device Profiles By Ids:', deviceProfilesByIds);
});
```

**15. getDeviceProfileDevicesAttributesKeys**

```javascript
deviceProfileService.getDeviceProfileDevicesAttributesKeys('your-deviceprofile-id').subscribe(deviceProfileDevicesAttributesKeys => {
  console.log('Get Device Profile Devices Attributes Keys:', deviceProfileDevicesAttributesKeys);
});
```

**16. getDeviceProfileDevicesTimeseriesKeys**

```javascript
deviceProfileService.getDeviceProfileDevicesTimeseriesKeys('your-deviceprofile-id').subscribe(deviceProfileDevicesTimeseriesKeys => {
  console.log('Get Device Profile Devices Timeseries Keys:', deviceProfileDevicesTimeseriesKeys);
});
```

**17. getDeviceProfileNames**

```javascript
deviceProfileService.getDeviceProfileNames('your-activeonly-value').subscribe(deviceProfileNames => {
  console.log('Get Device Profile Names:', deviceProfileNames);
});
```

---

### **DEVICE SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const deviceService = $injector.get(self.ctx.servicesMap.get('deviceService'));

// Alternative: Direct context access
const deviceService = self.ctx.deviceService;
```

**1. getDeviceInfosByQuery**

```javascript
self.ctx.deviceService.getDeviceInfosByQuery('your-deviceinfoquery-value').subscribe(deviceInfosByQuery => {
  console.log('Get Device Infos By Query:', deviceInfosByQuery);
});
```

**2. getTenantDevices**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.deviceService.getTenantDevices(pageLink, 'your-type-value').subscribe(tenantDevices => {
  console.log('Get Tenant Devices:', tenantDevices);
});
```

**3. getCustomerDevices**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.deviceService.getCustomerDevices('your-customer-id', pageLink, 'your-type-value').subscribe(customerDevices => {
  console.log('Get Customer Devices:', customerDevices);
});
```

**4. getDevice**

```javascript
self.ctx.deviceService.getDevice('your-device-id').subscribe(device => {
  console.log('Get Device:', device);
});
```

**5. getDevices**

```javascript
self.ctx.deviceService.getDevices('your-deviceids-value').subscribe(devices => {
  console.log('Get Devices:', devices);
});
```

**6. getUserDevices**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.deviceService.getUserDevices(pageLink, 'your-type-value').subscribe(userDevices => {
  console.log('Get User Devices:', userDevices);
});
```

**7. getAllDeviceInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.deviceService.getAllDeviceInfos(true, pageLink, 'your-deviceprofile-id').subscribe(allDeviceInfos => {
  console.log('Get All Device Infos:', allDeviceInfos);
});
```

**8. getCustomerDeviceInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.deviceService.getCustomerDeviceInfos(true, 'your-customer-id', pageLink, 'your-deviceprofile-id').subscribe(customerDeviceInfos => {
  console.log('Get Customer Device Infos:', customerDeviceInfos);
});
```

**9. getDeviceInfo**

```javascript
self.ctx.deviceService.getDeviceInfo('your-device-id').subscribe(deviceInfo => {
  console.log('Get Device Info:', deviceInfo);
});
```

**10. saveDevice**

```javascript
self.ctx.deviceService.saveDevice('your-device-value', 'your-entitygroupids-value').subscribe(device => {
  console.log('Save Device:', device);
});
```

**11. saveDeviceWithCredentials**

```javascript
self.ctx.deviceService.saveDeviceWithCredentials('your-device-value', 'your-credentials-value', 'your-entitygroupids-value').subscribe(deviceWithCredentials => {
  console.log('Save Device With Credentials:', deviceWithCredentials);
});
```

**12. getDeviceTypes**

```javascript
self.ctx.deviceService.getDeviceTypes().subscribe(deviceTypes => {
  console.log('Get Device Types:', deviceTypes);
});
```

**13. getDeviceCredentials**

```javascript
self.ctx.deviceService.getDeviceCredentials('your-device-id', true).subscribe(deviceCredentials => {
  console.log('Get Device Credentials:', deviceCredentials);
});
```

---

### **DOMAIN SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const domainService = $injector.get(self.ctx.servicesMap.get('domainService'));
```

**1. saveDomain**

```javascript
domainService.saveDomain('your-domain-value', 'your-oauth2clientids-value').subscribe(domain => {
  console.log('Save Domain:', domain);
});
```

**2. updateOauth2Clients**

```javascript
domainService.updateOauth2Clients('your--id', 'your-oauth2clientids-value').subscribe(result => {
  console.log('Update Oauth 2 Clients:', result);
});
```

**3. getDomainInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
domainService.getDomainInfos(pageLink).subscribe(domainInfos => {
  console.log('Get Domain Infos:', domainInfos);
});
```

**4. getDomainInfoById**

```javascript
domainService.getDomainInfoById('your--id').subscribe(domainInfoById => {
  console.log('Get Domain Info By Id:', domainInfoById);
});
```

**5. deleteDomain**

```javascript
domainService.deleteDomain('your--id').subscribe(result => {
  console.log('Delete Domain:', result);
});
```

---

### **EDGE SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const edgeService = $injector.get(self.ctx.servicesMap.get('edgeService'));
```

**1. getEdges**

```javascript
edgeService.getEdges('your-edgeids-value').subscribe(edges => {
  console.log('Get Edges:', edges);
});
```

**2. getEdge**

```javascript
edgeService.getEdge('your-edge-id').subscribe(edge => {
  console.log('Get Edge:', edge);
});
```

**3. getEdgeInfo**

```javascript
edgeService.getEdgeInfo('your-edge-id').subscribe(info => {
  console.log('Get Edge Info:', info);
});
```

**4. saveEdge**

```javascript
edgeService.saveEdge('your-edge-value', 'your-entitygroupids-value').subscribe(edge => {
  console.log('Save Edge:', edge);
});
```

**5. getEdgeTypes**

```javascript
edgeService.getEdgeTypes().subscribe(edgeTypes => {
  console.log('Get Edge Types:', edgeTypes);
});
```

**6. assignEdgeToCustomer**

```javascript
edgeService.assignEdgeToCustomer('your-customer-id', 'your-edge-id').subscribe(edgeToCustomer => {
  console.log('Assign Edge To Customer:', edgeToCustomer);
});
```

**7. makeEdgePublic**

```javascript
edgeService.makeEdgePublic('your-edge-id').subscribe(makeEdgePublic => {
  console.log('Make Edge Public:', makeEdgePublic);
});
```

**8. getTenantEdges**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
edgeService.getTenantEdges(pageLink, 'your-type-value').subscribe(tenantEdges => {
  console.log('Get Tenant Edges:', tenantEdges);
});
```

**9. getTenantEdgeInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
edgeService.getTenantEdgeInfos(pageLink, 'your-type-value').subscribe(tenantEdgeInfos => {
  console.log('Get Tenant Edge Infos:', tenantEdgeInfos);
});
```

**10. getUserEdges**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
edgeService.getUserEdges(pageLink, 'your-type-value').subscribe(userEdges => {
  console.log('Get User Edges:', userEdges);
});
```

**11. getAllEdgeInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
edgeService.getAllEdgeInfos(true, pageLink, 'your-type-value').subscribe(allEdgeInfos => {
  console.log('Get All Edge Infos:', allEdgeInfos);
});
```

**12. getCustomerEdgeInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
edgeService.getCustomerEdgeInfos(true, 'your-customer-id', pageLink, 'your-type-value').subscribe(customerEdgeInfos => {
  console.log('Get Customer Edge Infos:', customerEdgeInfos);
});
```

**13. findByQuery**

```javascript
edgeService.findByQuery('your-query-value').subscribe(byQuery => {
  console.log('Find By Query:', byQuery);
});
```

**14. getEdgeEvents**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
edgeService.getEdgeEvents('your-entity-id', pageLink).subscribe(edgeEvents => {
  console.log('Get Edge Events:', edgeEvents);
});
```

**15. findMissingToRelatedRuleChains**

```javascript
edgeService.findMissingToRelatedRuleChains('your-edge-id').subscribe(missingToRelatedRuleChains => {
  console.log('Find Missing To Related Rule Chains:', missingToRelatedRuleChains);
});
```

**16. findByName**

```javascript
edgeService.findByName('your-edgename-value').subscribe(byName => {
  console.log('Find By Name:', byName);
});
```

**17. bulkImportEdges**

```javascript
edgeService.bulkImportEdges('your-entitiesdata-value').subscribe(bulkImportEdges => {
  console.log('Bulk Import Edges:', bulkImportEdges);
});
```

**18. getEdgeInstallInstructions**

```javascript
edgeService.getEdgeInstallInstructions('your-edge-id', 'your-method-value').subscribe(edgeInstallInstructions => {
  console.log('Get Edge Install Instructions:', edgeInstallInstructions);
});
```

**19. getEdgeUpgradeInstructions**

```javascript
edgeService.getEdgeUpgradeInstructions('your-edgeversion-value', 'your-method-value').subscribe(edgeUpgradeInstructions => {
  console.log('Get Edge Upgrade Instructions:', edgeUpgradeInstructions);
});
```

**20. findAllRelatedEdgesMissingAttributes**

```javascript
edgeService.findAllRelatedEdgesMissingAttributes('your-integration-id').subscribe(allRelatedEdgesMissingAttributes => {
  console.log('Find All Related Edges Missing Attributes:', allRelatedEdgesMissingAttributes);
});
```

**21. findEdgeMissingAttributes**

```javascript
edgeService.findEdgeMissingAttributes('your-integrationids-value', 'your-edge-id').subscribe(edgeMissingAttributes => {
  console.log('Find Edge Missing Attributes:', edgeMissingAttributes);
});
```

**22. isEdgeUpgradeAvailable**

```javascript
edgeService.isEdgeUpgradeAvailable('your-edge-id').subscribe(isEdgeUpgradeAvailable => {
  console.log('Is Edge Upgrade Available:', isEdgeUpgradeAvailable);
});
```

---

### **ENTITIES VERSION CONTROL SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const entitiesVersionControlService = $injector.get(self.ctx.servicesMap.get('entitiesVersionControlService'));
```

**1. clearBranchList**

```javascript
entitiesVersionControlService.clearBranchList().subscribe(branchList => {
  console.log('Clear Branch List:', branchList);
});
```

**2. listBranches**

```javascript
entitiesVersionControlService.listBranches().subscribe(branches => {
  console.log('List Branches:', branches);
});
```

**3. getEntityDataInfo**

```javascript
entitiesVersionControlService.getEntityDataInfo('your-externalentity-id', 'your-internalentity-id', 'your-version-id').subscribe(entityDataInfo => {
  console.log('Get Entity Data Info:', entityDataInfo);
});
```

**4. saveEntitiesVersion**

```javascript
entitiesVersionControlService.saveEntitiesVersion('your-request-value').subscribe(entitiesVersion => {
  console.log('Save Entities Version:', entitiesVersion);
});
```

**5. getVersionCreateRequestStatus**

```javascript
entitiesVersionControlService.getVersionCreateRequestStatus('your-request-id').subscribe(versionCreateRequestStatus => {
  console.log('Get Version Create Request Status:', versionCreateRequestStatus);
});
```

**6. listEntityVersions**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
entitiesVersionControlService.listEntityVersions(pageLink, 'your-branch-value', 'your-externalentity-id', 'your-internalentity-id').subscribe(entityVersions => {
  console.log('List Entity Versions:', entityVersions);
});
```

**7. listEntityTypeVersions**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
entitiesVersionControlService.listEntityTypeVersions(pageLink, 'your-branch-value', 'your-entitytype-value').subscribe(entityTypeVersions => {
  console.log('List Entity Type Versions:', entityTypeVersions);
});
```

**8. listVersions**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
entitiesVersionControlService.listVersions(pageLink, 'your-branch-value').subscribe(versions => {
  console.log('List Versions:', versions);
});
```

**9. loadEntitiesVersion**

```javascript
entitiesVersionControlService.loadEntitiesVersion('your-request-value').subscribe(loadEntitiesVersion => {
  console.log('Load Entities Version:', loadEntitiesVersion);
});
```

**10. getVersionLoadRequestStatus**

```javascript
entitiesVersionControlService.getVersionLoadRequestStatus('your-request-id').subscribe(versionLoadRequestStatus => {
  console.log('Get Version Load Request Status:', versionLoadRequestStatus);
});
```

**11. compareEntityDataToVersion**

```javascript
entitiesVersionControlService.compareEntityDataToVersion('your-entity-id', 'your-version-id').subscribe(compareEntityDataToVersion => {
  console.log('Compare Entity Data To Version:', compareEntityDataToVersion);
});
```

**12. entityLoadErrorToMessage**

```javascript
entitiesVersionControlService.entityLoadErrorToMessage('your-entityloaderror-value').subscribe(entityLoadErrorToMessage => {
  console.log('Entity Load Error To Message:', entityLoadErrorToMessage);
});
```

---

### **ENTITY GROUP SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const entityGroupService = $injector.get(self.ctx.servicesMap.get('entityGroupService'));

// Alternative: Direct context access
const entityGroupService = self.ctx.entityGroupService;
```

**1. getOwners**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.entityGroupService.getOwners(pageLink).subscribe(owners => {
  console.log('Get Owners:', owners);
});
```

**2. getOwnerInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.entityGroupService.getOwnerInfos(pageLink).subscribe(ownerInfos => {
  console.log('Get Owner Infos:', ownerInfos);
});
```

**3. getOwnerInfo**

```javascript
self.ctx.entityGroupService.getOwnerInfo('your-owner-id').subscribe(ownerInfo => {
  console.log('Get Owner Info:', ownerInfo);
});
```

**4. getEntityGroup**

```javascript
self.ctx.entityGroupService.getEntityGroup('your-entitygroup-id').subscribe(entityGroup => {
  console.log('Get Entity Group:', entityGroup);
});
```

**5. getDeviceEntityGroup**

```javascript
self.ctx.entityGroupService.getDeviceEntityGroup('your-entitygroup-id').subscribe(deviceEntityGroup => {
  console.log('Get Device Entity Group:', deviceEntityGroup);
});
```

**6. fetchOtaPackageGroupInfo**

```javascript
self.ctx.entityGroupService.fetchOtaPackageGroupInfo('your-group-value').subscribe(fetchOtaPackageGroupInfo => {
  console.log('Fetch Ota Package Group Info:', fetchOtaPackageGroupInfo);
});
```

**7. updateDeviceGroupOtaPackage**

```javascript
self.ctx.entityGroupService.updateDeviceGroupOtaPackage('your-devicegroupotapackage-value', 'your-otapackage-id', 'your-group-id', 'your-otapackagetype-value').subscribe(deviceGroupOtaPackage => {
  console.log('Update Device Group Ota Package:', deviceGroupOtaPackage);
});
```

**8. saveDeviceGroupOtaPackage**

```javascript
self.ctx.entityGroupService.saveDeviceGroupOtaPackage('your-devicegroupotapackage-value').subscribe(deviceGroupOtaPackage => {
  console.log('Save Device Group Ota Package:', deviceGroupOtaPackage);
});
```

**9. saveDeviceEntityGroup**

```javascript
self.ctx.entityGroupService.saveDeviceEntityGroup('your-entitygroup-value', 'your-originalentitygroup-value').subscribe(deviceEntityGroup => {
  console.log('Save Device Entity Group:', deviceEntityGroup);
});
```

**10. getEntityGroupEntityInfo**

```javascript
self.ctx.entityGroupService.getEntityGroupEntityInfo('your-entitygroup-id').subscribe(entityGroupEntityInfo => {
  console.log('Get Entity Group Entity Info:', entityGroupEntityInfo);
});
```

**11. saveEntityGroup**

```javascript
self.ctx.entityGroupService.saveEntityGroup('your-entitygroup-value').subscribe(entityGroup => {
  console.log('Save Entity Group:', entityGroup);
});
```

**12. makeEntityGroupPublic**

```javascript
self.ctx.entityGroupService.makeEntityGroupPublic('your-entitygroup-id').subscribe(makeEntityGroupPublic => {
  console.log('Make Entity Group Public:', makeEntityGroupPublic);
});
```

**13. makeEntityGroupPrivate**

```javascript
self.ctx.entityGroupService.makeEntityGroupPrivate('your-entitygroup-id').subscribe(makeEntityGroupPrivate => {
  console.log('Make Entity Group Private:', makeEntityGroupPrivate);
});
```

**14. shareEntityGroup**

```javascript
self.ctx.entityGroupService.shareEntityGroup('your-entitygroup-id', 'your-sharegrouprequest-value').subscribe(shareEntityGroup => {
  console.log('Share Entity Group:', shareEntityGroup);
});
```

**15. shareEntityGroupV2**

```javascript
self.ctx.entityGroupService.shareEntityGroupV2('your-entitygroup-id', 'your-sharegrouprequest-value').subscribe(shareEntityGroupV2 => {
  console.log('Share Entity Group V 2:', shareEntityGroupV2);
});
```

**16. getEntityGroups**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.entityGroupService.getEntityGroups(pageLink, 'your-grouptype-value').subscribe(entityGroups => {
  console.log('Get Entity Groups:', entityGroups);
});
```

**17. getEntityGroupEntityInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.entityGroupService.getEntityGroupEntityInfos(pageLink, 'your-grouptype-value').subscribe(entityGroupEntityInfos => {
  console.log('Get Entity Group Entity Infos:', entityGroupEntityInfos);
});
```

**18. getAllEntityGroups**

```javascript
self.ctx.entityGroupService.getAllEntityGroups(0, 'your-grouptype-value').subscribe(allEntityGroups => {
  console.log('Get All Entity Groups:', allEntityGroups);
});
```

**19. getAllEntityGroupsByPageLink**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.entityGroupService.getAllEntityGroupsByPageLink(pageLink, 'your-grouptype-value').subscribe(allEntityGroupsByPageLink => {
  console.log('Get All Entity Groups By Page Link:', allEntityGroupsByPageLink);
});
```

**20. getSharedEntityGroups**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.entityGroupService.getSharedEntityGroups(pageLink, 'your-grouptype-value').subscribe(sharedEntityGroups => {
  console.log('Get Shared Entity Groups:', sharedEntityGroups);
});
```

**21. getSharedEntityGroupEntityInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.entityGroupService.getSharedEntityGroupEntityInfos(pageLink, 'your-grouptype-value').subscribe(sharedEntityGroupEntityInfos => {
  console.log('Get Shared Entity Group Entity Infos:', sharedEntityGroupEntityInfos);
});
```

**22. getEntityGroupIdsForEntityId**

```javascript
self.ctx.entityGroupService.getEntityGroupIdsForEntityId('your-entitytype-value', 'your-entity-id').subscribe(entityGroupIdsForEntityId => {
  console.log('Get Entity Group Ids For Entity Id:', entityGroupIdsForEntityId);
});
```

**23. getEntityGroupsByIds**

```javascript
self.ctx.entityGroupService.getEntityGroupsByIds('your-entitygroupids-value').subscribe(entityGroupsByIds => {
  console.log('Get Entity Groups By Ids:', entityGroupsByIds);
});
```

**24. getEntityGroupEntityInfosByIds**

```javascript
self.ctx.entityGroupService.getEntityGroupEntityInfosByIds('your-entitygroupids-value').subscribe(entityGroupEntityInfosByIds => {
  console.log('Get Entity Group Entity Infos By Ids:', entityGroupEntityInfosByIds);
});
```

**25. getEntityGroupsHierarchyByOwnerId**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.entityGroupService.getEntityGroupsHierarchyByOwnerId(pageLink, 'your-ownertype-value', 'your-owner-id', 'your-grouptype-value').subscribe(entityGroupsHierarchyByOwnerId => {
  console.log('Get Entity Groups Hierarchy By Owner Id:', entityGroupsHierarchyByOwnerId);
});
```

**26. getEntityGroupEntityInfosHierarchyByOwnerId**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.entityGroupService.getEntityGroupEntityInfosHierarchyByOwnerId(pageLink, 'your-ownertype-value', 'your-owner-id', 'your-grouptype-value').subscribe(entityGroupEntityInfosHierarchyByOwnerId => {
  console.log('Get Entity Group Entity Infos Hierarchy By Owner Id:', entityGroupEntityInfosHierarchyByOwnerId);
});
```

**27. getEntityGroupsByOwnerIdAndPageLink**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.entityGroupService.getEntityGroupsByOwnerIdAndPageLink('your-ownertype-value', 'your-owner-id', 'your-grouptype-value', pageLink).subscribe(entityGroupsByOwnerIdAndPageLink => {
  console.log('Get Entity Groups By Owner Id And Page Link:', entityGroupsByOwnerIdAndPageLink);
});
```

**28. getEntityGroupsByOwnerId**

```javascript
self.ctx.entityGroupService.getEntityGroupsByOwnerId('your-ownertype-value', 'your-owner-id', 'your-grouptype-value').subscribe(entityGroupsByOwnerId => {
  console.log('Get Entity Groups By Owner Id:', entityGroupsByOwnerId);
});
```

**29. getEntityGroupEntityInfosByOwnerId**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.entityGroupService.getEntityGroupEntityInfosByOwnerId(pageLink, 'your-ownertype-value', 'your-owner-id', 'your-grouptype-value').subscribe(entityGroupEntityInfosByOwnerId => {
  console.log('Get Entity Group Entity Infos By Owner Id:', entityGroupEntityInfosByOwnerId);
});
```

**30. getAllEntityGroupsByOwnerId**

```javascript
self.ctx.entityGroupService.getAllEntityGroupsByOwnerId(0, 'your-ownertype-value', 'your-owner-id', 'your-grouptype-value').subscribe(allEntityGroupsByOwnerId => {
  console.log('Get All Entity Groups By Owner Id:', allEntityGroupsByOwnerId);
});
```

**31. getAllEntityGroupsByOwnerIdAndPageLink**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.entityGroupService.getAllEntityGroupsByOwnerIdAndPageLink(pageLink, 'your-ownertype-value', 'your-owner-id', 'your-grouptype-value').subscribe(allEntityGroupsByOwnerIdAndPageLink => {
  console.log('Get All Entity Groups By Owner Id And Page Link:', allEntityGroupsByOwnerIdAndPageLink);
});
```

**32. getEntityGroupsByPageLink**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.entityGroupService.getEntityGroupsByPageLink(pageLink, 'your-grouptype-value').subscribe(entityGroupsByPageLink => {
  console.log('Get Entity Groups By Page Link:', entityGroupsByPageLink);
});
```

**33. getEntityGroupAllByOwnerId**

```javascript
self.ctx.entityGroupService.getEntityGroupAllByOwnerId('your-ownertype-value', 'your-owner-id', 'your-grouptype-value').subscribe(entityGroupAllByOwnerId => {
  console.log('Get Entity Group All By Owner Id:', entityGroupAllByOwnerId);
});
```

**34. addEntityToEntityGroup**

```javascript
self.ctx.entityGroupService.addEntityToEntityGroup('your-entitygroup-id', 'your-entity-id').subscribe(addEntityToEntityGroup => {
  console.log('Add Entity To Entity Group:', addEntityToEntityGroup);
});
```

**35. addEntitiesToEntityGroup**

```javascript
self.ctx.entityGroupService.addEntitiesToEntityGroup('your-entitygroup-id', 'your-entityids-value').subscribe(addEntitiesToEntityGroup => {
  console.log('Add Entities To Entity Group:', addEntitiesToEntityGroup);
});
```

**36. changeEntityOwner**

```javascript
self.ctx.entityGroupService.changeEntityOwner('your-owner-id', 'your-entity-id', 'your-entitygroupids-value').subscribe(changeEntityOwner => {
  console.log('Change Entity Owner:', changeEntityOwner);
});
```

**37. removeEntityFromEntityGroup**

```javascript
self.ctx.entityGroupService.removeEntityFromEntityGroup('your-entitygroup-id', 'your-entity-id').subscribe(entityFromEntityGroup => {
  console.log('Remove Entity From Entity Group:', entityFromEntityGroup);
});
```

**38. removeEntitiesFromEntityGroup**

```javascript
self.ctx.entityGroupService.removeEntitiesFromEntityGroup('your-entitygroup-id', 'your-entityids-value').subscribe(entitiesFromEntityGroup => {
  console.log('Remove Entities From Entity Group:', entitiesFromEntityGroup);
});
```

**39. getEntityGroupEntity**

```javascript
self.ctx.entityGroupService.getEntityGroupEntity('your-entitygroup-id', 'your-entity-id').subscribe(entityGroupEntity => {
  console.log('Get Entity Group Entity:', entityGroupEntity);
});
```

**40. getEdgeEntityGroups**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.entityGroupService.getEdgeEntityGroups(pageLink, 'your-edge-id', 'your-grouptype-value').subscribe(edgeEntityGroups => {
  console.log('Get Edge Entity Groups:', edgeEntityGroups);
});
```

**41. getAllEdgeEntityGroups**

```javascript
self.ctx.entityGroupService.getAllEdgeEntityGroups(0, 'your-edge-id', 'your-grouptype-value').subscribe(allEdgeEntityGroups => {
  console.log('Get All Edge Entity Groups:', allEdgeEntityGroups);
});
```

**42. getAllEdgeEntityGroupsByPageLink**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.entityGroupService.getAllEdgeEntityGroupsByPageLink(pageLink, 'your-edge-id', 'your-grouptype-value').subscribe(allEdgeEntityGroupsByPageLink => {
  console.log('Get All Edge Entity Groups By Page Link:', allEdgeEntityGroupsByPageLink);
});
```

**43. assignEntityGroupToEdge**

```javascript
self.ctx.entityGroupService.assignEntityGroupToEdge('your-edge-id', 'your-entitygroup-id', 'your-grouptype-value').subscribe(entityGroupToEdge => {
  console.log('Assign Entity Group To Edge:', entityGroupToEdge);
});
```

**44. unassignEntityGroupFromEdge**

```javascript
self.ctx.entityGroupService.unassignEntityGroupFromEdge('your-edge-id', 'your-entitygroup-id', 'your-grouptype-value').subscribe(entityGroupFromEdge => {
  console.log('Unassign Entity Group From Edge:', entityGroupFromEdge);
});
```

---

### **ENTITY RELATION SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const entityRelationService = $injector.get(self.ctx.servicesMap.get('entityRelationService'));

// Alternative: Direct context access
const entityRelationService = self.ctx.entityRelationService;
```

**1. saveRelation**

```javascript
self.ctx.entityRelationService.saveRelation('your-relation-value').subscribe(relation => {
  console.log('Save Relation:', relation);
});
```

**2. getRelation**

```javascript
self.ctx.entityRelationService.getRelation('your-from-id', 'your-relationtype-value', 'your-to-id').subscribe(relation => {
  console.log('Get Relation:', relation);
});
```

**3. findByFrom**

```javascript
self.ctx.entityRelationService.findByFrom('your-from-id').subscribe(byFrom => {
  console.log('Find By From:', byFrom);
});
```

**4. findInfoByFrom**

```javascript
self.ctx.entityRelationService.findInfoByFrom('your-from-id').subscribe(infoByFrom => {
  console.log('Find Info By From:', infoByFrom);
});
```

**5. findByFromAndType**

```javascript
self.ctx.entityRelationService.findByFromAndType('your-from-id', 'your-relationtype-value').subscribe(byFromAndType => {
  console.log('Find By From And Type:', byFromAndType);
});
```

**6. findByTo**

```javascript
self.ctx.entityRelationService.findByTo('your-to-id').subscribe(byTo => {
  console.log('Find By To:', byTo);
});
```

**7. findInfoByTo**

```javascript
self.ctx.entityRelationService.findInfoByTo('your-to-id').subscribe(infoByTo => {
  console.log('Find Info By To:', infoByTo);
});
```

**8. findByToAndType**

```javascript
self.ctx.entityRelationService.findByToAndType('your-to-id', 'your-relationtype-value').subscribe(byToAndType => {
  console.log('Find By To And Type:', byToAndType);
});
```

**9. findByQuery**

```javascript
self.ctx.entityRelationService.findByQuery('your-query-value').subscribe(byQuery => {
  console.log('Find By Query:', byQuery);
});
```

**10. findInfoByQuery**

```javascript
self.ctx.entityRelationService.findInfoByQuery('your-query-value').subscribe(infoByQuery => {
  console.log('Find Info By Query:', infoByQuery);
});
```

---

### **ENTITY SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const entityService = $injector.get(self.ctx.servicesMap.get('entityService'));

// Alternative: Direct context access
const entityService = self.ctx.entityService;
```

**1. getEntityObservable**

```javascript
self.ctx.entityService.getEntityObservable('your-entitytype-value', 'your-entity-id').subscribe(entityObservable => {
  console.log('Get Entity Observable:', entityObservable);
});
```

**2. saveEntityObservable**

```javascript
self.ctx.entityService.saveEntityObservable('your-entity-value').subscribe(entityObservable => {
  console.log('Save Entity Observable:', entityObservable);
});
```

**3. getEntity**

```javascript
self.ctx.entityService.getEntity('your-entitytype-value', 'your-entity-id').subscribe(entity => {
  console.log('Get Entity:', entity);
});
```

**4. saveEntity**

```javascript
self.ctx.entityService.saveEntity('your-entity-value').subscribe(entity => {
  console.log('Save Entity:', entity);
});
```

**5. saveGroupEntityObservable**

```javascript
self.ctx.entityService.saveGroupEntityObservable('your-entity-value', 'your-entitygroupids-value').subscribe(groupEntityObservable => {
  console.log('Save Group Entity Observable:', groupEntityObservable);
});
```

**6. saveGroupEntity**

```javascript
self.ctx.entityService.saveGroupEntity('your-entity-value', 'your-entitygroupids-value').subscribe(groupEntity => {
  console.log('Save Group Entity:', groupEntity);
});
```

**7. getEntitiesObservable**

```javascript
self.ctx.entityService.getEntitiesObservable('your-entitytype-value', 'your-entityids-value').subscribe(entitiesObservable => {
  console.log('Get Entities Observable:', entitiesObservable);
});
```

**8. getEntities**

```javascript
self.ctx.entityService.getEntities('your-entitytype-value', 'your-entityids-value').subscribe(entities => {
  console.log('Get Entities:', entities);
});
```

**9. getSingleTenantByPageLinkObservable**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.entityService.getSingleTenantByPageLinkObservable(pageLink).subscribe(singleTenantByPageLinkObservable => {
  console.log('Get Single Tenant By Page Link Observable:', singleTenantByPageLinkObservable);
});
```

**10. getEntitiesByPageLinkObservable**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.entityService.getEntitiesByPageLinkObservable('your-entitytype-value', pageLink, 'your-subtype-value').subscribe(entitiesByPageLinkObservable => {
  console.log('Get Entities By Page Link Observable:', entitiesByPageLinkObservable);
});
```

**11. getEntitiesByPageLink**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.entityService.getEntitiesByPageLink('your-entitytype-value', pageLink, 'your-subtype-value').subscribe(entitiesByPageLink => {
  console.log('Get Entities By Page Link:', entitiesByPageLink);
});
```

**12. getEntitiesByNameFilter**

```javascript
self.ctx.entityService.getEntitiesByNameFilter('your-entitytype-value', 'your-entitynamefilter-value', 0, 'your-subtype-value').subscribe(entitiesByNameFilter => {
  console.log('Get Entities By Name Filter:', entitiesByNameFilter);
});
```

**13. getEntityGroupEntitiesByPageLink**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.entityService.getEntityGroupEntitiesByPageLink('your-entitygroup-id', pageLink, 'your-entitygrouptype-value').subscribe(entityGroupEntitiesByPageLink => {
  console.log('Get Entity Group Entities By Page Link:', entityGroupEntitiesByPageLink);
});
```

**14. getEntityGroupEntities**

```javascript
self.ctx.entityService.getEntityGroupEntities('your-entitygroup-id', 'your-entitygrouptype-value', 0).subscribe(entityGroupEntities => {
  console.log('Get Entity Group Entities:', entityGroupEntities);
});
```

**15. findEntityDataByQuery**

```javascript
self.ctx.entityService.findEntityDataByQuery('your-query-value').subscribe(entityDataByQuery => {
  console.log('Find Entity Data By Query:', entityDataByQuery);
});
```

**16. findEntityKeysByQuery**

```javascript
self.ctx.entityService.findEntityKeysByQuery('your-query-value', 'your-scope-value').subscribe(entityKeysByQuery => {
  console.log('Find Entity Keys By Query:', entityKeysByQuery);
});
```

**17. findEntityKeysByQueryV2**

```javascript
self.ctx.entityService.findEntityKeysByQueryV2('your-query-value', 'your-scopes-value').subscribe(entityKeysByQueryV2 => {
  console.log('Find Entity Keys By Query V 2:', entityKeysByQueryV2);
});
```

**18. findAlarmDataByQuery**

```javascript
self.ctx.entityService.findAlarmDataByQuery('your-query-value').subscribe(alarmDataByQuery => {
  console.log('Find Alarm Data By Query:', alarmDataByQuery);
});
```

**19. findEntityInfosByFilterAndName**

```javascript
self.ctx.entityService.findEntityInfosByFilterAndName('your-filter-value', 'your-searchtext-value').subscribe(entityInfosByFilterAndName => {
  console.log('Find Entity Infos By Filter And Name:', entityInfosByFilterAndName);
});
```

**20. findSingleEntityInfoByEntityFilter**

```javascript
self.ctx.entityService.findSingleEntityInfoByEntityFilter('your-filter-value').subscribe(singleEntityInfoByEntityFilter => {
  console.log('Find Single Entity Info By Entity Filter:', singleEntityInfoByEntityFilter);
});
```

**21. getAliasFilterTypesByEntityTypes**

```javascript
self.ctx.entityService.getAliasFilterTypesByEntityTypes('your-entitytypes-value').subscribe(aliasFilterTypesByEntityTypes => {
  console.log('Get Alias Filter Types By Entity Types:', aliasFilterTypesByEntityTypes);
});
```

**22. filterAliasByEntityTypes**

```javascript
self.ctx.entityService.filterAliasByEntityTypes('your-entityalias-value', 'your-entitytypes-value').subscribe(filterAliasByEntityTypes => {
  console.log('Filter Alias By Entity Types:', filterAliasByEntityTypes);
});
```

**23. filterAliasFilterTypeByEntityTypes**

```javascript
self.ctx.entityService.filterAliasFilterTypeByEntityTypes('your-aliasfiltertype-value', 'your-entitytypes-value').subscribe(filterAliasFilterTypeByEntityTypes => {
  console.log('Filter Alias Filter Type By Entity Types:', filterAliasFilterTypeByEntityTypes);
});
```

**24. filterAliasFilterTypeByEntityType**

```javascript
self.ctx.entityService.filterAliasFilterTypeByEntityType('your-aliasfiltertype-value', 'your-entitytype-value').subscribe(filterAliasFilterTypeByEntityType => {
  console.log('Filter Alias Filter Type By Entity Type:', filterAliasFilterTypeByEntityType);
});
```

**25. prepareAllowedEntityTypesList**

```javascript
self.ctx.entityService.prepareAllowedEntityTypesList('your-allowedentitytypes-value', true, 'your-operation-value').subscribe(prepareAllowedEntityTypesList => {
  console.log('Prepare Allowed Entity Types List:', prepareAllowedEntityTypesList);
});
```

**26. getEntityFieldKeys**

```javascript
self.ctx.entityService.getEntityFieldKeys('your-entitytype-value', 'your-searchtext-value').subscribe(entityFieldKeys => {
  console.log('Get Entity Field Keys:', entityFieldKeys);
});
```

**27. getAlarmKeys**

```javascript
self.ctx.entityService.getAlarmKeys('your-searchtext-value').subscribe(alarmKeys => {
  console.log('Get Alarm Keys:', alarmKeys);
});
```

**28. getEntityKeys**

```javascript
self.ctx.entityService.getEntityKeys('your-entity-id', 'your-query-value', 'your-type-value').subscribe(entityKeys => {
  console.log('Get Entity Keys:', entityKeys);
});
```

**29. getEntityKeysByEntityFilter**

```javascript
self.ctx.entityService.getEntityKeysByEntityFilter('your-filter-value', 'your-types-value', 'your-entitytypes-value').subscribe(entityKeysByEntityFilter => {
  console.log('Get Entity Keys By Entity Filter:', entityKeysByEntityFilter);
});
```

**30. getEntityKeysByEntityFilterAndScope**

```javascript
self.ctx.entityService.getEntityKeysByEntityFilterAndScope('your-filter-value', 'your-types-value', 'your-entitytypes-value', 'your-scope-value').subscribe(entityKeysByEntityFilterAndScope => {
  console.log('Get Entity Keys By Entity Filter And Scope:', entityKeysByEntityFilterAndScope);
});
```

**31. createDatasourcesFromSubscriptionsInfo**

```javascript
self.ctx.entityService.createDatasourcesFromSubscriptionsInfo('your-subscriptionsinfo-value').subscribe(datasourcesFromSubscriptionsInfo => {
  console.log('Create Datasources From Subscriptions Info:', datasourcesFromSubscriptionsInfo);
});
```

**32. createAlarmSourceFromSubscriptionInfo**

```javascript
self.ctx.entityService.createAlarmSourceFromSubscriptionInfo('your-subscriptioninfo-value').subscribe(alarmSourceFromSubscriptionInfo => {
  console.log('Create Alarm Source From Subscription Info:', alarmSourceFromSubscriptionInfo);
});
```

**33. getAssignedToEdgeEntitiesByType**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.entityService.getAssignedToEdgeEntitiesByType('your-edge-id', 'your-entitytype-value', pageLink).subscribe(assignedToEdgeEntitiesByType => {
  console.log('Get Assigned To Edge Entities By Type:', assignedToEdgeEntitiesByType);
});
```

**34. getEdgeEventContent**

```javascript
self.ctx.entityService.getEdgeEventContent('your-entity-value').subscribe(edgeEventContent => {
  console.log('Get Edge Event Content:', edgeEventContent);
});
```

**35. getEntitySubtypesObservable**

```javascript
self.ctx.entityService.getEntitySubtypesObservable('your-entitytype-value').subscribe(entitySubtypesObservable => {
  console.log('Get Entity Subtypes Observable:', entitySubtypesObservable);
});
```

---

### **ENTITY VIEW SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const entityViewService = $injector.get(self.ctx.servicesMap.get('entityViewService'));

// Alternative: Direct context access
const entityViewService = self.ctx.entityViewService;
```

**1. getTenantEntityViews**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.entityViewService.getTenantEntityViews(pageLink, 'your-type-value').subscribe(tenantEntityViews => {
  console.log('Get Tenant Entity Views:', tenantEntityViews);
});
```

**2. getCustomerEntityViews**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.entityViewService.getCustomerEntityViews('your-customer-id', pageLink, 'your-type-value').subscribe(customerEntityViews => {
  console.log('Get Customer Entity Views:', customerEntityViews);
});
```

**3. getEntityView**

```javascript
self.ctx.entityViewService.getEntityView('your-entityview-id').subscribe(entityView => {
  console.log('Get Entity View:', entityView);
});
```

**4. getEntityViews**

```javascript
self.ctx.entityViewService.getEntityViews('your-entityviewids-value').subscribe(entityViews => {
  console.log('Get Entity Views:', entityViews);
});
```

**5. getUserEntityViews**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.entityViewService.getUserEntityViews(pageLink, 'your-type-value').subscribe(userEntityViews => {
  console.log('Get User Entity Views:', userEntityViews);
});
```

**6. getAllEntityViewInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.entityViewService.getAllEntityViewInfos(true, pageLink, 'your-type-value').subscribe(allEntityViewInfos => {
  console.log('Get All Entity View Infos:', allEntityViewInfos);
});
```

**7. getCustomerEntityViewInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.entityViewService.getCustomerEntityViewInfos(true, 'your-customer-id', pageLink, 'your-type-value').subscribe(customerEntityViewInfos => {
  console.log('Get Customer Entity View Infos:', customerEntityViewInfos);
});
```

**8. getEntityViewInfo**

```javascript
self.ctx.entityViewService.getEntityViewInfo('your-entityview-id').subscribe(entityViewInfo => {
  console.log('Get Entity View Info:', entityViewInfo);
});
```

**9. saveEntityView**

```javascript
self.ctx.entityViewService.saveEntityView('your-entityview-value', 'your-entitygroupids-value').subscribe(entityView => {
  console.log('Save Entity View:', entityView);
});
```

**10. getEntityViewTypes**

```javascript
self.ctx.entityViewService.getEntityViewTypes().subscribe(entityViewTypes => {
  console.log('Get Entity View Types:', entityViewTypes);
});
```

**11. findByQuery**

```javascript
self.ctx.entityViewService.findByQuery('your-query-value').subscribe(byQuery => {
  console.log('Find By Query:', byQuery);
});
```

---

### **EVENT SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const eventService = $injector.get(self.ctx.servicesMap.get('eventService'));
```

**1. getEvents**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
eventService.getEvents('your-entity-id', 'your-eventtype-value', 'your-tenant-id', pageLink).subscribe(events => {
  console.log('Get Events:', events);
});
```

**2. getFilterEvents**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
eventService.getFilterEvents('your-entity-id', 'your-eventtype-value', 'your-tenant-id', 'your-filters-value', pageLink).subscribe(filterEvents => {
  console.log('Get Filter Events:', filterEvents);
});
```

---

### **GIT HUB SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const gitHubService = $injector.get(self.ctx.servicesMap.get('gitHubService'));
```

**1. getGitHubStar**

```javascript
gitHubService.getGitHubStar().subscribe(gitHubStar => {
  console.log('Get Git Hub Star:', gitHubStar);
});
```

---

### **IMAGE SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const imageService = $injector.get(self.ctx.servicesMap.get('imageService'));
```

**1. uploadImage**

```javascript
imageService.uploadImage('your-file-value', 'your-title-value', 'your-imagesubtype-value').subscribe(uploadImage => {
  console.log('Upload Image:', uploadImage);
});
```

**2. updateImage**

```javascript
imageService.updateImage('your-type-value', 'your-key-value', 'your-file-value').subscribe(image => {
  console.log('Update Image:', image);
});
```

**3. updateImageInfo**

```javascript
imageService.updateImageInfo('your-imageinfo-value').subscribe(imageInfo => {
  console.log('Update Image Info:', imageInfo);
});
```

**4. updateImagePublicStatus**

```javascript
imageService.updateImagePublicStatus('your-imageinfo-value', true).subscribe(imagePublicStatus => {
  console.log('Update Image Public Status:', imagePublicStatus);
});
```

**5. getImages**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
imageService.getImages(pageLink, 'your-imagesubtype-value').subscribe(images => {
  console.log('Get Images:', images);
});
```

**6. getImageInfo**

```javascript
imageService.getImageInfo('your-type-value', 'your-key-value').subscribe(imageInfo => {
  console.log('Get Image Info:', imageInfo);
});
```

**7. getImageDataUrl**

```javascript
imageService.getImageDataUrl('your-imageurl-value').subscribe(imageDataUrl => {
  console.log('Get Image Data Url:', imageDataUrl);
});
```

**8. getLoginImageDataUrl**

```javascript
imageService.getLoginImageDataUrl('your-imageurl-value', true).subscribe(loginImageDataUrl => {
  console.log('Get Login Image Data Url:', loginImageDataUrl);
});
```

**9. loadImageDataUrl**

```javascript
imageService.loadImageDataUrl('your-imagelink-value').subscribe(loadImageDataUrl => {
  console.log('Load Image Data Url:', loadImageDataUrl);
});
```

**10. getImageString**

```javascript
imageService.getImageString('your-imageurl-value').subscribe(imageString => {
  console.log('Get Image String:', imageString);
});
```

**11. resolveImageUrl**

```javascript
imageService.resolveImageUrl('your-imageurl-value').subscribe(resolveImageUrl => {
  console.log('Resolve Image Url:', resolveImageUrl);
});
```

**12. resolveLoginImageUrl**

```javascript
imageService.resolveLoginImageUrl('your-imageurl-value', true).subscribe(resolveLoginImageUrl => {
  console.log('Resolve Login Image Url:', resolveLoginImageUrl);
});
```

**13. downloadImage**

```javascript
imageService.downloadImage('your-type-value', 'your-key-value').subscribe(downloadImage => {
  console.log('Download Image:', downloadImage);
});
```

**14. exportImage**

```javascript
imageService.exportImage('your-type-value', 'your-key-value').subscribe(image => {
  console.log('Export Image:', image);
});
```

**15. importImage**

```javascript
imageService.importImage('your-imagedata-value').subscribe(image => {
  console.log('Import Image:', image);
});
```

---

### **INTEGRATION SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const integrationService = $injector.get(self.ctx.servicesMap.get('integrationService'));
```

**1. getIntegrations**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
integrationService.getIntegrations(pageLink).subscribe(integrations => {
  console.log('Get Integrations:', integrations);
});
```

**2. getIntegrationsConvertersInfo**

```javascript
integrationService.getIntegrationsConvertersInfo().subscribe(integrationsConvertersInfo => {
  console.log('Get Integrations Converters Info:', integrationsConvertersInfo);
});
```

**3. getIntegrationsConvertersInfoCached**

```javascript
integrationService.getIntegrationsConvertersInfoCached().subscribe(integrationsConvertersInfoCached => {
  console.log('Get Integrations Converters Info Cached:', integrationsConvertersInfoCached);
});
```

**4. getIntegrationsInfo**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
integrationService.getIntegrationsInfo(pageLink, true).subscribe(integrationsInfo => {
  console.log('Get Integrations Info:', integrationsInfo);
});
```

**5. getIntegrationsByEdgeTemplate**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
integrationService.getIntegrationsByEdgeTemplate(pageLink, true).subscribe(integrationsByEdgeTemplate => {
  console.log('Get Integrations By Edge Template:', integrationsByEdgeTemplate);
});
```

**6. getIntegrationsByIds**

```javascript
integrationService.getIntegrationsByIds('your-integrationids-value').subscribe(integrationsByIds => {
  console.log('Get Integrations By Ids:', integrationsByIds);
});
```

**7. getIntegration**

```javascript
integrationService.getIntegration('your-integration-id').subscribe(integration => {
  console.log('Get Integration:', integration);
});
```

**8. saveIntegration**

```javascript
integrationService.saveIntegration('your-integration-value').subscribe(integration => {
  console.log('Save Integration:', integration);
});
```

**9. getIntegrationHttpEndpointLink**

```javascript
integrationService.getIntegrationHttpEndpointLink('your-configuration-value', 'your-integrationtype-value', 'your-routingkey-value').subscribe(integrationHttpEndpointLink => {
  console.log('Get Integration Http Endpoint Link:', integrationHttpEndpointLink);
});
```

**10. toLowerCase**

```javascript
integrationService.toLowerCase().subscribe(toLowerCase => {
  console.log('To Lower Case:', toLowerCase);
});
```

**11. assignIntegrationToEdge**

```javascript
integrationService.assignIntegrationToEdge('your-edge-id', 'your-integration-id').subscribe(integrationToEdge => {
  console.log('Assign Integration To Edge:', integrationToEdge);
});
```

**12. getEdgeIntegrations**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
integrationService.getEdgeIntegrations('your-edge-id', pageLink).subscribe(edgeIntegrations => {
  console.log('Get Edge Integrations:', edgeIntegrations);
});
```

**13. exportIntegrationPackage**

```javascript
integrationService.exportIntegrationPackage('your-integration-id').subscribe(integrationPackage => {
  console.log('Export Integration Package:', integrationPackage);
});
```

---

### **JOB SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const jobService = $injector.get(self.ctx.servicesMap.get('jobService'));
```

**1. getJobById**

```javascript
jobService.getJobById('your--id').subscribe(jobById => {
  console.log('Get Job By Id:', jobById);
});
```

**2. getJobs**

```javascript
jobService.getJobs('your-query-value').subscribe(jobs => {
  console.log('Get Jobs:', jobs);
});
```

**3. cancelJob**

```javascript
jobService.cancelJob('your--id').subscribe(result => {
  console.log('Cancel Job:', result);
});
```

**4. reprocessJob**

```javascript
jobService.reprocessJob('your--id').subscribe(result => {
  console.log('Reprocess Job:', result);
});
```

**5. deleteJob**

```javascript
jobService.deleteJob('your--id').subscribe(result => {
  console.log('Delete Job:', result);
});
```

---

### **MOBILE APP SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const mobileAppService = $injector.get(self.ctx.servicesMap.get('mobileAppService'));
```

**1. saveMobileApp**

```javascript
mobileAppService.saveMobileApp('your-mobileapp-value').subscribe(mobileApp => {
  console.log('Save Mobile App:', mobileApp);
});
```

**2. getTenantMobileAppInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
mobileAppService.getTenantMobileAppInfos(pageLink, 'your-platformtype-value').subscribe(tenantMobileAppInfos => {
  console.log('Get Tenant Mobile App Infos:', tenantMobileAppInfos);
});
```

**3. getMobileAppInfoById**

```javascript
mobileAppService.getMobileAppInfoById('your--id').subscribe(mobileAppInfoById => {
  console.log('Get Mobile App Info By Id:', mobileAppInfoById);
});
```

**4. deleteMobileApp**

```javascript
mobileAppService.deleteMobileApp('your--id').subscribe(result => {
  console.log('Delete Mobile App:', result);
});
```

**5. getTenantMobileAppBundleInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
mobileAppService.getTenantMobileAppBundleInfos(pageLink).subscribe(tenantMobileAppBundleInfos => {
  console.log('Get Tenant Mobile App Bundle Infos:', tenantMobileAppBundleInfos);
});
```

**6. getMobileAppBundleInfoById**

```javascript
mobileAppService.getMobileAppBundleInfoById('your--id').subscribe(mobileAppBundleInfoById => {
  console.log('Get Mobile App Bundle Info By Id:', mobileAppBundleInfoById);
});
```

**7. deleteMobileAppBundle**

```javascript
mobileAppService.deleteMobileAppBundle('your--id').subscribe(result => {
  console.log('Delete Mobile App Bundle:', result);
});
```

---

### **MOBILE APPLICATION SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const mobileApplicationService = $injector.get(self.ctx.servicesMap.get('mobileApplicationService'));
```

**1. getMobileAppSettings**

```javascript
mobileApplicationService.getMobileAppSettings().subscribe(settings => {
  console.log('Get Mobile App Settings:', settings);
});
```

**2. getMergedMobileAppSettings**

```javascript
mobileApplicationService.getMergedMobileAppSettings().subscribe(mergedMobileAppSettings => {
  console.log('Get Merged Mobile App Settings:', mergedMobileAppSettings);
});
```

**3. saveMobileAppSettings**

```javascript
mobileApplicationService.saveMobileAppSettings('your-mobileappsettings-value').subscribe(mobileAppSettings => {
  console.log('Save Mobile App Settings:', mobileAppSettings);
});
```

**4. getMobileAppDeepLink**

```javascript
mobileApplicationService.getMobileAppDeepLink().subscribe(mobileAppDeepLink => {
  console.log('Get Mobile App Deep Link:', mobileAppDeepLink);
});
```

---

### **NOTIFICATION SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const notificationService = $injector.get(self.ctx.servicesMap.get('notificationService'));
```

**1. getNotifications**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
notificationService.getNotifications(pageLink).subscribe(notifications => {
  console.log('Get Notifications:', notifications);
});
```

**2. deleteNotification**

```javascript
notificationService.deleteNotification('your--id').subscribe(result => {
  console.log('Delete Notification:', result);
});
```

**3. markNotificationAsRead**

```javascript
notificationService.markNotificationAsRead('your--id').subscribe(result => {
  console.log('Mark Notification As Read:', result);
});
```

**4. markAllNotificationsAsRead**

```javascript
notificationService.markAllNotificationsAsRead().subscribe(result => {
  console.log('Mark All Notifications As Read:', result);
});
```

**5. createNotificationRequest**

```javascript
notificationService.createNotificationRequest('your-notification-value').subscribe(notificationRequest => {
  console.log('Create Notification Request:', notificationRequest);
});
```

**6. sendEntitiesLimitIncreaseRequest**

```javascript
notificationService.sendEntitiesLimitIncreaseRequest('your-entitytype-value').subscribe(result => {
  console.log('Send Entities Limit Increase Request:', result);
});
```

**7. sendAddonAccessRequest**

```javascript
notificationService.sendAddonAccessRequest('your-addontype-value').subscribe(result => {
  console.log('Send Addon Access Request:', result);
});
```

**8. sendPlanUpgradeRequest**

```javascript
notificationService.sendPlanUpgradeRequest('your-planname-value').subscribe(result => {
  console.log('Send Plan Upgrade Request:', result);
});
```

**9. getNotificationRequestById**

```javascript
notificationService.getNotificationRequestById('your--id').subscribe(notificationRequestById => {
  console.log('Get Notification Request By Id:', notificationRequestById);
});
```

**10. getAvailableDeliveryMethods**

```javascript
notificationService.getAvailableDeliveryMethods().subscribe(availableDeliveryMethods => {
  console.log('Get Available Delivery Methods:', availableDeliveryMethods);
});
```

**11. deleteNotificationRequest**

```javascript
notificationService.deleteNotificationRequest('your--id').subscribe(result => {
  console.log('Delete Notification Request:', result);
});
```

**12. getNotificationRequestPreview**

```javascript
notificationService.getNotificationRequestPreview('your-notification-value').subscribe(notificationRequestPreview => {
  console.log('Get Notification Request Preview:', notificationRequestPreview);
});
```

**13. getNotificationRequests**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
notificationService.getNotificationRequests(pageLink).subscribe(notificationRequests => {
  console.log('Get Notification Requests:', notificationRequests);
});
```

**14. getNotificationSettings**

```javascript
notificationService.getNotificationSettings().subscribe(notificationSettings => {
  console.log('Get Notification Settings:', notificationSettings);
});
```

**15. saveNotificationSettings**

```javascript
notificationService.saveNotificationSettings('your-notificationsettings-value').subscribe(notificationSettings => {
  console.log('Save Notification Settings:', notificationSettings);
});
```

**16. listSlackConversations**

```javascript
notificationService.listSlackConversations('your-type-value', 'your-access-token').subscribe(slackConversations => {
  console.log('List Slack Conversations:', slackConversations);
});
```

**17. saveNotificationRule**

```javascript
notificationService.saveNotificationRule('your-notificationrule-value').subscribe(notificationRule => {
  console.log('Save Notification Rule:', notificationRule);
});
```

**18. getNotificationRuleById**

```javascript
notificationService.getNotificationRuleById('your--id').subscribe(notificationRuleById => {
  console.log('Get Notification Rule By Id:', notificationRuleById);
});
```

**19. deleteNotificationRule**

```javascript
notificationService.deleteNotificationRule('your--id').subscribe(result => {
  console.log('Delete Notification Rule:', result);
});
```

**20. getNotificationRules**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
notificationService.getNotificationRules(pageLink).subscribe(rules => {
  console.log('Get Notification Rules:', rules);
});
```

**21. saveNotificationTarget**

```javascript
notificationService.saveNotificationTarget('your-notificationtarget-value').subscribe(notificationTarget => {
  console.log('Save Notification Target:', notificationTarget);
});
```

**22. getNotificationTargetById**

```javascript
notificationService.getNotificationTargetById('your--id').subscribe(notificationTargetById => {
  console.log('Get Notification Target By Id:', notificationTargetById);
});
```

**23. deleteNotificationTarget**

```javascript
notificationService.deleteNotificationTarget('your--id').subscribe(result => {
  console.log('Delete Notification Target:', result);
});
```

**24. getNotificationTargetsByIds**

```javascript
notificationService.getNotificationTargetsByIds('your-ids-value').subscribe(notificationTargetsByIds => {
  console.log('Get Notification Targets By Ids:', notificationTargetsByIds);
});
```

**25. getNotificationTargets**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
notificationService.getNotificationTargets(pageLink, 'your-type-value').subscribe(targets => {
  console.log('Get Notification Targets:', targets);
});
```

**26. getRecipientsForNotificationTargetConfig**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
notificationService.getRecipientsForNotificationTargetConfig('your-notificationtarget-value', pageLink).subscribe(recipientsForNotificationTargetConfig => {
  console.log('Get Recipients For Notification Target Config:', recipientsForNotificationTargetConfig);
});
```

**27. saveNotificationTemplate**

```javascript
notificationService.saveNotificationTemplate('your-notificationtarget-value').subscribe(notificationTemplate => {
  console.log('Save Notification Template:', notificationTemplate);
});
```

**28. getNotificationTemplateById**

```javascript
notificationService.getNotificationTemplateById('your--id').subscribe(notificationTemplateById => {
  console.log('Get Notification Template By Id:', notificationTemplateById);
});
```

**29. deleteNotificationTemplate**

```javascript
notificationService.deleteNotificationTemplate('your--id').subscribe(result => {
  console.log('Delete Notification Template:', result);
});
```

**30. getNotificationTemplates**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
notificationService.getNotificationTemplates(pageLink, 'your-notificationtypes-value').subscribe(templates => {
  console.log('Get Notification Templates:', templates);
});
```

**31. getNotificationUserSettings**

```javascript
notificationService.getNotificationUserSettings().subscribe(notificationUserSettings => {
  console.log('Get Notification User Settings:', notificationUserSettings);
});
```

**32. saveNotificationUserSettings**

```javascript
notificationService.saveNotificationUserSettings('your-settings-value').subscribe(notificationUserSettings => {
  console.log('Save Notification User Settings:', notificationUserSettings);
});
```

**33. sendAddonAccessError**

```javascript
notificationService.sendAddonAccessError('your-addontype-value').subscribe(result => {
  console.log('Send Addon Access Error:', result);
});
```

---

### **O AUTH 2 SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const oAuth2Service = $injector.get(self.ctx.servicesMap.get('oAuth2Service'));
```

**1. getOAuth2Template**

```javascript
oAuth2Service.getOAuth2Template().subscribe(oAuth2Template => {
  console.log('Get O Auth 2 Template:', oAuth2Template);
});
```

**2. saveOAuth2Client**

```javascript
oAuth2Service.saveOAuth2Client('your-oauth2client-value').subscribe(oAuth2Client => {
  console.log('Save O Auth 2 Client:', oAuth2Client);
});
```

**3. findTenantOAuth2ClientInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
oAuth2Service.findTenantOAuth2ClientInfos(pageLink).subscribe(tenantOAuth2ClientInfos => {
  console.log('Find Tenant O Auth 2 Client Infos:', tenantOAuth2ClientInfos);
});
```

**4. findTenantOAuth2ClientInfosByIds**

```javascript
oAuth2Service.findTenantOAuth2ClientInfosByIds('your-clientids-value').subscribe(tenantOAuth2ClientInfosByIds => {
  console.log('Find Tenant O Auth 2 Client Infos By Ids:', tenantOAuth2ClientInfosByIds);
});
```

**5. getOAuth2ClientById**

```javascript
oAuth2Service.getOAuth2ClientById('your--id').subscribe(oAuth2ClientById => {
  console.log('Get O Auth 2 Client By Id:', oAuth2ClientById);
});
```

**6. deleteOauth2Client**

```javascript
oAuth2Service.deleteOauth2Client('your--id').subscribe(result => {
  console.log('Delete Oauth 2 Client:', result);
});
```

**7. getLoginProcessingUrl**

```javascript
oAuth2Service.getLoginProcessingUrl().subscribe(loginProcessingUrl => {
  console.log('Get Login Processing Url:', loginProcessingUrl);
});
```

---

### **OTA PACKAGE SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const otaPackageService = $injector.get(self.ctx.servicesMap.get('otaPackageService'));
```

**1. getOtaPackages**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
otaPackageService.getOtaPackages(pageLink).subscribe(otaPackages => {
  console.log('Get Ota Packages:', otaPackages);
});
```

**2. getOtaPackagesInfoByDeviceProfileId**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
otaPackageService.getOtaPackagesInfoByDeviceProfileId(pageLink, 'your-deviceprofile-id', 'your-type-value').subscribe(otaPackagesInfoByDeviceProfileId => {
  console.log('Get Ota Packages Info By Device Profile Id:', otaPackagesInfoByDeviceProfileId);
});
```

**3. getOtaPackage**

```javascript
otaPackageService.getOtaPackage('your-otapackage-id').subscribe(otaPackage => {
  console.log('Get Ota Package:', otaPackage);
});
```

**4. getOtaPackageInfo**

```javascript
otaPackageService.getOtaPackageInfo('your-otapackage-id').subscribe(otaPackageInfo => {
  console.log('Get Ota Package Info:', otaPackageInfo);
});
```

**5. downloadOtaPackage**

```javascript
otaPackageService.downloadOtaPackage('your-otapackage-id').subscribe(downloadOtaPackage => {
  console.log('Download Ota Package:', downloadOtaPackage);
});
```

**6. saveOtaPackage**

```javascript
otaPackageService.saveOtaPackage('your-otapackage-value').subscribe(otaPackage => {
  console.log('Save Ota Package:', otaPackage);
});
```

**7. saveOtaPackageInfo**

```javascript
otaPackageService.saveOtaPackageInfo('your-otapackageinfo-value').subscribe(otaPackageInfo => {
  console.log('Save Ota Package Info:', otaPackageInfo);
});
```

**8. uploadOtaPackageFile**

```javascript
otaPackageService.uploadOtaPackageFile('your-otapackage-id', 'your-file-value', 'your-checksumalgorithm-value', 'your-checksum-value').subscribe(uploadOtaPackageFile => {
  console.log('Upload Ota Package File:', uploadOtaPackageFile);
});
```

**9. getOtaPackageInfoByDeviceGroupId**

```javascript
otaPackageService.getOtaPackageInfoByDeviceGroupId('your-devicegroup-id', 'your-type-value').subscribe(otaPackageInfoByDeviceGroupId => {
  console.log('Get Ota Package Info By Device Group Id:', otaPackageInfoByDeviceGroupId);
});
```

**10. getOtaPackagesInfoByDeviceGroupId**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
otaPackageService.getOtaPackagesInfoByDeviceGroupId(pageLink, 'your-devicegroup-id', 'your-type-value').subscribe(otaPackagesInfoByDeviceGroupId => {
  console.log('Get Ota Packages Info By Device Group Id:', otaPackagesInfoByDeviceGroupId);
});
```

**11. countUpdateDeviceAfterChangePackage**

```javascript
otaPackageService.countUpdateDeviceAfterChangePackage('your-type-value', 'your-entity-id', 'your-package-id').subscribe(countUpdateDeviceAfterChangePackage => {
  console.log('Count Update Device After Change Package:', countUpdateDeviceAfterChangePackage);
});
```

**12. confirmDialogUpdatePackage**

```javascript
otaPackageService.confirmDialogUpdatePackage('your-entity-value', 'your-originentity-value').subscribe(confirmDialogUpdatePackage => {
  console.log('Confirm Dialog Update Package:', confirmDialogUpdatePackage);
});
```

---

### **QUEUE SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const queueService = $injector.get(self.ctx.servicesMap.get('queueService'));
```

**1. getQueueById**

```javascript
queueService.getQueueById('your-queue-id').subscribe(queueById => {
  console.log('Get Queue By Id:', queueById);
});
```

**2. getQueueByName**

```javascript
queueService.getQueueByName('your-queuename-value').subscribe(queueByName => {
  console.log('Get Queue By Name:', queueByName);
});
```

**3. getTenantQueuesByServiceType**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
queueService.getTenantQueuesByServiceType(pageLink, 'your-servicetype-value').subscribe(tenantQueuesByServiceType => {
  console.log('Get Tenant Queues By Service Type:', tenantQueuesByServiceType);
});
```

**4. saveQueue**

```javascript
queueService.saveQueue('your-queue-value', 'your-servicetype-value').subscribe(queue => {
  console.log('Save Queue:', queue);
});
```

**5. getQueueStatistics**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
queueService.getQueueStatistics(pageLink).subscribe(queueStatistics => {
  console.log('Get Queue Statistics:', queueStatistics);
});
```

**6. getQueueStatisticsById**

```javascript
queueService.getQueueStatisticsById('your-queuestat-id').subscribe(queueStatisticsById => {
  console.log('Get Queue Statistics By Id:', queueStatisticsById);
});
```

**7. getQueueStatisticsByIds**

```javascript
queueService.getQueueStatisticsByIds('your-queuestatids-value').subscribe(queueStatisticsByIds => {
  console.log('Get Queue Statistics By Ids:', queueStatisticsByIds);
});
```

---

### **REPORT SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const reportService = $injector.get(self.ctx.servicesMap.get('reportService'));
```

**1. getReport**

```javascript
reportService.getReport('your-report-id').subscribe(report => {
  console.log('Get Report:', report);
});
```

**2. getReports**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
reportService.getReports(pageLink).subscribe(reports => {
  console.log('Get Reports:', reports);
});
```

**3. getReportInfos**

```javascript
reportService.getReportInfos('your-query-value').subscribe(reportInfos => {
  console.log('Get Report Infos:', reportInfos);
});
```

**4. downloadReport**

```javascript
reportService.downloadReport('your-report-id').subscribe(downloadReport => {
  console.log('Download Report:', downloadReport);
});
```

**5. requestReport**

```javascript
reportService.requestReport('your-reportrequest-value').subscribe(requestReport => {
  console.log('Request Report:', requestReport);
});
```

**6. downloadTestReport**

```javascript
reportService.downloadTestReport('your-reportrequest-value').subscribe(downloadTestReport => {
  console.log('Download Test Report:', downloadTestReport);
});
```

**7. updateReportPublicStatus**

```javascript
reportService.updateReportPublicStatus('your-report-id', true).subscribe(reportPublicStatus => {
  console.log('Update Report Public Status:', reportPublicStatus);
});
```

**8. getPublicReportDownloadUrl**

```javascript
reportService.getPublicReportDownloadUrl('your-publickey-value').subscribe(publicReportDownloadUrl => {
  console.log('Get Public Report Download Url:', publicReportDownloadUrl);
});
```

**9. getReportsInfosByIds**

```javascript
reportService.getReportsInfosByIds('your-reportids-value').subscribe(reportsInfosByIds => {
  console.log('Get Reports Infos By Ids:', reportsInfosByIds);
});
```

**10. processDownloadReportResponse**

```javascript
reportService.processDownloadReportResponse('your-response-value').subscribe(processDownloadReportResponse => {
  console.log('Process Download Report Response:', processDownloadReportResponse);
});
```

---

### **REPORT TEMPLATE SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const reportTemplateService = $injector.get(self.ctx.servicesMap.get('reportTemplateService'));
```

**1. getReportTemplateInfo**

```javascript
reportTemplateService.getReportTemplateInfo('your-reporttemplate-id').subscribe(reportTemplateInfo => {
  console.log('Get Report Template Info:', reportTemplateInfo);
});
```

**2. getAllReportTemplateInfos**

```javascript
reportTemplateService.getAllReportTemplateInfos('your-query-value').subscribe(allReportTemplateInfos => {
  console.log('Get All Report Template Infos:', allReportTemplateInfos);
});
```

**3. getReportTemplatesByIds**

```javascript
reportTemplateService.getReportTemplatesByIds('your-reporttemplateids-value').subscribe(reportTemplatesByIds => {
  console.log('Get Report Templates By Ids:', reportTemplatesByIds);
});
```

---

### **RESOURCE SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const resourceService = $injector.get(self.ctx.servicesMap.get('resourceService'));

// Alternative: Direct context access
const resourceService = self.ctx.resourceService;
```

**1. getResources**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.resourceService.getResources(pageLink, 'your-resourcetype-value', 'your-resourcesubtype-value').subscribe(resources => {
  console.log('Get Resources:', resources);
});
```

**2. getTenantResources**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.resourceService.getTenantResources(pageLink).subscribe(tenantResources => {
  console.log('Get Tenant Resources:', tenantResources);
});
```

**3. getResource**

```javascript
self.ctx.resourceService.getResource('your-resource-id').subscribe(resource => {
  console.log('Get Resource:', resource);
});
```

**4. getResourceInfoById**

```javascript
self.ctx.resourceService.getResourceInfoById('your-resource-id').subscribe(resourceInfoById => {
  console.log('Get Resource Info By Id:', resourceInfoById);
});
```

**5. getResourceInfo**

```javascript
self.ctx.resourceService.getResourceInfo('your-type-value', 'your-scope-value', 'your-key-value').subscribe(resourceInfo => {
  console.log('Get Resource Info:', resourceInfo);
});
```

**6. downloadResource**

```javascript
self.ctx.resourceService.downloadResource('your-resource-id').subscribe(downloadResource => {
  console.log('Download Resource:', downloadResource);
});
```

**7. saveResources**

```javascript
self.ctx.resourceService.saveResources('your-resources-value').subscribe(resources => {
  console.log('Save Resources:', resources);
});
```

**8. saveResource**

```javascript
self.ctx.resourceService.saveResource('your-resource-value').subscribe(resource => {
  console.log('Save Resource:', resource);
});
```

**9. uploadResources**

```javascript
self.ctx.resourceService.uploadResources('your-resources-value').subscribe(uploadResources => {
  console.log('Upload Resources:', uploadResources);
});
```

**10. uploadResource**

```javascript
self.ctx.resourceService.uploadResource('your-resource-value').subscribe(uploadResource => {
  console.log('Upload Resource:', uploadResource);
});
```

**11. updatedResourceInfo**

```javascript
self.ctx.resourceService.updatedResourceInfo('your-resource-id', 'your-updatedresources-value').subscribe(dResourceInfo => {
  console.log('Updated Resource Info:', dResourceInfo);
});
```

**12. updatedResourceData**

```javascript
self.ctx.resourceService.updatedResourceData('your-resource-id', 'your-data-value').subscribe(dResourceData => {
  console.log('Updated Resource Data:', dResourceData);
});
```

**13. getResourcesByIds**

```javascript
self.ctx.resourceService.getResourcesByIds('your-ids-value').subscribe(resourcesByIds => {
  console.log('Get Resources By Ids:', resourcesByIds);
});
```

---

### **ROLE SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const roleService = $injector.get(self.ctx.servicesMap.get('roleService'));
```

**1. getRoles**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
roleService.getRoles(pageLink, 'your-type-value').subscribe(roles => {
  console.log('Get Roles:', roles);
});
```

**2. getRolesByIds**

```javascript
roleService.getRolesByIds('your-roleids-value').subscribe(rolesByIds => {
  console.log('Get Roles By Ids:', rolesByIds);
});
```

**3. getRole**

```javascript
roleService.getRole('your-role-id').subscribe(role => {
  console.log('Get Role:', role);
});
```

**4. saveRole**

```javascript
roleService.saveRole('your-role-value').subscribe(role => {
  console.log('Save Role:', role);
});
```

**5. saveGroupPermission**

```javascript
roleService.saveGroupPermission('your-grouppermission-value').subscribe(groupPermission => {
  console.log('Save Group Permission:', groupPermission);
});
```

**6. deleteGroupPermissions**

```javascript
roleService.deleteGroupPermissions('your-grouppermissionids-value').subscribe(groupPermissions => {
  console.log('Delete Group Permissions:', groupPermissions);
});
```

**7. deleteGroupPermission**

```javascript
roleService.deleteGroupPermission('your-grouppermission-id').subscribe(groupPermission => {
  console.log('Delete Group Permission:', groupPermission);
});
```

**8. getUserGroupPermissions**

```javascript
roleService.getUserGroupPermissions('your-usergroup-id').subscribe(userGroupPermissions => {
  console.log('Get User Group Permissions:', userGroupPermissions);
});
```

**9. getEntityGroupPermissions**

```javascript
roleService.getEntityGroupPermissions('your-entitygroup-id').subscribe(entityGroupPermissions => {
  console.log('Get Entity Group Permissions:', entityGroupPermissions);
});
```

**10. getGroupPermissionInfo**

```javascript
roleService.getGroupPermissionInfo('your-grouppermission-id', true).subscribe(groupPermissionInfo => {
  console.log('Get Group Permission Info:', groupPermissionInfo);
});
```

**11. loadUserGroupPermissionInfos**

```javascript
roleService.loadUserGroupPermissionInfos('your-grouppermissions-value').subscribe(loadUserGroupPermissionInfos => {
  console.log('Load User Group Permission Infos:', loadUserGroupPermissionInfos);
});
```

---

### **RULE CHAIN SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const ruleChainService = $injector.get(self.ctx.servicesMap.get('ruleChainService'));
```

**1. getRuleChains**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
ruleChainService.getRuleChains(pageLink, 'your-type-value').subscribe(ruleChains => {
  console.log('Get Rule Chains:', ruleChains);
});
```

**2. getRuleChainsByIds**

```javascript
ruleChainService.getRuleChainsByIds('your-rulechainids-value').subscribe(ruleChainsByIds => {
  console.log('Get Rule Chains By Ids:', ruleChainsByIds);
});
```

**3. getRuleChain**

```javascript
ruleChainService.getRuleChain('your-rulechain-id').subscribe(ruleChain => {
  console.log('Get Rule Chain:', ruleChain);
});
```

**4. getRuleChainOutputLabels**

```javascript
ruleChainService.getRuleChainOutputLabels('your-rulechain-id').subscribe(ruleChainOutputLabels => {
  console.log('Get Rule Chain Output Labels:', ruleChainOutputLabels);
});
```

**5. createDefaultRuleChain**

```javascript
ruleChainService.createDefaultRuleChain('your-rulechainname-value').subscribe(defaultRuleChain => {
  console.log('Create Default Rule Chain:', defaultRuleChain);
});
```

**6. saveRuleChain**

```javascript
ruleChainService.saveRuleChain('your-rulechain-value').subscribe(ruleChain => {
  console.log('Save Rule Chain:', ruleChain);
});
```

**7. setRootRuleChain**

```javascript
ruleChainService.setRootRuleChain('your-rulechain-id').subscribe(rootRuleChain => {
  console.log('Set Root Rule Chain:', rootRuleChain);
});
```

**8. getRuleChainMetadata**

```javascript
ruleChainService.getRuleChainMetadata('your-rulechain-id').subscribe(ruleChainMetadata => {
  console.log('Get Rule Chain Metadata:', ruleChainMetadata);
});
```

**9. saveRuleChainMetadata**

```javascript
ruleChainService.saveRuleChainMetadata('your-rulechainmetadata-value').subscribe(ruleChainMetadata => {
  console.log('Save Rule Chain Metadata:', ruleChainMetadata);
});
```

**10. getRuleNodeComponents**

```javascript
ruleChainService.getRuleNodeComponents('your-modulesmap-value', 'your-rulechaintype-value').subscribe(ruleNodeComponents => {
  console.log('Get Rule Node Components:', ruleNodeComponents);
});
```

**11. getRuleNodeConfigComponent**

```javascript
ruleChainService.getRuleNodeConfigComponent('your-directive-value').subscribe(ruleNodeConfigComponent => {
  console.log('Get Rule Node Config Component:', ruleNodeConfigComponent);
});
```

**12. getRuleNodeComponentByClazz**

```javascript
ruleChainService.getRuleNodeComponentByClazz('your-rulechaintype-value', 'your-clazz-value').subscribe(ruleNodeComponentByClazz => {
  console.log('Get Rule Node Component By Clazz:', ruleNodeComponentByClazz);
});
```

**13. getRuleNodeSupportedLinks**

```javascript
ruleChainService.getRuleNodeSupportedLinks('your-component-value').subscribe(ruleNodeSupportedLinks => {
  console.log('Get Rule Node Supported Links:', ruleNodeSupportedLinks);
});
```

**14. ruleNodeAllowCustomLinks**

```javascript
ruleChainService.ruleNodeAllowCustomLinks('your-component-value').subscribe(ruleNodeAllowCustomLinks => {
  console.log('Rule Node Allow Custom Links:', ruleNodeAllowCustomLinks);
});
```

**15. ruleNodeSourceRuleChainId**

```javascript
ruleChainService.ruleNodeSourceRuleChainId('your-component-value').subscribe(ruleNodeSourceRuleChainId => {
  console.log('Rule Node Source Rule Chain Id:', ruleNodeSourceRuleChainId);
});
```

**16. getLatestRuleNodeDebugInput**

```javascript
ruleChainService.getLatestRuleNodeDebugInput('your-rulenode-id').subscribe(latestRuleNodeDebugInput => {
  console.log('Get Latest Rule Node Debug Input:', latestRuleNodeDebugInput);
});
```

**17. testScript**

```javascript
ruleChainService.testScript('your-inputparams-value', 'your-scriptlang-value').subscribe(testScript => {
  console.log('Test Script:', testScript);
});
```

**18. loadRuleNodeComponents**

```javascript
ruleChainService.loadRuleNodeComponents('your-rulechaintype-value').subscribe(loadRuleNodeComponents => {
  console.log('Load Rule Node Components:', loadRuleNodeComponents);
});
```

**19. resolveRuleNodeComponentsUiResources**

```javascript
ruleChainService.resolveRuleNodeComponentsUiResources('your-components-value', 'your-modulesmap-value').subscribe(resolveRuleNodeComponentsUiResources => {
  console.log('Resolve Rule Node Components Ui Resources:', resolveRuleNodeComponentsUiResources);
});
```

**20. resolveRuleNodeComponentUiResources**

```javascript
ruleChainService.resolveRuleNodeComponentUiResources('your-component-value', 'your-modulesmap-value').subscribe(resolveRuleNodeComponentUiResources => {
  console.log('Resolve Rule Node Component Ui Resources:', resolveRuleNodeComponentUiResources);
});
```

**21. getEdgeRuleChains**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
ruleChainService.getEdgeRuleChains('your-edge-id', pageLink).subscribe(edgeRuleChains => {
  console.log('Get Edge Rule Chains:', edgeRuleChains);
});
```

**22. assignRuleChainToEdge**

```javascript
ruleChainService.assignRuleChainToEdge('your-edge-id', 'your-rulechain-id').subscribe(ruleChainToEdge => {
  console.log('Assign Rule Chain To Edge:', ruleChainToEdge);
});
```

**23. setEdgeTemplateRootRuleChain**

```javascript
ruleChainService.setEdgeTemplateRootRuleChain('your-rulechain-id').subscribe(edgeTemplateRootRuleChain => {
  console.log('Set Edge Template Root Rule Chain:', edgeTemplateRootRuleChain);
});
```

**24. setAutoAssignToEdgeRuleChain**

```javascript
ruleChainService.setAutoAssignToEdgeRuleChain('your-rulechain-id').subscribe(autoAssignToEdgeRuleChain => {
  console.log('Set Auto Assign To Edge Rule Chain:', autoAssignToEdgeRuleChain);
});
```

**25. unsetAutoAssignToEdgeRuleChain**

```javascript
ruleChainService.unsetAutoAssignToEdgeRuleChain('your-rulechain-id').subscribe(unsetAutoAssignToEdgeRuleChain => {
  console.log('Unset Auto Assign To Edge Rule Chain:', unsetAutoAssignToEdgeRuleChain);
});
```

**26. getAutoAssignToEdgeRuleChains**

```javascript
ruleChainService.getAutoAssignToEdgeRuleChains().subscribe(autoAssignToEdgeRuleChains => {
  console.log('Get Auto Assign To Edge Rule Chains:', autoAssignToEdgeRuleChains);
});
```

**27. setEdgeRootRuleChain**

```javascript
ruleChainService.setEdgeRootRuleChain('your-edge-id', 'your-rulechain-id').subscribe(edgeRootRuleChain => {
  console.log('Set Edge Root Rule Chain:', edgeRootRuleChain);
});
```

---

### **SCHEDULER EVENT SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const schedulerEventService = $injector.get(self.ctx.servicesMap.get('schedulerEventService'));
```

**1. getSchedulerEvents**

```javascript
schedulerEventService.getSchedulerEvents('your-type-value').subscribe(schedulerEvents => {
  console.log('Get Scheduler Events:', schedulerEvents);
});
```

**2. getSchedulerEventsByPageLink**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
schedulerEventService.getSchedulerEventsByPageLink('your-type-value', pageLink, 'your-edge-id').subscribe(schedulerEventsByPageLink => {
  console.log('Get Scheduler Events By Page Link:', schedulerEventsByPageLink);
});
```

**3. getCalendarSchedulerEvents**

```javascript
schedulerEventService.getCalendarSchedulerEvents('your-type-value', 0, 0, 'your-textsearch-value', 'your-edge-id').subscribe(calendarSchedulerEvents => {
  console.log('Get Calendar Scheduler Events:', calendarSchedulerEvents);
});
```

**4. getSchedulerEventsByIds**

```javascript
schedulerEventService.getSchedulerEventsByIds('your-schedulereventids-value').subscribe(schedulerEventsByIds => {
  console.log('Get Scheduler Events By Ids:', schedulerEventsByIds);
});
```

**5. getSchedulerEventInfo**

```javascript
schedulerEventService.getSchedulerEventInfo('your-schedulerevent-id').subscribe(schedulerEventInfo => {
  console.log('Get Scheduler Event Info:', schedulerEventInfo);
});
```

**6. getSchedulerEvent**

```javascript
schedulerEventService.getSchedulerEvent('your-schedulerevent-id').subscribe(schedulerEvent => {
  console.log('Get Scheduler Event:', schedulerEvent);
});
```

**7. saveSchedulerEvent**

```javascript
schedulerEventService.saveSchedulerEvent('your-schedulerevent-value').subscribe(schedulerEvent => {
  console.log('Save Scheduler Event:', schedulerEvent);
});
```

**8. getEdgeSchedulerEvents**

```javascript
schedulerEventService.getEdgeSchedulerEvents('your-edge-id').subscribe(edgeSchedulerEvents => {
  console.log('Get Edge Scheduler Events:', edgeSchedulerEvents);
});
```

**9. assignSchedulerEventToEdge**

```javascript
schedulerEventService.assignSchedulerEventToEdge('your-edge-id', 'your-schedulerevent-id').subscribe(schedulerEventToEdge => {
  console.log('Assign Scheduler Event To Edge:', schedulerEventToEdge);
});
```

**10. getScheduledReports**

```javascript
schedulerEventService.getScheduledReports('your-query-value').subscribe(scheduledReports => {
  console.log('Get Scheduled Reports:', scheduledReports);
});
```

---

### **SECRET STORAGE SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const secretStorageService = $injector.get(self.ctx.servicesMap.get('secretStorageService'));
```

**1. getSecrets**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
secretStorageService.getSecrets(pageLink).subscribe(secrets => {
  console.log('Get Secrets:', secrets);
});
```

**2. saveSecret**

```javascript
secretStorageService.saveSecret('your-secret-value').subscribe(secret => {
  console.log('Save Secret:', secret);
});
```

**3. updateSecretDescription**

```javascript
secretStorageService.updateSecretDescription('your-secret-id', 'your-description-value').subscribe(result => {
  console.log('Update Secret Description:', result);
});
```

**4. updateSecretValue**

```javascript
secretStorageService.updateSecretValue('your-secret-id', 'your-value-value').subscribe(result => {
  console.log('Update Secret Value:', result);
});
```

**5. getSecretByName**

```javascript
secretStorageService.getSecretByName('your-name-value').subscribe(secretByName => {
  console.log('Get Secret By Name:', secretByName);
});
```

---

### **SELF REGISTRATION SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const selfRegistrationService = $injector.get(self.ctx.servicesMap.get('selfRegistrationService'));
```

**1. getRegistrationLink**

```javascript
selfRegistrationService.getRegistrationLink('your-domainname-value').subscribe(registrationLink => {
  console.log('Get Registration Link:', registrationLink);
});
```

**2. loadSelfRegistrationParams**

```javascript
selfRegistrationService.loadSelfRegistrationParams().subscribe(loadSelfRegistrationParams => {
  console.log('Load Self Registration Params:', loadSelfRegistrationParams);
});
```

**3. loadPrivacyPolicy**

```javascript
selfRegistrationService.loadPrivacyPolicy().subscribe(loadPrivacyPolicy => {
  console.log('Load Privacy Policy:', loadPrivacyPolicy);
});
```

**4. loadTermsOfUse**

```javascript
selfRegistrationService.loadTermsOfUse().subscribe(loadTermsOfUse => {
  console.log('Load Terms Of Use:', loadTermsOfUse);
});
```

**5. isAvailablePage**

```javascript
selfRegistrationService.isAvailablePage().subscribe(isAvailablePage => {
  console.log('Is Available Page:', isAvailablePage);
});
```

**6. saveSelfRegistrationParams**

```javascript
selfRegistrationService.saveSelfRegistrationParams('your-selfregistrationparams-value').subscribe(selfRegistrationParams => {
  console.log('Save Self Registration Params:', selfRegistrationParams);
});
```

**7. getSelfRegistrationParams**

```javascript
selfRegistrationService.getSelfRegistrationParams().subscribe(selfRegistrationParams => {
  console.log('Get Self Registration Params:', selfRegistrationParams);
});
```

---

### **SIGNUP SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const signupService = $injector.get(self.ctx.servicesMap.get('signupService'));
```

**1. signup**

```javascript
signupService.signup('your-signuprequest-value').subscribe(signup => {
  console.log('Signup:', signup);
});
```

**2. acceptPrivacyPolicy**

```javascript
signupService.acceptPrivacyPolicy().subscribe(acceptPrivacyPolicy => {
  console.log('Accept Privacy Policy:', acceptPrivacyPolicy);
});
```

**3. deleteTenantAccount**

```javascript
signupService.deleteTenantAccount().subscribe(tenantAccount => {
  console.log('Delete Tenant Account:', tenantAccount);
});
```

**4. isDisplayWelcome**

```javascript
signupService.isDisplayWelcome().subscribe(isDisplayWelcome => {
  console.log('Is Display Welcome:', isDisplayWelcome);
});
```

**5. setNotDisplayWelcome**

```javascript
signupService.setNotDisplayWelcome().subscribe(notDisplayWelcome => {
  console.log('Set Not Display Welcome:', notDisplayWelcome);
});
```

---

### **SOLUTIONS CREATOR SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const solutionsCreatorService = $injector.get(self.ctx.servicesMap.get('solutionsCreatorService'));
```

**1. getSolutionById**

```javascript
solutionsCreatorService.getSolutionById('your-solution-id').subscribe(solutionById => {
  console.log('Get Solution By Id:', solutionById);
});
```

**2. startSolution**

```javascript
solutionsCreatorService.startSolution().subscribe(startSolution => {
  console.log('Start Solution:', startSolution);
});
```

**3. clearStep**

```javascript
solutionsCreatorService.clearStep('your-solution-id', 'your-step-value').subscribe(result => {
  console.log('Clear Step:', result);
});
```

**4. createSolution**

```javascript
solutionsCreatorService.createSolution('your-solution-id').subscribe(solution => {
  console.log('Create Solution:', solution);
});
```

**5. chatSolution**

```javascript
solutionsCreatorService.chatSolution('your-solution-id', 'your-step-value', 'your-msg-value').subscribe(chatSolution => {
  console.log('Chat Solution:', chatSolution);
});
```

**6. updateSolutionData**

```javascript
solutionsCreatorService.updateSolutionData('your-solution-id', 'your-datakey-value', 'your-msg-value').subscribe(solutionData => {
  console.log('Update Solution Data:', solutionData);
});
```

**7. installSolution**

```javascript
solutionsCreatorService.installSolution('your-solution-id').subscribe(installSolution => {
  console.log('Install Solution:', installSolution);
});
```

**8. uninstallSolution**

```javascript
solutionsCreatorService.uninstallSolution('your-solution-id').subscribe(uninstallSolution => {
  console.log('Uninstall Solution:', uninstallSolution);
});
```

**9. getSolutions**

```javascript
solutionsCreatorService.getSolutions().subscribe(solutions => {
  console.log('Get Solutions:', solutions);
});
```

**10. deleteSolution**

```javascript
solutionsCreatorService.deleteSolution('your-solution-id').subscribe(result => {
  console.log('Delete Solution:', result);
});
```

---

### **SYSTEM SETUP SERVICE**

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

---

### **TENANT PROFILE SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const tenantProfileService = $injector.get(self.ctx.servicesMap.get('tenantProfileService'));
```

**1. getTenantProfiles**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
tenantProfileService.getTenantProfiles(pageLink).subscribe(tenantProfiles => {
  console.log('Get Tenant Profiles:', tenantProfiles);
});
```

**2. getTenantProfile**

```javascript
tenantProfileService.getTenantProfile('your-tenantprofile-id').subscribe(tenantProfile => {
  console.log('Get Tenant Profile:', tenantProfile);
});
```

**3. saveTenantProfile**

```javascript
tenantProfileService.saveTenantProfile('your-tenantprofile-value').subscribe(tenantProfile => {
  console.log('Save Tenant Profile:', tenantProfile);
});
```

**4. setDefaultTenantProfile**

```javascript
tenantProfileService.setDefaultTenantProfile('your-tenantprofile-id').subscribe(defaultTenantProfile => {
  console.log('Set Default Tenant Profile:', defaultTenantProfile);
});
```

**5. getDefaultTenantProfileInfo**

```javascript
tenantProfileService.getDefaultTenantProfileInfo().subscribe(defaultTenantProfileInfo => {
  console.log('Get Default Tenant Profile Info:', defaultTenantProfileInfo);
});
```

**6. getTenantProfileInfo**

```javascript
tenantProfileService.getTenantProfileInfo('your-tenantprofile-id').subscribe(tenantProfileInfo => {
  console.log('Get Tenant Profile Info:', tenantProfileInfo);
});
```

**7. getTenantProfileInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
tenantProfileService.getTenantProfileInfos(pageLink).subscribe(tenantProfileInfos => {
  console.log('Get Tenant Profile Infos:', tenantProfileInfos);
});
```

**8. getTenantProfilesByIds**

```javascript
tenantProfileService.getTenantProfilesByIds('your-tenantprofileids-value').subscribe(tenantProfilesByIds => {
  console.log('Get Tenant Profiles By Ids:', tenantProfilesByIds);
});
```

---

### **TENANT SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const tenantService = $injector.get(self.ctx.servicesMap.get('tenantService'));
```

**1. getTenants**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
tenantService.getTenants(pageLink).subscribe(tenants => {
  console.log('Get Tenants:', tenants);
});
```

**2. getTenantsByIds**

```javascript
tenantService.getTenantsByIds('your-tenantids-value').subscribe(tenantsByIds => {
  console.log('Get Tenants By Ids:', tenantsByIds);
});
```

**3. getTenantInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
tenantService.getTenantInfos(pageLink).subscribe(tenantInfos => {
  console.log('Get Tenant Infos:', tenantInfos);
});
```

**4. getTenant**

```javascript
tenantService.getTenant('your-tenant-id').subscribe(tenant => {
  console.log('Get Tenant:', tenant);
});
```

**5. getTenantInfo**

```javascript
tenantService.getTenantInfo('your-tenant-id').subscribe(tenantInfo => {
  console.log('Get Tenant Info:', tenantInfo);
});
```

**6. saveTenant**

```javascript
tenantService.saveTenant('your-tenant-value').subscribe(tenant => {
  console.log('Save Tenant:', tenant);
});
```

---

### **TRENDZ SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const trendzService = $injector.get(self.ctx.servicesMap.get('trendzService'));
```

**1. getTrendzSummary**

```javascript
trendzService.getTrendzSummary().subscribe(trendzSummary => {
  console.log('Get Trendz Summary:', trendzSummary);
});
```

**2. performTrendzHealthcheck**

```javascript
trendzService.performTrendzHealthcheck().subscribe(performTrendzHealthcheck => {
  console.log('Perform Trendz Healthcheck:', performTrendzHealthcheck);
});
```

**3. getTrendzConfig**

```javascript
trendzService.getTrendzConfig().subscribe(trendzConfig => {
  console.log('Get Trendz Config:', trendzConfig);
});
```

**4. saveTrendzConfig**

```javascript
trendzService.saveTrendzConfig('your-trendzconfig-value').subscribe(trendzConfig => {
  console.log('Save Trendz Config:', trendzConfig);
});
```

**5. getTrendzSyncResult**

```javascript
trendzService.getTrendzSyncResult().subscribe(trendzSyncResult => {
  console.log('Get Trendz Sync Result:', trendzSyncResult);
});
```

**6. connectToTrendz**

```javascript
trendzService.connectToTrendz().subscribe(connectToTrendz => {
  console.log('Connect To Trendz:', connectToTrendz);
});
```

---

### **TRENDZ SETTINGS SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const trendzSettingsService = $injector.get(self.ctx.servicesMap.get('trendzSettingsService'));
```

**1. getTrendzSettings**

```javascript
trendzSettingsService.getTrendzSettings().subscribe(trendzSettings => {
  console.log('Get Trendz Settings:', trendzSettings);
});
```

**2. saveTrendzSettings**

```javascript
trendzSettingsService.saveTrendzSettings('your-trendzsettings-value').subscribe(trendzSettings => {
  console.log('Save Trendz Settings:', trendzSettings);
});
```

---

### **TWO FACTOR AUTHENTICATION SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const twoFactorAuthenticationService = $injector.get(self.ctx.servicesMap.get('twoFactorAuthenticationService'));
```

**1. getTwoFaSettings**

```javascript
twoFactorAuthenticationService.getTwoFaSettings().subscribe(twoFaSettings => {
  console.log('Get Two Fa Settings:', twoFaSettings);
});
```

**2. saveTwoFaSettings**

```javascript
twoFactorAuthenticationService.saveTwoFaSettings('your-settings-value').subscribe(twoFaSettings => {
  console.log('Save Two Fa Settings:', twoFaSettings);
});
```

**3. getAvailableTwoFaProviders**

```javascript
twoFactorAuthenticationService.getAvailableTwoFaProviders().subscribe(availableTwoFaProviders => {
  console.log('Get Available Two Fa Providers:', availableTwoFaProviders);
});
```

**4. generateTwoFaAccountConfig**

```javascript
twoFactorAuthenticationService.generateTwoFaAccountConfig('your-providertype-value').subscribe(twoFaAccountConfig => {
  console.log('Generate Two Fa Account Config:', twoFaAccountConfig);
});
```

**5. getAccountTwoFaSettings**

```javascript
twoFactorAuthenticationService.getAccountTwoFaSettings().subscribe(accountTwoFaSettings => {
  console.log('Get Account Two Fa Settings:', accountTwoFaSettings);
});
```

**6. updateTwoFaAccountConfig**

```javascript
twoFactorAuthenticationService.updateTwoFaAccountConfig('your-providertype-value', true).subscribe(twoFaAccountConfig => {
  console.log('Update Two Fa Account Config:', twoFaAccountConfig);
});
```

**7. submitTwoFaAccountConfig**

```javascript
twoFactorAuthenticationService.submitTwoFaAccountConfig('your-authconfig-value').subscribe(submitTwoFaAccountConfig => {
  console.log('Submit Two Fa Account Config:', submitTwoFaAccountConfig);
});
```

**8. verifyAndSaveTwoFaAccountConfig**

```javascript
twoFactorAuthenticationService.verifyAndSaveTwoFaAccountConfig('your-authconfig-value', 0).subscribe(verifyAndSaveTwoFaAccountConfig => {
  console.log('Verify And Save Two Fa Account Config:', verifyAndSaveTwoFaAccountConfig);
});
```

**9. deleteTwoFaAccountConfig**

```javascript
twoFactorAuthenticationService.deleteTwoFaAccountConfig('your-providertype-value').subscribe(twoFaAccountConfig => {
  console.log('Delete Two Fa Account Config:', twoFaAccountConfig);
});
```

---

### **UI SETTINGS SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const uiSettingsService = $injector.get(self.ctx.servicesMap.get('uiSettingsService'));
```

**1. getHelpBaseUrl**

```javascript
uiSettingsService.getHelpBaseUrl().subscribe(helpBaseUrl => {
  console.log('Get Help Base Url:', helpBaseUrl);
});
```

---

### **USAGE INFO SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const usageInfoService = $injector.get(self.ctx.servicesMap.get('usageInfoService'));
```

**1. getUsageInfo**

```javascript
usageInfoService.getUsageInfo().subscribe(usageInfo => {
  console.log('Get Usage Info:', usageInfo);
});
```

---

### **USER PERMISSIONS SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const userPermissionsService = $injector.get(self.ctx.servicesMap.get('userPermissionsService'));
```

**1. loadPermissionsInfo**

```javascript
userPermissionsService.loadPermissionsInfo().subscribe(loadPermissionsInfo => {
  console.log('Load Permissions Info:', loadPermissionsInfo);
});
```

**2. hasEntityPermission**

```javascript
userPermissionsService.hasEntityPermission('your-entity-id', 'your-operation-value').subscribe(hasEntityPermission => {
  console.log('Has Entity Permission:', hasEntityPermission);
});
```

**3. getOperationsByResource**

```javascript
userPermissionsService.getOperationsByResource('your-resource-value').subscribe(operationsByResource => {
  console.log('Get Operations By Resource:', operationsByResource);
});
```

**4. getAllowedGroupRoleOperations**

```javascript
userPermissionsService.getAllowedGroupRoleOperations().subscribe(allowedGroupRoleOperations => {
  console.log('Get Allowed Group Role Operations:', allowedGroupRoleOperations);
});
```

**5. getAllowedResources**

```javascript
userPermissionsService.getAllowedResources().subscribe(allowedResources => {
  console.log('Get Allowed Resources:', allowedResources);
});
```

**6. hasReadGroupsPermission**

```javascript
userPermissionsService.hasReadGroupsPermission('your-entitytype-value').subscribe(hasReadGroupsPermission => {
  console.log('Has Read Groups Permission:', hasReadGroupsPermission);
});
```

**7. hasGenericReadGroupsPermission**

```javascript
userPermissionsService.hasGenericReadGroupsPermission('your-entitytype-value').subscribe(hasGenericReadGroupsPermission => {
  console.log('Has Generic Read Groups Permission:', hasGenericReadGroupsPermission);
});
```

**8. hasSharedReadGroupsPermission**

```javascript
userPermissionsService.hasSharedReadGroupsPermission('your-entitytype-value').subscribe(hasSharedReadGroupsPermission => {
  console.log('Has Shared Read Groups Permission:', hasSharedReadGroupsPermission);
});
```

**9. hasReadGenericPermission**

```javascript
userPermissionsService.hasReadGenericPermission('your-resource-value').subscribe(hasReadGenericPermission => {
  console.log('Has Read Generic Permission:', hasReadGenericPermission);
});
```

**10. hasGenericPermission**

```javascript
userPermissionsService.hasGenericPermission('your-resource-value', 'your-operation-value').subscribe(hasGenericPermission => {
  console.log('Has Generic Permission:', hasGenericPermission);
});
```

**11. isAiEnabled**

```javascript
userPermissionsService.isAiEnabled().subscribe(isAiEnabled => {
  console.log('Is Ai Enabled:', isAiEnabled);
});
```

**12. isResourceAllowed**

```javascript
userPermissionsService.isResourceAllowed('your-resource-value').subscribe(isResourceAllowed => {
  console.log('Is Resource Allowed:', isResourceAllowed);
});
```

**13. hasGenericPermissionByEntityGroupType**

```javascript
userPermissionsService.hasGenericPermissionByEntityGroupType('your-operation-value', 'your-grouptype-value').subscribe(hasGenericPermissionByEntityGroupType => {
  console.log('Has Generic Permission By Entity Group Type:', hasGenericPermissionByEntityGroupType);
});
```

**14. hasGenericEntityGroupTypePermission**

```javascript
userPermissionsService.hasGenericEntityGroupTypePermission('your-operation-value', 'your-grouptype-value').subscribe(hasGenericEntityGroupTypePermission => {
  console.log('Has Generic Entity Group Type Permission:', hasGenericEntityGroupTypePermission);
});
```

**15. hasGenericEntityGroupPermission**

```javascript
userPermissionsService.hasGenericEntityGroupPermission('your-operation-value', 'your-entitygroup-value').subscribe(hasGenericEntityGroupPermission => {
  console.log('Has Generic Entity Group Permission:', hasGenericEntityGroupPermission);
});
```

**16. hasEntityGroupPermission**

```javascript
userPermissionsService.hasEntityGroupPermission('your-operation-value', 'your-entitygroup-value').subscribe(hasEntityGroupPermission => {
  console.log('Has Entity Group Permission:', hasEntityGroupPermission);
});
```

**17. hasGroupEntityPermission**

```javascript
userPermissionsService.hasGroupEntityPermission('your-operation-value', 'your-entitygroup-value').subscribe(hasGroupEntityPermission => {
  console.log('Has Group Entity Permission:', hasGroupEntityPermission);
});
```

**18. isOwnedGroup**

```javascript
userPermissionsService.isOwnedGroup('your-entitygroup-value').subscribe(isOwnedGroup => {
  console.log('Is Owned Group:', isOwnedGroup);
});
```

**19. getUserOwnerId**

```javascript
userPermissionsService.getUserOwnerId().subscribe(userOwnerId => {
  console.log('Get User Owner Id:', userOwnerId);
});
```

**20. isDirectOwner**

```javascript
userPermissionsService.isDirectOwner('your-owner-id').subscribe(isDirectOwner => {
  console.log('Is Direct Owner:', isDirectOwner);
});
```

**21. hasEntityTypeOperationPermission**

```javascript
userPermissionsService.hasEntityTypeOperationPermission('your-entitytype-value', 'your-operation-value', 'your-entitygroup-value').subscribe(hasEntityTypeOperationPermission => {
  console.log('Has Entity Type Operation Permission:', hasEntityTypeOperationPermission);
});
```

**22. hasResourcesGenericPermission**

```javascript
userPermissionsService.hasResourcesGenericPermission('your-resource-value', 'your-operation-value').subscribe(hasResourcesGenericPermission => {
  console.log('Has Resources Generic Permission:', hasResourcesGenericPermission);
});
```

**23. hasGenericResourcesPermission**

```javascript
userPermissionsService.hasGenericResourcesPermission('your-resources-value', 'your-operation-value').subscribe(hasGenericResourcesPermission => {
  console.log('Has Generic Resources Permission:', hasGenericResourcesPermission);
});
```

**24. hasGenericOperationsPermission**

```javascript
userPermissionsService.hasGenericOperationsPermission('your-resource-value', 'your-operations-value').subscribe(hasGenericOperationsPermission => {
  console.log('Has Generic Operations Permission:', hasGenericOperationsPermission);
});
```

**25. hasGenericAllPermission**

```javascript
userPermissionsService.hasGenericAllPermission('your-resource-value', 'your-operation-value').subscribe(hasGenericAllPermission => {
  console.log('Has Generic All Permission:', hasGenericAllPermission);
});
```

**26. hasGenericResourcePermission**

```javascript
userPermissionsService.hasGenericResourcePermission('your-resource-value', 'your-operation-value').subscribe(hasGenericResourcePermission => {
  console.log('Has Generic Resource Permission:', hasGenericResourcePermission);
});
```

**27. checkOperation**

```javascript
userPermissionsService.checkOperation('your-operations-value', 'your-operation-value').subscribe(operation => {
  console.log('Check Operation:', operation);
});
```

**28. checkEntityGroupPermission**

```javascript
userPermissionsService.checkEntityGroupPermission('your-operation-value', 'your-entitygroup-value', true).subscribe(entityGroupPermission => {
  console.log('Check Entity Group Permission:', entityGroupPermission);
});
```

**29. hasGroupPermissions**

```javascript
userPermissionsService.hasGroupPermissions('your-entitygroup-value', 'your-operation-value', true).subscribe(hasGroupPermissions => {
  console.log('Has Group Permissions:', hasGroupPermissions);
});
```

**30. isCurrentUserOwner**

```javascript
userPermissionsService.isCurrentUserOwner('your-entitygroup-value').subscribe(isCurrentUserOwner => {
  console.log('Is Current User Owner:', isCurrentUserOwner);
});
```

**31. containsId**

```javascript
userPermissionsService.containsId('your-idsarray-value', 'your--id').subscribe(containsId => {
  console.log('Contains Id:', containsId);
});
```

**32. idsEqual**

```javascript
userPermissionsService.idsEqual('your-id1-value', 'your-id2-value').subscribe(idsEqual => {
  console.log('Ids Equal:', idsEqual);
});
```

---

### **USER SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const userService = $injector.get(self.ctx.servicesMap.get('userService'));

// Alternative: Direct context access
const userService = self.ctx.userService;
```

**1. getTenantAdmins**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.userService.getTenantAdmins('your-tenant-id', pageLink).subscribe(admins => {
  console.log('Get Tenant Admins:', admins);
});
```

**2. getCustomerUsers**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.userService.getCustomerUsers('your-customer-id', pageLink).subscribe(users => {
  console.log('Get Customer Users:', users);
});
```

**3. getAllCustomerUsers**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.userService.getAllCustomerUsers(pageLink).subscribe(allCustomerUsers => {
  console.log('Get All Customer Users:', allCustomerUsers);
});
```

**4. getUsersForAssign**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.userService.getUsersForAssign('your-alarm-id', pageLink).subscribe(usersForAssign => {
  console.log('Get Users For Assign:', usersForAssign);
});
```

**5. getUser**

```javascript
self.ctx.userService.getUser('your-user-id').subscribe(user => {
  console.log('Get User:', user);
});
```

**6. getUserInfo**

```javascript
self.ctx.userService.getUserInfo('your-user-id').subscribe(info => {
  console.log('Get User Info:', info);
});
```

**7. getUsers** (!!CE VERSION!!)

```javascript
self.ctx.userService.getUsers('your-userids-value').subscribe(users => {
  console.log('Get Users:', users);
});
```

**8. getUserUsers**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.userService.getUserUsers(pageLink).subscribe(userUsers => {
  console.log('Get User Users:', userUsers);
});
```

**9. getAllUserInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.userService.getAllUserInfos(true, pageLink).subscribe(allUserInfos => {
  console.log('Get All User Infos:', allUserInfos);
});
```

**10. getCustomerUserInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.userService.getCustomerUserInfos(true, 'your-customer-id', pageLink).subscribe(customerUserInfos => {
  console.log('Get Customer User Infos:', customerUserInfos);
});
```

**11. saveUser**

```javascript
self.ctx.userService.saveUser('your-user-value', 'your-email@example.com', 'your-entitygroupids-value').subscribe(user => {
  console.log('Save User:', user);
});
```

**12. getActivationLink**

```javascript
self.ctx.userService.getActivationLink('your-user-id').subscribe(activationLink => {
  console.log('Get Activation Link:', activationLink);
});
```

**13. getActivationLinkInfo**

```javascript
self.ctx.userService.getActivationLinkInfo('your-user-id').subscribe(activationLinkInfo => {
  console.log('Get Activation Link Info:', activationLinkInfo);
});
```

**14. setUserCredentialsEnabled**

```javascript
self.ctx.userService.setUserCredentialsEnabled('your-user-id', true).subscribe(userCredentialsEnabled => {
  console.log('Set User Credentials Enabled:', userCredentialsEnabled);
});
```

**15. findUsersByQuery**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.userService.findUsersByQuery(pageLink).subscribe(usersByQuery => {
  console.log('Find Users By Query:', usersByQuery);
});
```

---

### **USER SETTINGS SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const userSettingsService = $injector.get(self.ctx.servicesMap.get('userSettingsService'));

// Alternative: Direct context access
const userSettingsService = self.ctx.userSettingsService;
```

**1. loadUserSettings**

```javascript
self.ctx.userSettingsService.loadUserSettings().subscribe(loadUserSettings => {
  console.log('Load User Settings:', loadUserSettings);
});
```

**2. saveUserSettings**

```javascript
self.ctx.userSettingsService.saveUserSettings('your-usersettings-value').subscribe(userSettings => {
  console.log('Save User Settings:', userSettings);
});
```

**3. putUserSettings**

```javascript
self.ctx.userSettingsService.putUserSettings('your-usersettingsdata-value').subscribe(result => {
  console.log('Put User Settings:', result);
});
```

**4. getDocumentationLinks**

```javascript
self.ctx.userSettingsService.getDocumentationLinks().subscribe(documentationLinks => {
  console.log('Get Documentation Links:', documentationLinks);
});
```

**5. updateDocumentationLinks**

```javascript
self.ctx.userSettingsService.updateDocumentationLinks('your-documentationlinks-value').subscribe(result => {
  console.log('Update Documentation Links:', result);
});
```

**6. getQuickLinks**

```javascript
self.ctx.userSettingsService.getQuickLinks().subscribe(quickLinks => {
  console.log('Get Quick Links:', quickLinks);
});
```

**7. updateQuickLinks**

```javascript
self.ctx.userSettingsService.updateQuickLinks('your-quicklinks-value').subscribe(result => {
  console.log('Update Quick Links:', result);
});
```

**8. getGettingStarted**

```javascript
self.ctx.userSettingsService.getGettingStarted().subscribe(gettingStarted => {
  console.log('Get Getting Started:', gettingStarted);
});
```

**9. updateGettingStarted**

```javascript
self.ctx.userSettingsService.updateGettingStarted('your-gettingstarted-value').subscribe(result => {
  console.log('Update Getting Started:', result);
});
```

**10. getUserDashboardsInfo**

```javascript
self.ctx.userSettingsService.getUserDashboardsInfo().subscribe(userDashboardsInfo => {
  console.log('Get User Dashboards Info:', userDashboardsInfo);
});
```

**11. reportUserDashboardAction**

```javascript
self.ctx.userSettingsService.reportUserDashboardAction('your-dashboard-id', 'your-action-value').subscribe(reportUserDashboardAction => {
  console.log('Report User Dashboard Action:', reportUserDashboardAction);
});
```

---

### **WHITE LABELING SERVICE**

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

---

### **WIDGET SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const widgetService = $injector.get(self.ctx.servicesMap.get('widgetService'));
```

**1. getWidgetScopeVariables**

```javascript
widgetService.getWidgetScopeVariables().subscribe(widgetScopeVariables => {
  console.log('Get Widget Scope Variables:', widgetScopeVariables);
});
```

**2. getAllWidgetsBundles**

```javascript
widgetService.getAllWidgetsBundles().subscribe(allWidgetsBundles => {
  console.log('Get All Widgets Bundles:', allWidgetsBundles);
});
```

**3. getSystemWidgetsBundles**

```javascript
widgetService.getSystemWidgetsBundles().subscribe(systemWidgetsBundles => {
  console.log('Get System Widgets Bundles:', systemWidgetsBundles);
});
```

**4. getTenantWidgetsBundles**

```javascript
widgetService.getTenantWidgetsBundles().subscribe(tenantWidgetsBundles => {
  console.log('Get Tenant Widgets Bundles:', tenantWidgetsBundles);
});
```

**5. getWidgetBundles**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
widgetService.getWidgetBundles(pageLink).subscribe(widgetBundles => {
  console.log('Get Widget Bundles:', widgetBundles);
});
```

**6. getWidgetsBundle**

```javascript
widgetService.getWidgetsBundle('your-widgetsbundle-id').subscribe(widgetsBundle => {
  console.log('Get Widgets Bundle:', widgetsBundle);
});
```

**7. exportWidgetsBundle**

```javascript
widgetService.exportWidgetsBundle('your-widgetsbundle-id').subscribe(widgetsBundle => {
  console.log('Export Widgets Bundle:', widgetsBundle);
});
```

**8. getWidgetsBundlesByIds**

```javascript
widgetService.getWidgetsBundlesByIds('your-widgetsbundleids-value').subscribe(widgetsBundlesByIds => {
  console.log('Get Widgets Bundles By Ids:', widgetsBundlesByIds);
});
```

**9. saveWidgetsBundle**

```javascript
widgetService.saveWidgetsBundle('your-widgetsbundle-value').subscribe(widgetsBundle => {
  console.log('Save Widgets Bundle:', widgetsBundle);
});
```

**10. updateWidgetsBundleWidgetTypes**

```javascript
widgetService.updateWidgetsBundleWidgetTypes('your-widgetsbundle-id', 'your-widgettypeids-value').subscribe(result => {
  console.log('Update Widgets Bundle Widget Types:', result);
});
```

**11. updateWidgetsBundleWidgetFqns**

```javascript
widgetService.updateWidgetsBundleWidgetFqns('your-widgetsbundle-id', 'your-widgettypefqns-value').subscribe(result => {
  console.log('Update Widgets Bundle Widget Fqns:', result);
});
```

**12. getBundleWidgetTypes**

```javascript
widgetService.getBundleWidgetTypes('your-widgetsbundle-id').subscribe(bundleWidgetTypes => {
  console.log('Get Bundle Widget Types:', bundleWidgetTypes);
});
```

**13. exportBundleWidgetTypesDetails**

```javascript
widgetService.exportBundleWidgetTypesDetails('your-widgetsbundle-id').subscribe(bundleWidgetTypesDetails => {
  console.log('Export Bundle Widget Types Details:', bundleWidgetTypesDetails);
});
```

**14. getBundleWidgetTypeFqns**

```javascript
widgetService.getBundleWidgetTypeFqns('your-widgetsbundle-id').subscribe(bundleWidgetTypeFqns => {
  console.log('Get Bundle Widget Type Fqns:', bundleWidgetTypeFqns);
});
```

**15. getBundleWidgetTypeInfosList**

```javascript
widgetService.getBundleWidgetTypeInfosList('your-widgetsbundle-id').subscribe(bundleWidgetTypeInfosList => {
  console.log('Get Bundle Widget Type Infos List:', bundleWidgetTypeInfosList);
});
```

**16. getBundleWidgetTypeInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
widgetService.getBundleWidgetTypeInfos(pageLink, 'your-widgetsbundle-id', 'your-widgettypes-value').subscribe(bundleWidgetTypeInfos => {
  console.log('Get Bundle Widget Type Infos:', bundleWidgetTypeInfos);
});
```

**17. getWidgetType**

```javascript
widgetService.getWidgetType('your-fullfqn-value').subscribe(widgetType => {
  console.log('Get Widget Type:', widgetType);
});
```

**18. saveWidgetTypeDetails**

```javascript
widgetService.saveWidgetTypeDetails('your-widgetinfo-value', 'your--id', 0, 0).subscribe(widgetTypeDetails => {
  console.log('Save Widget Type Details:', widgetTypeDetails);
});
```

**19. saveImportedWidgetTypeDetails**

```javascript
widgetService.saveImportedWidgetTypeDetails('your-widgettypedetails-value').subscribe(importedWidgetTypeDetails => {
  console.log('Save Imported Widget Type Details:', importedWidgetTypeDetails);
});
```

**20. getWidgetTypeById**

```javascript
widgetService.getWidgetTypeById('your-widgettype-id').subscribe(widgetTypeById => {
  console.log('Get Widget Type By Id:', widgetTypeById);
});
```

**21. exportWidgetType**

```javascript
widgetService.exportWidgetType('your-widgettype-id').subscribe(widgetType => {
  console.log('Export Widget Type:', widgetType);
});
```

**22. getWidgetTypeInfoById**

```javascript
widgetService.getWidgetTypeInfoById('your-widgettype-id').subscribe(widgetTypeInfoById => {
  console.log('Get Widget Type Info By Id:', widgetTypeInfoById);
});
```

**23. saveWidgetType**

```javascript
widgetService.saveWidgetType('your-widgettypedetails-value').subscribe(widgetType => {
  console.log('Save Widget Type:', widgetType);
});
```

**24. getWidgetTypes**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
widgetService.getWidgetTypes(pageLink, 'your-widgettypes-value').subscribe(widgetTypes => {
  console.log('Get Widget Types:', widgetTypes);
});
```

**25. getWidgetTemplate**

```javascript
widgetService.getWidgetTemplate('your-widgettypeparam-value').subscribe(widgetTemplate => {
  console.log('Get Widget Template:', widgetTemplate);
});
```

**26. getWidgetInfoFromCache**

```javascript
widgetService.getWidgetInfoFromCache('your-fullfqn-value').subscribe(widgetInfoFromCache => {
  console.log('Get Widget Info From Cache:', widgetInfoFromCache);
});
```

**27. getBasicWidgetSettingsComponentBySelector**

```javascript
widgetService.getBasicWidgetSettingsComponentBySelector('your-selector-value').subscribe(basicWidgetSettingsComponentBySelector => {
  console.log('Get Basic Widget Settings Component By Selector:', basicWidgetSettingsComponentBySelector);
});
```

**28. getWidgetSettingsComponentTypeBySelector**

```javascript
widgetService.getWidgetSettingsComponentTypeBySelector('your-selector-value').subscribe(widgetSettingsComponentTypeBySelector => {
  console.log('Get Widget Settings Component Type By Selector:', widgetSettingsComponentTypeBySelector);
});
```

**29. widgetTypeUpdated**

```javascript
widgetService.widgetTypeUpdated('your-updatedwidgettype-value').subscribe(widgetTypeUpdated => {
  console.log('Widget Type Updated:', widgetTypeUpdated);
});
```

**30. loadWidgetsBundleCache**

```javascript
widgetService.loadWidgetsBundleCache().subscribe(loadWidgetsBundleCache => {
  console.log('Load Widgets Bundle Cache:', loadWidgetsBundleCache);
});
```

---
