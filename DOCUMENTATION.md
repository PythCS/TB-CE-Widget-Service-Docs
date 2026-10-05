# ThingsBoard CE Widget Services

Generated from ThingsBoard CE commit `79bb2b0a659d` (65 services, 807 methods).

## Using Services in Widgets/Custom Actions

Using services in custom actions is slightly different than in custom widget development.

In custom actions you use `widgetContext` — in widget development you use `self.ctx`. Same services, different context variable.

Example Custom Action:

```javascript
const $injector = widgetContext.$scope.$injector;
const userService = $injector.get(widgetContext.servicesMap.get('userService'));
```

Example Widget Development:

```javascript
const $injector = self.ctx.$scope.$injector;
const userService = $injector.get(self.ctx.servicesMap.get('userService'));
```

## Using Page Links

Page links are how ThingsBoard handles pagination. Instead of asking the server for
1000+ entities in one go, you request a page at a time — this keeps the server responsive.

You create one with `self.ctx.pageLink(pageSize, page, searchText, sortProperty, sortOrder)`:

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
//                       pageSize: 10, page: 0, text filter, sort field, sort direction
deviceService.getTenantDevices(pageLink).subscribe(devices => {
  console.log('List of Devices:', devices);
});
```

`devices.data` holds the page items, `devices.hasNext` tells you whether to request the
next page (bump the page number and call again).


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
- [O AUTH2 SERVICE](#o-auth2-service)
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


### **ADMIN SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const adminService = $injector.get(self.ctx.servicesMap.get('adminService'));
```

**1. sendTestMail**

```javascript
const $injector = self.ctx.$scope.$injector;
const adminService = $injector.get(self.ctx.servicesMap.get('adminService'));
const adminSettings = {  // AdminSettings<MailServerSettings> object
  // ... set the fields you need
};
adminService.sendTestMail(adminSettings).subscribe(sendTestMail => {
  console.log('Send Test Mail:', sendTestMail);
});
```

**2. sendTestSms**

```javascript
const $injector = self.ctx.$scope.$injector;
const adminService = $injector.get(self.ctx.servicesMap.get('adminService'));
const testSmsRequest = {  // TestSmsRequest object
  // ... set the fields you need
};
adminService.sendTestSms(testSmsRequest).subscribe(sendTestSms => {
  console.log('Send Test Sms:', sendTestSms);
});
```

**3. getSecuritySettings**

```javascript
const $injector = self.ctx.$scope.$injector;
const adminService = $injector.get(self.ctx.servicesMap.get('adminService'));
adminService.getSecuritySettings().subscribe(securitySettings => {
  console.log('Get Security Settings:', securitySettings);
});
```

**4. saveSecuritySettings**

```javascript
const $injector = self.ctx.$scope.$injector;
const adminService = $injector.get(self.ctx.servicesMap.get('adminService'));
const securitySettings = {  // SecuritySettings object
  // ... set the fields you need
};
adminService.saveSecuritySettings(securitySettings).subscribe(savedSecuritySettings => {
  console.log('Saved Security Settings:', savedSecuritySettings);
});
```

**5. getJwtSettings**

```javascript
const $injector = self.ctx.$scope.$injector;
const adminService = $injector.get(self.ctx.servicesMap.get('adminService'));
adminService.getJwtSettings().subscribe(jwtSettings => {
  console.log('Get Jwt Settings:', jwtSettings);
});
```

**6. saveJwtSettings**

```javascript
const $injector = self.ctx.$scope.$injector;
const adminService = $injector.get(self.ctx.servicesMap.get('adminService'));
const jwtSettings = {  // JwtSettings object
  // ... set the fields you need
};
adminService.saveJwtSettings(jwtSettings).subscribe(savedJwtSettings => {
  console.log('Saved Jwt Settings:', savedJwtSettings);
});
```

**7. getRepositorySettings**

```javascript
const $injector = self.ctx.$scope.$injector;
const adminService = $injector.get(self.ctx.servicesMap.get('adminService'));
adminService.getRepositorySettings().subscribe(repositorySettings => {
  console.log('Get Repository Settings:', repositorySettings);
});
```

**8. saveRepositorySettings**

```javascript
const $injector = self.ctx.$scope.$injector;
const adminService = $injector.get(self.ctx.servicesMap.get('adminService'));
const repositorySettings = {  // RepositorySettings object
  // ... set the fields you need
};
adminService.saveRepositorySettings(repositorySettings).subscribe(savedRepositorySettings => {
  console.log('Saved Repository Settings:', savedRepositorySettings);
});
```

**9. checkRepositoryAccess**

```javascript
const $injector = self.ctx.$scope.$injector;
const adminService = $injector.get(self.ctx.servicesMap.get('adminService'));
const repositorySettings = {  // RepositorySettings object
  // ... set the fields you need
};
adminService.checkRepositoryAccess(repositorySettings).subscribe(checkRepositoryAccess => {
  console.log('Check Repository Access:', checkRepositoryAccess);
});
```

**10. getRepositorySettingsInfo**

```javascript
const $injector = self.ctx.$scope.$injector;
const adminService = $injector.get(self.ctx.servicesMap.get('adminService'));
adminService.getRepositorySettingsInfo().subscribe(repositorySettingsInfo => {
  console.log('Get Repository Settings Info:', repositorySettingsInfo);
});
```

**11. getAutoCommitSettings**

```javascript
const $injector = self.ctx.$scope.$injector;
const adminService = $injector.get(self.ctx.servicesMap.get('adminService'));
adminService.getAutoCommitSettings().subscribe(autoCommitSettings => {
  console.log('Get Auto Commit Settings:', autoCommitSettings);
});
```

**12. autoCommitSettingsExists**

```javascript
const $injector = self.ctx.$scope.$injector;
const adminService = $injector.get(self.ctx.servicesMap.get('adminService'));
adminService.autoCommitSettingsExists().subscribe(autoCommitSettingsExists => {
  console.log('Auto Commit Settings Exists:', autoCommitSettingsExists);
});
```

**13. saveAutoCommitSettings**

```javascript
const $injector = self.ctx.$scope.$injector;
const adminService = $injector.get(self.ctx.servicesMap.get('adminService'));
const autoCommitSettings = {  // AutoCommitSettings object
  // ... set the fields you need
};
adminService.saveAutoCommitSettings(autoCommitSettings).subscribe(savedAutoCommitSettings => {
  console.log('Saved Auto Commit Settings:', savedAutoCommitSettings);
});
```

**14. checkUpdates**

```javascript
const $injector = self.ctx.$scope.$injector;
const adminService = $injector.get(self.ctx.servicesMap.get('adminService'));
adminService.checkUpdates().subscribe(checkUpdates => {
  console.log('Check Updates:', checkUpdates);
});
```

**15. getFeaturesInfo**

```javascript
const $injector = self.ctx.$scope.$injector;
const adminService = $injector.get(self.ctx.servicesMap.get('adminService'));
adminService.getFeaturesInfo().subscribe(featuresInfo => {
  console.log('Get Features Info:', featuresInfo);
});
```

**16. getLicenseUsageInfo**

```javascript
const $injector = self.ctx.$scope.$injector;
const adminService = $injector.get(self.ctx.servicesMap.get('adminService'));
adminService.getLicenseUsageInfo().subscribe(licenseUsageInfo => {
  console.log('Get License Usage Info:', licenseUsageInfo);
});
```

**17. getSubscriptionInfo**

```javascript
const $injector = self.ctx.$scope.$injector;
const adminService = $injector.get(self.ctx.servicesMap.get('adminService'));
adminService.getSubscriptionInfo().subscribe(subscriptionInfo => {
  console.log('Get Subscription Info:', subscriptionInfo);
});
```

**18. refreshLicense**

```javascript
const $injector = self.ctx.$scope.$injector;
const adminService = $injector.get(self.ctx.servicesMap.get('adminService'));
adminService.refreshLicense().subscribe(refreshLicense => {
  console.log('Refresh License:', refreshLicense);
});
```

**19. getLoginProcessingUrl**

```javascript
const $injector = self.ctx.$scope.$injector;
const adminService = $injector.get(self.ctx.servicesMap.get('adminService'));
adminService.getLoginProcessingUrl().subscribe(loginProcessingUrl => {
  console.log('Get Login Processing Url:', loginProcessingUrl);
});
```

**20. generateAccessToken**

```javascript
const $injector = self.ctx.$scope.$injector;
const adminService = $injector.get(self.ctx.servicesMap.get('adminService'));
adminService.generateAccessToken().subscribe(generateAccessToken => {
  console.log('Generate Access Token:', generateAccessToken);
});
```

**21. getMailConfigTemplate**

```javascript
const $injector = self.ctx.$scope.$injector;
const adminService = $injector.get(self.ctx.servicesMap.get('adminService'));
adminService.getMailConfigTemplate().subscribe(mailConfigTemplates => {
  console.log('List of Mail Config Templates:', mailConfigTemplates);
});
```

### **AGENT SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
```

**1. getAgentById**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const agentId = 'your-agent-id';
agentService.getAgentById(agentId).subscribe(agentBy => {
  console.log('Get Agent By Id:', agentBy);
});
```

**2. getAgentInfoById**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const agentId = 'your-agent-id';
agentService.getAgentInfoById(agentId).subscribe(agentInfoBy => {
  console.log('Get Agent Info By Id:', agentInfoBy);
});
```

**3. getAgentInfosByIds**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const agentIds = ['your-agent-i-1', 'your-agent-i-2'];
agentService.getAgentInfosByIds(agentIds).subscribe(agentInfosBys => {
  console.log('Get Agent Infos By Ids:', agentInfosBys);
});
```

**4. getAgentInstallInstructions**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const agentId = 'your-agent-id';
const method = 'value';
agentService.getAgentInstallInstructions(agentId, method).subscribe(agentInstallInstructions => {
  console.log('Get Agent Install Instructions:', agentInstallInstructions);
});
```

**5. getAgentProvisionInstructions**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const agentProfileId = 'your-agent-profile-id';
const method = 'value';
agentService.getAgentProvisionInstructions(agentProfileId, method).subscribe(agentProvisionInstructions => {
  console.log('Get Agent Provision Instructions:', agentProvisionInstructions);
});
```

**6. upgradeAgent**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const agentId = 'your-agent-id';
const imageRef = 'your-image-ref';
agentService.upgradeAgent(agentId, imageRef).subscribe(upgradeAgent => {
  console.log('Upgrade Agent:', upgradeAgent);
});
```

**7. saveAgent**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const agent = {  // Agent object
  // ... set the fields you need
};
const entityGroupIds = ['your-entity-group-i-1', 'your-entity-group-i-2'];
agentService.saveAgent(agent, entityGroupIds).subscribe(savedAgent => {
  console.log('Saved Agent:', savedAgent);
});
```

**8. join**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const result = agentService.join();
console.log('Result:', result);
```

**9. deleteAgent**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const agentId = 'your-agent-id';
agentService.deleteAgent(agentId).subscribe(result => {
  console.log('Delete Agent result:', result);
});
```

**10. getTenantAgentInfos**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
agentService.getTenantAgentInfos(pageLink).subscribe(tenantAgentInfos => {
  console.log('List of Tenant Agent Infos:', tenantAgentInfos);
});
```

**11. getCustomerAgentInfos**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const customerId = 'your-customer-id';
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
agentService.getCustomerAgentInfos(customerId, pageLink).subscribe(customerAgentInfos => {
  console.log('List of Customer Agent Infos:', customerAgentInfos);
});
```

**12. getAgentProfileById**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const agentProfileId = 'your-agent-profile-id';
agentService.getAgentProfileById(agentProfileId).subscribe(agentProfileBy => {
  console.log('Get Agent Profile By Id:', agentProfileBy);
});
```

**13. getAgentProfileInfoById**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const agentProfileId = 'your-agent-profile-id';
agentService.getAgentProfileInfoById(agentProfileId).subscribe(agentProfileInfoBy => {
  console.log('Get Agent Profile Info By Id:', agentProfileInfoBy);
});
```

**14. saveAgentProfile**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const agentProfile = {  // AgentProfile object
  // ... set the fields you need
};
const appProfileIds = ['your-app-profile-i-1', 'your-app-profile-i-2'];
agentService.saveAgentProfile(agentProfile, appProfileIds).subscribe(savedAgentProfile => {
  console.log('Saved Agent Profile:', savedAgentProfile);
});
```

**15. deleteAgentProfile**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const agentProfileId = 'your-agent-profile-id';
agentService.deleteAgentProfile(agentProfileId).subscribe(result => {
  console.log('Delete Agent Profile result:', result);
});
```

**16. setDefaultAgentProfile**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const agentProfileId = 'your-agent-profile-id';
agentService.setDefaultAgentProfile(agentProfileId).subscribe(setDefaultAgentProfile => {
  console.log('Set Default Agent Profile:', setDefaultAgentProfile);
});
```

**17. getDefaultAgentProfileInfo**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
agentService.getDefaultAgentProfileInfo().subscribe(defaultAgentProfileInfo => {
  console.log('Get Default Agent Profile Info:', defaultAgentProfileInfo);
});
```

**18. getTenantAgentProfiles**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
agentService.getTenantAgentProfiles(pageLink).subscribe(tenantAgentProfiles => {
  console.log('List of Tenant Agent Profiles:', tenantAgentProfiles);
});
```

**19. getTenantAgentProfileInfos**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
agentService.getTenantAgentProfileInfos(pageLink).subscribe(tenantAgentProfileInfos => {
  console.log('List of Tenant Agent Profile Infos:', tenantAgentProfileInfos);
});
```

**20. getAgentProfileAppProfileInfos**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const agentProfileId = 'your-agent-profile-id';
agentService.getAgentProfileAppProfileInfos(agentProfileId).subscribe(agentProfileAppProfileInfos => {
  console.log('Get Agent Profile App Profile Infos:', agentProfileAppProfileInfos);
});
```

**21. assignAppProfileToAgentProfile**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const agentProfileId = 'your-agent-profile-id';
const applicationProfileId = 'your-application-profile-id';
agentService.assignAppProfileToAgentProfile(agentProfileId, applicationProfileId).subscribe(assignAppProfileToAgentProfile => {
  console.log('Assign App Profile To Agent Profile:', assignAppProfileToAgentProfile);
});
```

**22. assignAppProfilesToAgentProfile**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const agentProfileId = 'your-agent-profile-id';
const appProfileIds = ['your-app-profile-i-1', 'your-app-profile-i-2'];
agentService.assignAppProfilesToAgentProfile(agentProfileId, appProfileIds).subscribe(assignAppProfilesToAgentProfile => {
  console.log('Assign App Profiles To Agent Profile:', assignAppProfilesToAgentProfile);
});
```

**23. join**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const result = agentService.join();
console.log('Result:', result);
```

**24. setAppProfileRelatesOnAutoDiscovery**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const agentProfileId = 'your-agent-profile-id';
const applicationProfileId = 'your-application-profile-id';
const relate = true;
agentService.setAppProfileRelatesOnAutoDiscovery(agentProfileId, applicationProfileId, relate).subscribe(setAppProfileRelatesOnAutoDiscovery => {
  console.log('Set App Profile Relates On Auto Discovery:', setAppProfileRelatesOnAutoDiscovery);
});
```

**25. previewBulkOperation**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const agentProfileId = 'your-agent-profile-id';
const applicationProfileId = 'your-application-profile-id';
const request = {  // BulkOperationRequest object
  // ... set the fields you need
};
agentService.previewBulkOperation(agentProfileId, applicationProfileId, request).subscribe(previewBulkOperation => {
  console.log('Preview Bulk Operation:', previewBulkOperation);
});
```

**26. bulkOperation**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const agentProfileId = 'your-agent-profile-id';
const applicationProfileId = 'your-application-profile-id';
const request = {  // BulkOperationRequest object
  // ... set the fields you need
};
agentService.bulkOperation(agentProfileId, applicationProfileId, request).subscribe(bulkOperation => {
  console.log('Bulk Operation:', bulkOperation);
});
```

**27. getAgentApplicationInfoById**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const applicationId = 'your-application-id';
agentService.getAgentApplicationInfoById(applicationId).subscribe(agentApplicationInfoBy => {
  console.log('Get Agent Application Info By Id:', agentApplicationInfoBy);
});
```

**28. getAgentApplicationsByAgentId**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const agentId = 'your-agent-id';
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
agentService.getAgentApplicationsByAgentId(agentId, pageLink).subscribe(agentApplicationsByAgents => {
  console.log('List of Agent Applications By Agent Ids:', agentApplicationsByAgents);
});
```

**29. getAgentApplicationByRelatedEntity**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const entityType = 'your-entity-type';
const entityId = 'your-entity-id';
agentService.getAgentApplicationByRelatedEntity(entityType, entityId).subscribe(agentApplicationByRelatedEntity => {
  console.log('Get Agent Application By Related Entity:', agentApplicationByRelatedEntity);
});
```

**30. updateAgentApplication**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const application = {  // AgentApplication object
  // ... set the fields you need
};
agentService.updateAgentApplication(application).subscribe(savedAgentApplication => {
  console.log('Saved Agent Application:', savedAgentApplication);
});
```

**31. installAgentApp**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const request = {  // AgentAppEventRequest object
  // ... set the fields you need
};
agentService.installAgentApp(request).subscribe(installAgentApp => {
  console.log('Install Agent App:', installAgentApp);
});
```

**32. createAgentAppEvent**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const applicationId = 'your-application-id';
const request = {  // AgentAppEventRequest object
  // ... set the fields you need
};
agentService.createAgentAppEvent(applicationId, request).subscribe(createAgentAppEvent => {
  console.log('Create Agent App Event:', createAgentAppEvent);
});
```

**33. cancelAgentAppEvent**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const applicationId = 'your-application-id';
const eventId = 'your-event-id';
agentService.cancelAgentAppEvent(applicationId, eventId).subscribe(cancelAgentAppEvent => {
  console.log('Cancel Agent App Event:', cancelAgentAppEvent);
});
```

**34. getAgentAppEventById**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const eventId = 'your-event-id';
agentService.getAgentAppEventById(eventId).subscribe(agentAppEventBy => {
  console.log('Get Agent App Event By Id:', agentAppEventBy);
});
```

**35. getAgentAppEvents**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const applicationId = 'your-application-id';
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const actionType = 'your-action-type';
const processingStatus = 'your-processing-status';
agentService.getAgentAppEvents(applicationId, pageLink, actionType, processingStatus).subscribe(agentAppEvents => {
  console.log('List of Agent App Events:', agentAppEvents);
});
```

**36. getAgentAppEventsByAgentId**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const agentId = 'your-agent-id';
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
agentService.getAgentAppEventsByAgentId(agentId, pageLink).subscribe(agentAppEventsByAgents => {
  console.log('List of Agent App Events By Agent Ids:', agentAppEventsByAgents);
});
```

**37. getAgentAppEventInfosByAgentId**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const agentId = 'your-agent-id';
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const actionType = 'your-action-type';
const processingStatus = 'your-processing-status';
agentService.getAgentAppEventInfosByAgentId(agentId, pageLink, actionType, processingStatus).subscribe(agentAppEventInfosByAgents => {
  console.log('List of Agent App Event Infos By Agent Ids:', agentAppEventInfosByAgents);
});
```

**38. mergeForPreview**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const templateVersion = 'your-template-version';
const appType = {  // AgentApplicationType object
  // ... set the fields you need
};
const application = {  // AgentApplication object
  // ... set the fields you need
};
const composeType = 'your-compose-type';
const relatedEntityId = {  // EntityId object
  // ... set the fields you need
};
const actionType = {  // AgentAppEventActionType object
  // ... set the fields you need
};
const setHostValues = true;
agentService.mergeForPreview(templateVersion, appType, application, composeType, relatedEntityId, actionType, setHostValues).subscribe(mergeForPreview => {
  console.log('Merge For Preview:', mergeForPreview);
});
```

**39. assignRelatedEntity**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const applicationId = 'your-application-id';
const relatedEntityId = {  // EntityId object
  // ... set the fields you need
};
agentService.assignRelatedEntity(applicationId, relatedEntityId).subscribe(assignRelatedEntity => {
  console.log('Assign Related Entity:', assignRelatedEntity);
});
```

**40. unassignRelatedEntity**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const applicationId = 'your-application-id';
agentService.unassignRelatedEntity(applicationId).subscribe(unassignRelatedEntity => {
  console.log('Unassign Related Entity:', unassignRelatedEntity);
});
```

**41. detachFromProfile**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const applicationId = 'your-application-id';
agentService.detachFromProfile(applicationId).subscribe(detachFromProfile => {
  console.log('Detach From Profile:', detachFromProfile);
});
```

**42. attachToProfile**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const applicationId = 'your-application-id';
const profileId = 'your-profile-id';
agentService.attachToProfile(applicationId, profileId).subscribe(attachToProfile => {
  console.log('Attach To Profile:', attachToProfile);
});
```

**43. getLatestAgentAppTemplate**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const appType = 'your-app-type';
const configType = 'your-config-type';
agentService.getLatestAgentAppTemplate(appType, configType).subscribe(latestAgentAppTemplate => {
  console.log('Get Latest Agent App Template:', latestAgentAppTemplate);
});
```

**44. getAgentAppTemplateByVersion**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const appType = 'your-app-type';
const configType = 'your-config-type';
const version = 'your-version';
agentService.getAgentAppTemplateByVersion(appType, configType, version).subscribe(agentAppTemplateByVersion => {
  console.log('Get Agent App Template By Version:', agentAppTemplateByVersion);
});
```

**45. getAgentAppTemplates**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
agentService.getAgentAppTemplates().subscribe(agentAppTemplates => {
  console.log('Get Agent App Templates:', agentAppTemplates);
});
```

**46. getAgentAppProfilesByAppType**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const appType = 'your-app-type';
agentService.getAgentAppProfilesByAppType(appType).subscribe(agentAppProfilesByAppType => {
  console.log('Get Agent App Profiles By App Type:', agentAppProfilesByAppType);
});
```

**47. getAgentAppTemplatesByAppType**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const appType = 'your-app-type';
const configType = 'value';
agentService.getAgentAppTemplatesByAppType(appType, configType).subscribe(agentAppTemplatesByAppType => {
  console.log('Get Agent App Templates By App Type:', agentAppTemplatesByAppType);
});
```

**48. getAgentAppProfileById**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const profileId = 'your-profile-id';
agentService.getAgentAppProfileById(profileId).subscribe(agentAppProfileBy => {
  console.log('Get Agent App Profile By Id:', agentAppProfileBy);
});
```

**49. getAgentAppProfileInfoById**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const profileId = 'your-profile-id';
agentService.getAgentAppProfileInfoById(profileId).subscribe(agentAppProfileInfoBy => {
  console.log('Get Agent App Profile Info By Id:', agentAppProfileInfoBy);
});
```

**50. saveAgentAppProfile**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const profile = {  // AgentAppProfile object
  // ... set the fields you need
};
agentService.saveAgentAppProfile(profile).subscribe(savedAgentAppProfile => {
  console.log('Saved Agent App Profile:', savedAgentAppProfile);
});
```

**51. deleteAgentAppProfile**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const profileId = 'your-profile-id';
agentService.deleteAgentAppProfile(profileId).subscribe(result => {
  console.log('Delete Agent App Profile result:', result);
});
```

**52. getTenantAgentAppProfiles**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
agentService.getTenantAgentAppProfiles(pageLink).subscribe(tenantAgentAppProfiles => {
  console.log('List of Tenant Agent App Profiles:', tenantAgentAppProfiles);
});
```

**53. getAgentAppProfilesByIds**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const profileIds = ['your-profile-i-1', 'your-profile-i-2'];
agentService.getAgentAppProfilesByIds(profileIds).subscribe(agentAppProfilesBys => {
  console.log('Get Agent App Profiles By Ids:', agentAppProfilesBys);
});
```

**54. materializeAgentAppProfile**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const appType = {  // AgentApplicationType object
  // ... set the fields you need
};
const templateVersion = 'your-template-version';
const composeType = 'your-compose-type';
agentService.materializeAgentAppProfile(appType, templateVersion, composeType).subscribe(materializeAgentAppProfile => {
  console.log('Materialize Agent App Profile:', materializeAgentAppProfile);
});
```

**55. mergeProfileForPreview**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const templateVersion = 'your-template-version';
const profile = {  // AgentAppProfile object
  // ... set the fields you need
};
const composeType = 'your-compose-type';
const actionType = {  // AgentAppEventActionType object
  // ... set the fields you need
};
const setHostValues = true;
agentService.mergeProfileForPreview(templateVersion, profile, composeType, actionType, setHostValues).subscribe(mergeProfileForPreview => {
  console.log('Merge Profile For Preview:', mergeProfileForPreview);
});
```

**56. getAgentAppUnits**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const applicationId = 'your-application-id';
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const type = 'type-value';
agentService.getAgentAppUnits(applicationId, pageLink, type).subscribe(agentAppUnits => {
  console.log('List of Agent App Units:', agentAppUnits);
});
```

**57. getAgentBulkAction**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const bulkActionId = 'your-bulk-action-id';
agentService.getAgentBulkAction(bulkActionId).subscribe(agentBulkAction => {
  console.log('Get Agent Bulk Action:', agentBulkAction);
});
```

**58. getAgentProfileBulkActions**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const agentProfileId = 'your-agent-profile-id';
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
agentService.getAgentProfileBulkActions(agentProfileId, pageLink).subscribe(agentProfileBulkActions => {
  console.log('List of Agent Profile Bulk Actions:', agentProfileBulkActions);
});
```

**59. getAgentProfileAppProfileBulkActions**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const agentProfileId = 'your-agent-profile-id';
const applicationProfileId = 'your-application-profile-id';
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
agentService.getAgentProfileAppProfileBulkActions(agentProfileId, applicationProfileId, pageLink).subscribe(agentProfileAppProfileBulkActions => {
  console.log('List of Agent Profile App Profile Bulk Actions:', agentProfileAppProfileBulkActions);
});
```

**60. getAgentBulkActionEventStats**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const bulkActionId = 'your-bulk-action-id';
agentService.getAgentBulkActionEventStats(bulkActionId).subscribe(agentBulkActionEventStats => {
  console.log('Get Agent Bulk Action Event Stats:', agentBulkActionEventStats);
});
```

**61. getAgentBulkActionEvents**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const bulkActionId = 'your-bulk-action-id';
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const actionType = 'your-action-type';
const processingStatus = 'your-processing-status';
agentService.getAgentBulkActionEvents(bulkActionId, pageLink, actionType, processingStatus).subscribe(agentBulkActionEvents => {
  console.log('List of Agent Bulk Action Events:', agentBulkActionEvents);
});
```

**62. getRelatedEntityCandidates**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const entityType = {  // EntityType object
  // ... set the fields you need
};
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const currentEntityId = 'your-current-entity-id';
agentService.getRelatedEntityCandidates(entityType, pageLink, currentEntityId).subscribe(relatedEntityCandidates => {
  console.log('List of Related Entity Candidates:', relatedEntityCandidates);
});
```

### **AI CHAT SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const aiChatService = $injector.get(self.ctx.servicesMap.get('aiChatService'));
```

**1. listChats**

```javascript
const $injector = self.ctx.$scope.$injector;
const aiChatService = $injector.get(self.ctx.servicesMap.get('aiChatService'));
aiChatService.listChats().subscribe(listChats => {
  console.log('List Chats:', listChats);
});
```

**2. createChat**

```javascript
const $injector = self.ctx.$scope.$injector;
const aiChatService = $injector.get(self.ctx.servicesMap.get('aiChatService'));
const chat = {  // ChatConfiguration object
  // ... set the fields you need
};
aiChatService.createChat(chat).subscribe(createChat => {
  console.log('Create Chat:', createChat);
});
```

**3. updatedChat**

```javascript
const $injector = self.ctx.$scope.$injector;
const aiChatService = $injector.get(self.ctx.servicesMap.get('aiChatService'));
const chatId = 'your-chat-id';
const chat = {  // ChatConfiguration object
  // ... set the fields you need
};
aiChatService.updatedChat(chatId, chat).subscribe(saveddChat => {
  console.log('Saved Updated Chat:', saveddChat);
});
```

**4. deleteChat**

```javascript
const $injector = self.ctx.$scope.$injector;
const aiChatService = $injector.get(self.ctx.servicesMap.get('aiChatService'));
const chatId = 'your-chat-id';
aiChatService.deleteChat(chatId).subscribe(result => {
  console.log('Delete Chat result:', result);
});
```

**5. getChatMessages**

```javascript
const $injector = self.ctx.$scope.$injector;
const aiChatService = $injector.get(self.ctx.servicesMap.get('aiChatService'));
const chatId = 'your-chat-id';
aiChatService.getChatMessages(chatId).subscribe(chatMessages => {
  console.log('List of Chat Messages:', chatMessages);
});
```

**6. generateDashboard**

```javascript
const $injector = self.ctx.$scope.$injector;
const aiChatService = $injector.get(self.ctx.servicesMap.get('aiChatService'));
const deviceId = 'your-device-id';
const timeseriesKeys = [];  // e.g. array of timeseries-keys values
aiChatService.generateDashboard(deviceId, timeseriesKeys).subscribe(generateDashboard => {
  console.log('Generate Dashboard:', generateDashboard);
});
```

**7. resolveToolApproval**

```javascript
const $injector = self.ctx.$scope.$injector;
const aiChatService = $injector.get(self.ctx.servicesMap.get('aiChatService'));
const result = {  // ApprovalResult object
  // ... set the fields you need
};
aiChatService.resolveToolApproval(result).subscribe(resolveToolApproval => {
  console.log('Resolve Tool Approval:', resolveToolApproval);
});
```

**8. sendChatMessage**

```javascript
const $injector = self.ctx.$scope.$injector;
const aiChatService = $injector.get(self.ctx.servicesMap.get('aiChatService'));
const chatId = 'your-chat-id';
const request = {  // SendChatMessageRequest object
  // ... set the fields you need
};
aiChatService.sendChatMessage(chatId, request).subscribe(sendChatMessage => {
  console.log('Send Chat Message:', sendChatMessage);
});
```

**9. parseEventStrings**

```javascript
const $injector = self.ctx.$scope.$injector;
const aiChatService = $injector.get(self.ctx.servicesMap.get('aiChatService'));
const input = 'your-input';
const result = aiChatService.parseEventStrings(input);
console.log('Result:', result);
```

**10. parseSingleEvent**

```javascript
const $injector = self.ctx.$scope.$injector;
const aiChatService = $injector.get(self.ctx.servicesMap.get('aiChatService'));
const input = 'your-input';
const result = aiChatService.parseSingleEvent(input);
console.log('Result:', result);
```

### **AI MODEL SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const aiModelService = $injector.get(self.ctx.servicesMap.get('aiModelService'));
```

**1. saveAiModel**

```javascript
const $injector = self.ctx.$scope.$injector;
const aiModelService = $injector.get(self.ctx.servicesMap.get('aiModelService'));
const aiModel = {  // AiModel object
  // ... set the fields you need
};
aiModelService.saveAiModel(aiModel).subscribe(savedAiModel => {
  console.log('Saved Ai Model:', savedAiModel);
});
```

**2. getAiModels**

```javascript
const $injector = self.ctx.$scope.$injector;
const aiModelService = $injector.get(self.ctx.servicesMap.get('aiModelService'));
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
aiModelService.getAiModels(pageLink).subscribe(aiModels => {
  console.log('List of Ai Models:', aiModels);
});
```

**3. getAiModelById**

```javascript
const $injector = self.ctx.$scope.$injector;
const aiModelService = $injector.get(self.ctx.servicesMap.get('aiModelService'));
const aiModelId = 'your-ai-model-id';
aiModelService.getAiModelById(aiModelId).subscribe(aiModelBy => {
  console.log('Get Ai Model By Id:', aiModelBy);
});
```

**4. checkConnectivity**

```javascript
const $injector = self.ctx.$scope.$injector;
const aiModelService = $injector.get(self.ctx.servicesMap.get('aiModelService'));
const aiModelWithUserMsg = {  // AiModelWithUserMsg object
  // ... set the fields you need
};
aiModelService.checkConnectivity(aiModelWithUserMsg).subscribe(checkConnectivity => {
  console.log('Check Connectivity:', checkConnectivity);
});
```

### **ALARM COMMENT SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const alarmCommentService = $injector.get(self.ctx.servicesMap.get('alarmCommentService'));
```

**1. saveAlarmComment**

```javascript
const $injector = self.ctx.$scope.$injector;
const alarmCommentService = $injector.get(self.ctx.servicesMap.get('alarmCommentService'));
const alarmId = 'your-alarm-id';
const alarmComment = {  // AlarmComment object
  // ... set the fields you need
};
alarmCommentService.saveAlarmComment(alarmId, alarmComment).subscribe(savedAlarmComment => {
  console.log('Saved Alarm Comment:', savedAlarmComment);
});
```

**2. getAlarmComments**

```javascript
const $injector = self.ctx.$scope.$injector;
const alarmCommentService = $injector.get(self.ctx.servicesMap.get('alarmCommentService'));
const alarmId = 'your-alarm-id';
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
alarmCommentService.getAlarmComments(alarmId, pageLink).subscribe(alarmComments => {
  console.log('List of Alarm Comments:', alarmComments);
});
```

**3. deleteAlarmComments**

```javascript
const $injector = self.ctx.$scope.$injector;
const alarmCommentService = $injector.get(self.ctx.servicesMap.get('alarmCommentService'));
const alarmId = 'your-alarm-id';
const commentId = 'your-comment-id';
alarmCommentService.deleteAlarmComments(alarmId, commentId).subscribe(result => {
  console.log('Delete Alarm Comments result:', result);
});
```

### **ALARM RULES SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const alarmRulesService = $injector.get(self.ctx.servicesMap.get('alarmRulesService'));
```

**1. getAlarmRuleById**

```javascript
const $injector = self.ctx.$scope.$injector;
const alarmRulesService = $injector.get(self.ctx.servicesMap.get('alarmRulesService'));
const alarmRuleId = 'your-alarm-rule-id';
alarmRulesService.getAlarmRuleById(alarmRuleId).subscribe(alarmRuleBy => {
  console.log('Get Alarm Rule By Id:', alarmRuleBy);
});
```

**2. saveAlarmRule**

```javascript
const $injector = self.ctx.$scope.$injector;
const alarmRulesService = $injector.get(self.ctx.servicesMap.get('alarmRulesService'));
const alarmRule = {  // CalculatedFieldAlarmRule object
  // ... set the fields you need
};
alarmRulesService.saveAlarmRule(alarmRule).subscribe(savedAlarmRule => {
  console.log('Saved Alarm Rule:', savedAlarmRule);
});
```

**3. deleteAlarmRule**

```javascript
const $injector = self.ctx.$scope.$injector;
const alarmRulesService = $injector.get(self.ctx.servicesMap.get('alarmRulesService'));
const alarmRuleId = 'your-alarm-rule-id';
alarmRulesService.deleteAlarmRule(alarmRuleId).subscribe(result => {
  console.log('Delete Alarm Rule result:', result);
});
```

**4. getAlarmRules**

```javascript
const $injector = self.ctx.$scope.$injector;
const alarmRulesService = $injector.get(self.ctx.servicesMap.get('alarmRulesService'));
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const query = {  // CalculatedFieldsQuery object
  // ... set the fields you need
};
alarmRulesService.getAlarmRules(pageLink, query).subscribe(alarmRules => {
  console.log('List of Alarm Rules:', alarmRules);
});
```

**5. getAlarmRulesByEntityId**

```javascript
const $injector = self.ctx.$scope.$injector;
const alarmRulesService = $injector.get(self.ctx.servicesMap.get('alarmRulesService'));
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
alarmRulesService.getAlarmRulesByEntityId(pageLink).subscribe(alarmRulesByEntitys => {
  console.log('List of Alarm Rules By Entity Ids:', alarmRulesByEntitys);
});
```

**6. testScript**

```javascript
const $injector = self.ctx.$scope.$injector;
const alarmRulesService = $injector.get(self.ctx.servicesMap.get('alarmRulesService'));
const inputParams = {  // CalculatedFieldTestScriptInputParams object
  // ... set the fields you need
};
alarmRulesService.testScript(inputParams).subscribe(testScript => {
  console.log('Test Script:', testScript);
});
```

**7. getLatestAlarmRuleDebugEvent**

```javascript
const $injector = self.ctx.$scope.$injector;
const alarmRulesService = $injector.get(self.ctx.servicesMap.get('alarmRulesService'));
const id = 'your-id';
alarmRulesService.getLatestAlarmRuleDebugEvent(id).subscribe(latestAlarmRuleDebugEvent => {
  console.log('Get Latest Alarm Rule Debug Event:', latestAlarmRuleDebugEvent);
});
```

**8. getAlarmRuleNames**

```javascript
const $injector = self.ctx.$scope.$injector;
const alarmRulesService = $injector.get(self.ctx.servicesMap.get('alarmRulesService'));
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
alarmRulesService.getAlarmRuleNames(pageLink).subscribe(alarmRuleNames => {
  console.log('List of Alarm Rule Names:', alarmRuleNames);
});
```

### **ALARM SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const alarmService = $injector.get(self.ctx.servicesMap.get('alarmService'));
```

**1. getAlarm**

```javascript
const $injector = self.ctx.$scope.$injector;
const alarmService = $injector.get(self.ctx.servicesMap.get('alarmService'));
const alarmId = 'your-alarm-id';
alarmService.getAlarm(alarmId).subscribe(alarm => {
  console.log('Get Alarm:', alarm);
});
```

**2. getAlarmInfo**

```javascript
const $injector = self.ctx.$scope.$injector;
const alarmService = $injector.get(self.ctx.servicesMap.get('alarmService'));
const alarmId = 'your-alarm-id';
alarmService.getAlarmInfo(alarmId).subscribe(alarmInfo => {
  console.log('Get Alarm Info:', alarmInfo);
});
```

**3. saveAlarm**

```javascript
const $injector = self.ctx.$scope.$injector;
const alarmService = $injector.get(self.ctx.servicesMap.get('alarmService'));
const alarm = {  // Alarm object
  // ... set the fields you need
};
alarmService.saveAlarm(alarm).subscribe(savedAlarm => {
  console.log('Saved Alarm:', savedAlarm);
});
```

**4. ackAlarm**

```javascript
const $injector = self.ctx.$scope.$injector;
const alarmService = $injector.get(self.ctx.servicesMap.get('alarmService'));
const alarmId = 'your-alarm-id';
alarmService.ackAlarm(alarmId).subscribe(ackAlarm => {
  console.log('Ack Alarm:', ackAlarm);
});
```

**5. clearAlarm**

```javascript
const $injector = self.ctx.$scope.$injector;
const alarmService = $injector.get(self.ctx.servicesMap.get('alarmService'));
const alarmId = 'your-alarm-id';
alarmService.clearAlarm(alarmId).subscribe(clearAlarm => {
  console.log('Clear Alarm:', clearAlarm);
});
```

**6. assignAlarm**

```javascript
const $injector = self.ctx.$scope.$injector;
const alarmService = $injector.get(self.ctx.servicesMap.get('alarmService'));
const alarmId = 'your-alarm-id';
const assigneeId = 'your-assignee-id';
alarmService.assignAlarm(alarmId, assigneeId).subscribe(assignAlarm => {
  console.log('Assign Alarm:', assignAlarm);
});
```

**7. unassignAlarm**

```javascript
const $injector = self.ctx.$scope.$injector;
const alarmService = $injector.get(self.ctx.servicesMap.get('alarmService'));
const alarmId = 'your-alarm-id';
alarmService.unassignAlarm(alarmId).subscribe(unassignAlarm => {
  console.log('Unassign Alarm:', unassignAlarm);
});
```

**8. deleteAlarm**

```javascript
const $injector = self.ctx.$scope.$injector;
const alarmService = $injector.get(self.ctx.servicesMap.get('alarmService'));
const alarmId = 'your-alarm-id';
alarmService.deleteAlarm(alarmId).subscribe(result => {
  console.log('Delete Alarm result:', result);
});
```

**9. getAlarms**

```javascript
const $injector = self.ctx.$scope.$injector;
const alarmService = $injector.get(self.ctx.servicesMap.get('alarmService'));
const query = {  // AlarmQuery object
  // ... set the fields you need
};
alarmService.getAlarms(query).subscribe(alarms => {
  console.log('List of Alarms:', alarms);
});
```

**10. getAlarmsV2**

```javascript
const $injector = self.ctx.$scope.$injector;
const alarmService = $injector.get(self.ctx.servicesMap.get('alarmService'));
const query = {  // AlarmQueryV2 object
  // ... set the fields you need
};
alarmService.getAlarmsV2(query).subscribe(alarmsV2s => {
  console.log('List of Alarms V2s:', alarmsV2s);
});
```

**11. getAllAlarms**

```javascript
const $injector = self.ctx.$scope.$injector;
const alarmService = $injector.get(self.ctx.servicesMap.get('alarmService'));
const query = {  // AlarmQuery object
  // ... set the fields you need
};
alarmService.getAllAlarms(query).subscribe(allAlarms => {
  console.log('List of All Alarms:', allAlarms);
});
```

**12. getAllAlarmsV2**

```javascript
const $injector = self.ctx.$scope.$injector;
const alarmService = $injector.get(self.ctx.servicesMap.get('alarmService'));
const query = {  // AlarmQueryV2 object
  // ... set the fields you need
};
alarmService.getAllAlarmsV2(query).subscribe(allAlarmsV2s => {
  console.log('List of All Alarms V2s:', allAlarmsV2s);
});
```

**13. getHighestAlarmSeverity**

```javascript
const $injector = self.ctx.$scope.$injector;
const alarmService = $injector.get(self.ctx.servicesMap.get('alarmService'));
const entityId = {  // EntityId object
  // ... set the fields you need
};
const alarmSearchStatus = {  // AlarmSearchStatus object
  // ... set the fields you need
};
const alarmStatus = {  // AlarmStatus object
  // ... set the fields you need
};
alarmService.getHighestAlarmSeverity(entityId, alarmSearchStatus, alarmStatus).subscribe(highestAlarmSeverity => {
  console.log('Get Highest Alarm Severity:', highestAlarmSeverity);
});
```

**14. getAlarmTypes**

```javascript
const $injector = self.ctx.$scope.$injector;
const alarmService = $injector.get(self.ctx.servicesMap.get('alarmService'));
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
alarmService.getAlarmTypes(pageLink).subscribe(alarmTypes => {
  console.log('List of Alarm Types:', alarmTypes);
});
```

### **API KEY SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const apiKeyService = $injector.get(self.ctx.servicesMap.get('apiKeyService'));
```

**1. saveApiKey**

```javascript
const $injector = self.ctx.$scope.$injector;
const apiKeyService = $injector.get(self.ctx.servicesMap.get('apiKeyService'));
const apiKey = {  // ApiKeyInfo object
  // ... set the fields you need
};
apiKeyService.saveApiKey(apiKey).subscribe(savedApiKey => {
  console.log('Saved Api Key:', savedApiKey);
});
```

**2. deleteApiKey**

```javascript
const $injector = self.ctx.$scope.$injector;
const apiKeyService = $injector.get(self.ctx.servicesMap.get('apiKeyService'));
const id = 'your-id';
apiKeyService.deleteApiKey(id).subscribe(result => {
  console.log('Delete Api Key result:', result);
});
```

**3. updateApiKeyDescription**

```javascript
const $injector = self.ctx.$scope.$injector;
const apiKeyService = $injector.get(self.ctx.servicesMap.get('apiKeyService'));
const id = 'your-id';
const description = 'your-description';
apiKeyService.updateApiKeyDescription(id, description).subscribe(savedApiKeyDescription => {
  console.log('Saved Api Key Description:', savedApiKeyDescription);
});
```

**4. enableApiKey**

```javascript
const $injector = self.ctx.$scope.$injector;
const apiKeyService = $injector.get(self.ctx.servicesMap.get('apiKeyService'));
const id = 'your-id';
const enabledValue = true;
apiKeyService.enableApiKey(id, enabledValue).subscribe(enableApiKey => {
  console.log('Enable Api Key:', enableApiKey);
});
```

**5. getUserApiKeys**

```javascript
const $injector = self.ctx.$scope.$injector;
const apiKeyService = $injector.get(self.ctx.servicesMap.get('apiKeyService'));
const userId = 'your-user-id';
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
apiKeyService.getUserApiKeys(userId, pageLink).subscribe(userApiKeys => {
  console.log('List of User Api Keys:', userApiKeys);
});
```

### **ASSET PROFILE SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const assetProfileService = $injector.get(self.ctx.servicesMap.get('assetProfileService'));
```

**1. getAssetProfiles**

```javascript
const $injector = self.ctx.$scope.$injector;
const assetProfileService = $injector.get(self.ctx.servicesMap.get('assetProfileService'));
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
assetProfileService.getAssetProfiles(pageLink).subscribe(assetProfiles => {
  console.log('List of Asset Profiles:', assetProfiles);
});
```

**2. getAssetProfile**

```javascript
const $injector = self.ctx.$scope.$injector;
const assetProfileService = $injector.get(self.ctx.servicesMap.get('assetProfileService'));
const assetProfileId = 'your-asset-profile-id';
assetProfileService.getAssetProfile(assetProfileId).subscribe(assetProfile => {
  console.log('Get Asset Profile:', assetProfile);
});
```

**3. exportAssetProfile**

```javascript
const $injector = self.ctx.$scope.$injector;
const assetProfileService = $injector.get(self.ctx.servicesMap.get('assetProfileService'));
const assetProfileId = 'your-asset-profile-id';
assetProfileService.exportAssetProfile(assetProfileId).subscribe(exportAssetProfile => {
  console.log('Export Asset Profile:', exportAssetProfile);
});
```

**4. saveAssetProfile**

```javascript
const $injector = self.ctx.$scope.$injector;
const assetProfileService = $injector.get(self.ctx.servicesMap.get('assetProfileService'));
const assetProfile = {  // AssetProfile object
  // ... set the fields you need
};
assetProfileService.saveAssetProfile(assetProfile).subscribe(savedAssetProfile => {
  console.log('Saved Asset Profile:', savedAssetProfile);
});
```

**5. setDefaultAssetProfile**

```javascript
const $injector = self.ctx.$scope.$injector;
const assetProfileService = $injector.get(self.ctx.servicesMap.get('assetProfileService'));
const assetProfileId = 'your-asset-profile-id';
assetProfileService.setDefaultAssetProfile(assetProfileId).subscribe(setDefaultAssetProfile => {
  console.log('Set Default Asset Profile:', setDefaultAssetProfile);
});
```

**6. getDefaultAssetProfileInfo**

```javascript
const $injector = self.ctx.$scope.$injector;
const assetProfileService = $injector.get(self.ctx.servicesMap.get('assetProfileService'));
assetProfileService.getDefaultAssetProfileInfo().subscribe(defaultAssetProfileInfo => {
  console.log('Get Default Asset Profile Info:', defaultAssetProfileInfo);
});
```

**7. getAssetProfileInfo**

```javascript
const $injector = self.ctx.$scope.$injector;
const assetProfileService = $injector.get(self.ctx.servicesMap.get('assetProfileService'));
const assetProfileId = 'your-asset-profile-id';
assetProfileService.getAssetProfileInfo(assetProfileId).subscribe(assetProfileInfo => {
  console.log('Get Asset Profile Info:', assetProfileInfo);
});
```

**8. getAssetProfileInfos**

```javascript
const $injector = self.ctx.$scope.$injector;
const assetProfileService = $injector.get(self.ctx.servicesMap.get('assetProfileService'));
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
assetProfileService.getAssetProfileInfos(pageLink).subscribe(assetProfileInfos => {
  console.log('List of Asset Profile Infos:', assetProfileInfos);
});
```

**9. getAssetProfilesByIds**

```javascript
const $injector = self.ctx.$scope.$injector;
const assetProfileService = $injector.get(self.ctx.servicesMap.get('assetProfileService'));
const assetProfileIds = ['your-asset-profile-i-1', 'your-asset-profile-i-2'];
assetProfileService.getAssetProfilesByIds(assetProfileIds).subscribe(assetProfilesBys => {
  console.log('List of Asset Profiles By Ids:', assetProfilesBys);
});
```

**10. getAssetProfileNames**

```javascript
const $injector = self.ctx.$scope.$injector;
const assetProfileService = $injector.get(self.ctx.servicesMap.get('assetProfileService'));
const activeOnly = 'value';
assetProfileService.getAssetProfileNames(activeOnly).subscribe(assetProfileNames => {
  console.log('List of Asset Profile Names:', assetProfileNames);
});
```

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
const assetService = self.ctx.assetService;
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const type = 'value';
assetService.getTenantAssets(pageLink, type).subscribe(tenantAssets => {
  console.log('List of Tenant Assets:', tenantAssets);
});
```

**2. getCustomerAssets**

```javascript
const assetService = self.ctx.assetService;
const customerId = 'your-customer-id';
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const type = 'value';
assetService.getCustomerAssets(customerId, pageLink, type).subscribe(customerAssets => {
  console.log('List of Customer Assets:', customerAssets);
});
```

**3. getAsset**

```javascript
const assetService = self.ctx.assetService;
const assetId = 'your-asset-id';
assetService.getAsset(assetId).subscribe(asset => {
  console.log('Get Asset:', asset);
});
```

**4. getAssets**

```javascript
const assetService = self.ctx.assetService;
const assetIds = ['your-asset-i-1', 'your-asset-i-2'];
assetService.getAssets(assetIds).subscribe(assets => {
  console.log('List of Assets:', assets);
});
```

**5. getUserAssets**

```javascript
const assetService = self.ctx.assetService;
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const type = 'value';
assetService.getUserAssets(pageLink, type).subscribe(userAssets => {
  console.log('List of User Assets:', userAssets);
});
```

**6. getAllAssetInfos**

```javascript
const assetService = self.ctx.assetService;
const includeCustomers = true;
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const assetProfileId = 'value';
assetService.getAllAssetInfos(includeCustomers, pageLink, assetProfileId).subscribe(allAssetInfos => {
  console.log('List of All Asset Infos:', allAssetInfos);
});
```

**7. getCustomerAssetInfos**

```javascript
const assetService = self.ctx.assetService;
const includeCustomers = true;
const customerId = 'your-customer-id';
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const assetProfileId = 'value';
assetService.getCustomerAssetInfos(includeCustomers, customerId, pageLink, assetProfileId).subscribe(customerAssetInfos => {
  console.log('List of Customer Asset Infos:', customerAssetInfos);
});
```

**8. getAssetInfo**

```javascript
const assetService = self.ctx.assetService;
const assetId = 'your-asset-id';
assetService.getAssetInfo(assetId).subscribe(assetInfo => {
  console.log('Get Asset Info:', assetInfo);
});
```

**9. saveAsset**

```javascript
const assetService = self.ctx.assetService;
const asset = {  // Asset object
  // ... set the fields you need
};
const entityGroupIds = ['your-entity-group-i-1', 'your-entity-group-i-2'];
const result = assetService.saveAsset(asset, entityGroupIds);
console.log('Result:', result);
```

**10. getAssetTypes**

```javascript
const assetService = self.ctx.assetService;
assetService.getAssetTypes().subscribe(assetTypes => {
  console.log('List of Asset Types:', assetTypes);
});
```

**11. findByQuery**

```javascript
const assetService = self.ctx.assetService;
const query = {  // AssetSearchQuery object
  // ... set the fields you need
};
assetService.findByQuery(query).subscribe(byQuerys => {
  console.log('List of By Querys:', byQuerys);
});
```

**12. findByName**

```javascript
const assetService = self.ctx.assetService;
const assetName = 'your-asset-name';
assetService.findByName(assetName).subscribe(byName => {
  console.log('Find By Name:', byName);
});
```

**13. bulkImportAssets**

```javascript
const assetService = self.ctx.assetService;
const entitiesData = {  // BulkImportRequest object
  // ... set the fields you need
};
assetService.bulkImportAssets(entitiesData).subscribe(bulkImportAssets => {
  console.log('Bulk Import Assets:', bulkImportAssets);
});
```

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
const attributeService = self.ctx.attributeService;
const entityId = {  // EntityId object
  // ... set the fields you need
};
const attributeScope = {  // AttributeScope object
  // ... set the fields you need
};
const keys = [];  // e.g. array of keys values
attributeService.getEntityAttributes(entityId, attributeScope, keys).subscribe(entityAttributes => {
  console.log('List of Entity Attributes:', entityAttributes);
});
```

**2. deleteEntityAttributes**

```javascript
const attributeService = self.ctx.attributeService;
const entityId = {  // EntityId object
  // ... set the fields you need
};
const attributeScope = {  // AttributeScope object
  // ... set the fields you need
};
const attributes = [];  // e.g. array of attributes values
attributeService.deleteEntityAttributes(entityId, attributeScope, attributes).subscribe(result => {
  console.log('Delete Entity Attributes result:', result);
});
```

**3. deleteEntityTimeseries**

```javascript
const attributeService = self.ctx.attributeService;
const entityId = {  // EntityId object
  // ... set the fields you need
};
const timeseries = [];  // e.g. array of timeseries values
const startTs = 10;
const endTs = 10;
attributeService.deleteEntityTimeseries(entityId, timeseries, startTs, endTs).subscribe(result => {
  console.log('Delete Entity Timeseries result:', result);
});
```

**4. saveEntityAttributes**

```javascript
const attributeService = self.ctx.attributeService;
const entityId = {  // EntityId object
  // ... set the fields you need
};
const attributeScope = {  // AttributeScope object
  // ... set the fields you need
};
const attributes = [];  // e.g. array of attributes values
attributeService.saveEntityAttributes(entityId, attributeScope, attributes).subscribe(savedEntityAttributes => {
  console.log('Saved Entity Attributes:', savedEntityAttributes);
});
```

**5. saveEntityTimeseries**

```javascript
const attributeService = self.ctx.attributeService;
const entityId = {  // EntityId object
  // ... set the fields you need
};
const timeseriesScope = 'your-timeseries-scope';
const timeseries = [];  // e.g. array of timeseries values
attributeService.saveEntityTimeseries(entityId, timeseriesScope, timeseries).subscribe(savedEntityTimeseries => {
  console.log('Saved Entity Timeseries:', savedEntityTimeseries);
});
```

**6. getEntityTimeseries**

```javascript
const attributeService = self.ctx.attributeService;
const entityId = {  // EntityId object
  // ... set the fields you need
};
const keys = [];  // e.g. array of keys values
const startTs = 10;
const endTs = 10;
const limit = 'value';
const agg = 'value';
const interval = 10;
const orderBy = 'value';
const useStrictDataTypes = 'value';
attributeService.getEntityTimeseries(entityId, keys, startTs, endTs, limit, agg, interval, orderBy, useStrictDataTypes).subscribe(entityTimeseries => {
  console.log('Get Entity Timeseries:', entityTimeseries);
});
```

**7. getEntityTimeseriesLatest**

```javascript
const attributeService = self.ctx.attributeService;
const entityId = {  // EntityId object
  // ... set the fields you need
};
const keys = [];  // e.g. array of keys values
attributeService.getEntityTimeseriesLatest(entityId, keys).subscribe(entityTimeseriesLatest => {
  console.log('Get Entity Timeseries Latest:', entityTimeseriesLatest);
});
```

### **AUDIT LOG SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const auditLogService = $injector.get(self.ctx.servicesMap.get('auditLogService'));
```

**1. getAuditLogs**

```javascript
const $injector = self.ctx.$scope.$injector;
const auditLogService = $injector.get(self.ctx.servicesMap.get('auditLogService'));
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const result = auditLogService.getAuditLogs(pageLink);
console.log('Result:', result);
```

**2. getAuditLogsByCustomerId**

```javascript
const $injector = self.ctx.$scope.$injector;
const auditLogService = $injector.get(self.ctx.servicesMap.get('auditLogService'));
const customerId = 'your-customer-id';
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const result = auditLogService.getAuditLogsByCustomerId(customerId, pageLink);
console.log('Result:', result);
```

**3. getAuditLogsByUserId**

```javascript
const $injector = self.ctx.$scope.$injector;
const auditLogService = $injector.get(self.ctx.servicesMap.get('auditLogService'));
const userId = 'your-user-id';
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const result = auditLogService.getAuditLogsByUserId(userId, pageLink);
console.log('Result:', result);
```

**4. getAuditLogsByEntityId**

```javascript
const $injector = self.ctx.$scope.$injector;
const auditLogService = $injector.get(self.ctx.servicesMap.get('auditLogService'));
const entityId = {  // EntityId object
  // ... set the fields you need
};
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const result = auditLogService.getAuditLogsByEntityId(entityId, pageLink);
console.log('Result:', result);
```

### **BLOB ENTITY SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const blobEntityService = $injector.get(self.ctx.servicesMap.get('blobEntityService'));
```

**1. getBlobEntityInfo**

```javascript
const $injector = self.ctx.$scope.$injector;
const blobEntityService = $injector.get(self.ctx.servicesMap.get('blobEntityService'));
const blobEntityId = 'your-blob-entity-id';
blobEntityService.getBlobEntityInfo(blobEntityId).subscribe(blobEntityInfo => {
  console.log('Get Blob Entity Info:', blobEntityInfo);
});
```

**2. getBlobEntities**

```javascript
const $injector = self.ctx.$scope.$injector;
const blobEntityService = $injector.get(self.ctx.servicesMap.get('blobEntityService'));
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const type = 'value';
blobEntityService.getBlobEntities(pageLink, type).subscribe(blobEntities => {
  console.log('List of Blob Entities:', blobEntities);
});
```

**3. getBlobEntitiesByIds**

```javascript
const $injector = self.ctx.$scope.$injector;
const blobEntityService = $injector.get(self.ctx.servicesMap.get('blobEntityService'));
const blobEntityIds = ['your-blob-entity-i-1', 'your-blob-entity-i-2'];
blobEntityService.getBlobEntitiesByIds(blobEntityIds).subscribe(blobEntitiesBys => {
  console.log('List of Blob Entities By Ids:', blobEntitiesBys);
});
```

**4. downloadBlobEntity**

```javascript
const $injector = self.ctx.$scope.$injector;
const blobEntityService = $injector.get(self.ctx.servicesMap.get('blobEntityService'));
const blobEntityId = 'your-blob-entity-id';
blobEntityService.downloadBlobEntity(blobEntityId).subscribe(downloadBlobEntity => {
  console.log('Download Blob Entity:', downloadBlobEntity);
});
```

### **CALCULATED FIELDS SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const calculatedFieldsService = $injector.get(self.ctx.servicesMap.get('calculatedFieldsService'));
```

**1. getCalculatedFieldById**

```javascript
const $injector = self.ctx.$scope.$injector;
const calculatedFieldsService = $injector.get(self.ctx.servicesMap.get('calculatedFieldsService'));
const calculatedFieldId = 'your-calculated-field-id';
calculatedFieldsService.getCalculatedFieldById(calculatedFieldId).subscribe(calculatedFieldBy => {
  console.log('Get Calculated Field By Id:', calculatedFieldBy);
});
```

**2. saveCalculatedField**

```javascript
const $injector = self.ctx.$scope.$injector;
const calculatedFieldsService = $injector.get(self.ctx.servicesMap.get('calculatedFieldsService'));
const calculatedField = {  // CalculatedField object
  // ... set the fields you need
};
calculatedFieldsService.saveCalculatedField(calculatedField).subscribe(savedCalculatedField => {
  console.log('Saved Calculated Field:', savedCalculatedField);
});
```

**3. deleteCalculatedField**

```javascript
const $injector = self.ctx.$scope.$injector;
const calculatedFieldsService = $injector.get(self.ctx.servicesMap.get('calculatedFieldsService'));
const calculatedFieldId = 'your-calculated-field-id';
calculatedFieldsService.deleteCalculatedField(calculatedFieldId).subscribe(result => {
  console.log('Delete Calculated Field result:', result);
});
```

**4. getCalculatedFields**

```javascript
const $injector = self.ctx.$scope.$injector;
const calculatedFieldsService = $injector.get(self.ctx.servicesMap.get('calculatedFieldsService'));
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const query = {  // CalculatedFieldsQuery object
  // ... set the fields you need
};
calculatedFieldsService.getCalculatedFields(pageLink, query).subscribe(calculatedFields => {
  console.log('List of Calculated Fields:', calculatedFields);
});
```

**5. getCalculatedFieldsByEntityId**

```javascript
const $injector = self.ctx.$scope.$injector;
const calculatedFieldsService = $injector.get(self.ctx.servicesMap.get('calculatedFieldsService'));
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const type = {  // CalculatedFieldType object
  // ... set the fields you need
};
calculatedFieldsService.getCalculatedFieldsByEntityId(pageLink, type).subscribe(calculatedFieldsByEntitys => {
  console.log('List of Calculated Fields By Entity Ids:', calculatedFieldsByEntitys);
});
```

**6. testScript**

```javascript
const $injector = self.ctx.$scope.$injector;
const calculatedFieldsService = $injector.get(self.ctx.servicesMap.get('calculatedFieldsService'));
const inputParams = {  // CalculatedFieldTestScriptInputParams object
  // ... set the fields you need
};
calculatedFieldsService.testScript(inputParams).subscribe(testScript => {
  console.log('Test Script:', testScript);
});
```

**7. getLatestCalculatedFieldDebugEvent**

```javascript
const $injector = self.ctx.$scope.$injector;
const calculatedFieldsService = $injector.get(self.ctx.servicesMap.get('calculatedFieldsService'));
const id = 'your-id';
calculatedFieldsService.getLatestCalculatedFieldDebugEvent(id).subscribe(latestCalculatedFieldDebugEvent => {
  console.log('Get Latest Calculated Field Debug Event:', latestCalculatedFieldDebugEvent);
});
```

**8. getCalculatedFieldNames**

```javascript
const $injector = self.ctx.$scope.$injector;
const calculatedFieldsService = $injector.get(self.ctx.servicesMap.get('calculatedFieldsService'));
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const type = {  // CalculatedFieldType object
  // ... set the fields you need
};
calculatedFieldsService.getCalculatedFieldNames(pageLink, type).subscribe(calculatedFieldNames => {
  console.log('List of Calculated Field Names:', calculatedFieldNames);
});
```

**9. reprocessCalculatedField**

```javascript
const $injector = self.ctx.$scope.$injector;
const calculatedFieldsService = $injector.get(self.ctx.servicesMap.get('calculatedFieldsService'));
const id = 'your-id';
const startTs = 10;
const endTs = 10;
calculatedFieldsService.reprocessCalculatedField(id, startTs, endTs).subscribe(reprocessCalculatedField => {
  console.log('Reprocess Calculated Field:', reprocessCalculatedField);
});
```

**10. getLastCalculatedFieldReprocessingJob**

```javascript
const $injector = self.ctx.$scope.$injector;
const calculatedFieldsService = $injector.get(self.ctx.servicesMap.get('calculatedFieldsService'));
const id = 'your-id';
calculatedFieldsService.getLastCalculatedFieldReprocessingJob(id).subscribe(lastCalculatedFieldReprocessingJob => {
  console.log('Get Last Calculated Field Reprocessing Job:', lastCalculatedFieldReprocessingJob);
});
```

**11. validateCalculatedFieldReprocessing**

```javascript
const $injector = self.ctx.$scope.$injector;
const calculatedFieldsService = $injector.get(self.ctx.servicesMap.get('calculatedFieldsService'));
const id = 'your-id';
calculatedFieldsService.validateCalculatedFieldReprocessing(id).subscribe(validateCalculatedFieldReprocessing => {
  console.log('Validate Calculated Field Reprocessing:', validateCalculatedFieldReprocessing);
});
```

### **COMPONENT DESCRIPTOR SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const componentDescriptorService = $injector.get(self.ctx.servicesMap.get('componentDescriptorService'));
```

**1. getComponentDescriptorsByType**

```javascript
const $injector = self.ctx.$scope.$injector;
const componentDescriptorService = $injector.get(self.ctx.servicesMap.get('componentDescriptorService'));
const componentType = {  // ComponentType object
  // ... set the fields you need
};
const ruleChainType = {  // RuleChainType object
  // ... set the fields you need
};
componentDescriptorService.getComponentDescriptorsByType(componentType, ruleChainType).subscribe(componentDescriptorsByTypes => {
  console.log('List of Component Descriptors By Types:', componentDescriptorsByTypes);
});
```

**2. getComponentDescriptorsByTypes**

```javascript
const $injector = self.ctx.$scope.$injector;
const componentDescriptorService = $injector.get(self.ctx.servicesMap.get('componentDescriptorService'));
const componentTypes = [];  // e.g. array of component-types values
const ruleChainType = {  // RuleChainType object
  // ... set the fields you need
};
componentDescriptorService.getComponentDescriptorsByTypes(componentTypes, ruleChainType).subscribe(componentDescriptorsByTypes => {
  console.log('List of Component Descriptors By Types:', componentDescriptorsByTypes);
});
```

**3. getComponentDescriptorByClazz**

```javascript
const $injector = self.ctx.$scope.$injector;
const componentDescriptorService = $injector.get(self.ctx.servicesMap.get('componentDescriptorService'));
const componentDescriptorClazz = 'your-component-descriptor-clazz';
componentDescriptorService.getComponentDescriptorByClazz(componentDescriptorClazz).subscribe(componentDescriptorByClazz => {
  console.log('Get Component Descriptor By Clazz:', componentDescriptorByClazz);
});
```

### **CONVERTER LIBRARY SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const converterLibraryService = $injector.get(self.ctx.servicesMap.get('converterLibraryService'));
```

**1. getVendors**

```javascript
const $injector = self.ctx.$scope.$injector;
const converterLibraryService = $injector.get(self.ctx.servicesMap.get('converterLibraryService'));
const integrationType = {  // IntegrationType object
  // ... set the fields you need
};
const converterType = {  // ConverterType object
  // ... set the fields you need
};
converterLibraryService.getVendors(integrationType, converterType).subscribe(vendors => {
  console.log('Get Vendors:', vendors);
});
```

**2. getModels**

```javascript
const $injector = self.ctx.$scope.$injector;
const converterLibraryService = $injector.get(self.ctx.servicesMap.get('converterLibraryService'));
const integrationType = {  // IntegrationType object
  // ... set the fields you need
};
const vendorName = 'your-vendor-name';
const converterType = {  // ConverterType object
  // ... set the fields you need
};
converterLibraryService.getModels(integrationType, vendorName, converterType).subscribe(models => {
  console.log('Get Models:', models);
});
```

**3. getConverter**

```javascript
const $injector = self.ctx.$scope.$injector;
const converterLibraryService = $injector.get(self.ctx.servicesMap.get('converterLibraryService'));
const integrationType = {  // IntegrationType object
  // ... set the fields you need
};
const vendorName = 'your-vendor-name';
const modelName = 'your-model-name';
const converterType = {  // ConverterType object
  // ... set the fields you need
};
converterLibraryService.getConverter(integrationType, vendorName, modelName, converterType).subscribe(converter => {
  console.log('Get Converter:', converter);
});
```

**4. getConverterMetaData**

```javascript
const $injector = self.ctx.$scope.$injector;
const converterLibraryService = $injector.get(self.ctx.servicesMap.get('converterLibraryService'));
const integrationType = {  // IntegrationType object
  // ... set the fields you need
};
const vendorName = 'your-vendor-name';
const modelName = 'your-model-name';
const converterType = {  // ConverterType object
  // ... set the fields you need
};
converterLibraryService.getConverterMetaData(integrationType, vendorName, modelName, converterType).subscribe(converterMetaData => {
  console.log('Get Converter Meta Data:', converterMetaData);
});
```

**5. getConverterPayload**

```javascript
const $injector = self.ctx.$scope.$injector;
const converterLibraryService = $injector.get(self.ctx.servicesMap.get('converterLibraryService'));
const integrationType = {  // IntegrationType object
  // ... set the fields you need
};
const vendorName = 'your-vendor-name';
const modelName = 'your-model-name';
const converterType = {  // ConverterType object
  // ... set the fields you need
};
converterLibraryService.getConverterPayload(integrationType, vendorName, modelName, converterType).subscribe(converterPayload => {
  console.log('Get Converter Payload:', converterPayload);
});
```

### **CONVERTER SERVICE**

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

### **CUSTOM MENU SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const customMenuService = $injector.get(self.ctx.servicesMap.get('customMenuService'));
```

**1. getCustomMenu**

```javascript
const $injector = self.ctx.$scope.$injector;
const customMenuService = $injector.get(self.ctx.servicesMap.get('customMenuService'));
const result = customMenuService.getCustomMenu();
console.log('Result:', result);
```

**2. loadCustomMenu**

```javascript
const $injector = self.ctx.$scope.$injector;
const customMenuService = $injector.get(self.ctx.servicesMap.get('customMenuService'));
customMenuService.loadCustomMenu().subscribe(customMenu => {
  console.log('Load Custom Menu:', customMenu);
});
```

**3. getCustomMenuInfos**

```javascript
const $injector = self.ctx.$scope.$injector;
const customMenuService = $injector.get(self.ctx.servicesMap.get('customMenuService'));
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const scope = {  // CMScope object
  // ... set the fields you need
};
const assigneeType = {  // CMAssigneeType object
  // ... set the fields you need
};
customMenuService.getCustomMenuInfos(pageLink, scope, assigneeType).subscribe(customMenuInfos => {
  console.log('List of Custom Menu Infos:', customMenuInfos);
});
```

**4. getCustomMenuInfo**

```javascript
const $injector = self.ctx.$scope.$injector;
const customMenuService = $injector.get(self.ctx.servicesMap.get('customMenuService'));
const customMenuId = 'your-custom-menu-id';
customMenuService.getCustomMenuInfo(customMenuId).subscribe(customMenuInfo => {
  console.log('Get Custom Menu Info:', customMenuInfo);
});
```

**5. getCustomMenuConfig**

```javascript
const $injector = self.ctx.$scope.$injector;
const customMenuService = $injector.get(self.ctx.servicesMap.get('customMenuService'));
const customMenuId = 'your-custom-menu-id';
customMenuService.getCustomMenuConfig(customMenuId).subscribe(customMenuConfig => {
  console.log('Get Custom Menu Config:', customMenuConfig);
});
```

**6. getCustomMenuAssigneeList**

```javascript
const $injector = self.ctx.$scope.$injector;
const customMenuService = $injector.get(self.ctx.servicesMap.get('customMenuService'));
const customMenuId = 'your-custom-menu-id';
customMenuService.getCustomMenuAssigneeList(customMenuId).subscribe(customMenuAssigneeLists => {
  console.log('List of Custom Menu Assignee Lists:', customMenuAssigneeLists);
});
```

**7. updateCustomMenuConfig**

```javascript
const $injector = self.ctx.$scope.$injector;
const customMenuService = $injector.get(self.ctx.servicesMap.get('customMenuService'));
const customMenuId = 'your-custom-menu-id';
const customMenuConfig = {  // CustomMenuConfig object
  // ... set the fields you need
};
customMenuService.updateCustomMenuConfig(customMenuId, customMenuConfig).subscribe(savedCustomMenuConfig => {
  console.log('Saved Custom Menu Config:', savedCustomMenuConfig);
});
```

**8. updateCustomMenuName**

```javascript
const $injector = self.ctx.$scope.$injector;
const customMenuService = $injector.get(self.ctx.servicesMap.get('customMenuService'));
const customMenuId = 'your-custom-menu-id';
const name = 'name-value';
customMenuService.updateCustomMenuName(customMenuId, name).subscribe(savedCustomMenuName => {
  console.log('Saved Custom Menu Name:', savedCustomMenuName);
});
```

**9. assignCustomMenu**

```javascript
const $injector = self.ctx.$scope.$injector;
const customMenuService = $injector.get(self.ctx.servicesMap.get('customMenuService'));
const customMenuId = 'your-custom-menu-id';
const assigneeType = {  // CMAssigneeType object
  // ... set the fields you need
};
const entityIds = ['your-entity-i-1', 'your-entity-i-2'];
customMenuService.assignCustomMenu(customMenuId, assigneeType, entityIds).subscribe(assignCustomMenu => {
  console.log('Assign Custom Menu:', assignCustomMenu);
});
```

**10. saveCustomMenu**

```javascript
const $injector = self.ctx.$scope.$injector;
const customMenuService = $injector.get(self.ctx.servicesMap.get('customMenuService'));
const customMenuInfo = {  // CustomMenuInfo object
  // ... set the fields you need
};
const assignToList = [];  // e.g. array of assign-to-list values
customMenuService.saveCustomMenu(customMenuInfo, assignToList).subscribe(savedCustomMenu => {
  console.log('Saved Custom Menu:', savedCustomMenu);
});
```

**11. deleteCustomMenu**

```javascript
const $injector = self.ctx.$scope.$injector;
const customMenuService = $injector.get(self.ctx.servicesMap.get('customMenuService'));
const customMenuId = 'your-custom-menu-id';
customMenuService.deleteCustomMenu(customMenuId).subscribe(result => {
  console.log('Delete Custom Menu result:', result);
});
```

### **CUSTOM TRANSLATION SERVICE**

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
const customerService = self.ctx.customerService;
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
customerService.getCustomers(pageLink).subscribe(customers => {
  console.log('List of Customers:', customers);
});
```

**2. getCustomer**

```javascript
const customerService = self.ctx.customerService;
const customerId = 'your-customer-id';
customerService.getCustomer(customerId).subscribe(customer => {
  console.log('Get Customer:', customer);
});
```

**3. getCustomerInfo**

```javascript
const customerService = self.ctx.customerService;
const customerId = 'your-customer-id';
customerService.getCustomerInfo(customerId).subscribe(customerInfo => {
  console.log('Get Customer Info:', customerInfo);
});
```

**4. saveCustomer**

```javascript
const customerService = self.ctx.customerService;
const customer = {  // Customer object
  // ... set the fields you need
};
const entityGroupIds = ['your-entity-group-i-1', 'your-entity-group-i-2'];
const result = customerService.saveCustomer(customer, entityGroupIds);
console.log('Result:', result);
```

**5. getCustomersByIds**

```javascript
const customerService = self.ctx.customerService;
const customerIds = ['your-customer-i-1', 'your-customer-i-2'];
customerService.getCustomersByIds(customerIds).subscribe(customersBys => {
  console.log('List of Customers By Ids:', customersBys);
});
```

**6. getUserCustomers**

```javascript
const customerService = self.ctx.customerService;
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
customerService.getUserCustomers(pageLink).subscribe(userCustomers => {
  console.log('List of User Customers:', userCustomers);
});
```

**7. getAllCustomerInfos**

```javascript
const customerService = self.ctx.customerService;
const includeCustomers = true;
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
customerService.getAllCustomerInfos(includeCustomers, pageLink).subscribe(allCustomerInfos => {
  console.log('List of All Customer Infos:', allCustomerInfos);
});
```

**8. getCustomerCustomerInfos**

```javascript
const customerService = self.ctx.customerService;
const includeCustomers = true;
const customerId = 'your-customer-id';
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
customerService.getCustomerCustomerInfos(includeCustomers, customerId, pageLink).subscribe(customerCustomerInfos => {
  console.log('List of Customer Customer Infos:', customerCustomerInfos);
});
```

**9. getShortCustomerInfo**

```javascript
const customerService = self.ctx.customerService;
const customerId = 'your-customer-id';
customerService.getShortCustomerInfo(customerId).subscribe(shortCustomerInfo => {
  console.log('Get Short Customer Info:', shortCustomerInfo);
});
```

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
const dashboardReportService = self.ctx.reportService;
const result = dashboardReportService.loadReportParams();
console.log('Result:', result);
```

**2. onWaitForMap**

```javascript
const dashboardReportService = self.ctx.reportService;
const result = dashboardReportService.onWaitForMap();
console.log('Result:', result);
```

**3. onWaitForWidget**

```javascript
const dashboardReportService = self.ctx.reportService;
const result = dashboardReportService.onWaitForWidget();
console.log('Result:', result);
```

**4. onMapLoaded**

```javascript
const dashboardReportService = self.ctx.reportService;
const uuid = 'your-uuid';
const result = dashboardReportService.onMapLoaded(uuid);
console.log('Result:', result);
```

**5. onWidgetLoaded**

```javascript
const dashboardReportService = self.ctx.reportService;
const uuid = 'your-uuid';
const result = dashboardReportService.onWidgetLoaded(uuid);
console.log('Result:', result);
```

**6. downloadDashboardReport**

```javascript
const dashboardReportService = self.ctx.reportService;
const dashboardId = 'your-dashboard-id';
const reportType = {  // DashboardReportType object
  // ... set the fields you need
};
const state = 'state-value';
const timewindow = {  // Timewindow object
  // ... set the fields you need
};
dashboardReportService.downloadDashboardReport(dashboardId, reportType, state, timewindow).subscribe(downloadDashboardReport => {
  console.log('Download Dashboard Report:', downloadDashboardReport);
});
```

**7. downloadTestReport**

```javascript
const dashboardReportService = self.ctx.reportService;
const reportConfig = {  // DashboardReportParams object
  // ... set the fields you need
};
const reportsServerEndpointUrl = 'your-reports-server-endpoint-url';
dashboardReportService.downloadTestReport(reportConfig, reportsServerEndpointUrl).subscribe(downloadTestReport => {
  console.log('Download Test Report:', downloadTestReport);
});
```

**8. openReport**

```javascript
const dashboardReportService = self.ctx.reportService;
const openReportMessage = {  // OpenReportMessage object
  // ... set the fields you need
};
dashboardReportService.openReport(openReportMessage).subscribe(openReport => {
  console.log('Open Report:', openReport);
});
```

**9. pageHeight**

```javascript
const dashboardReportService = self.ctx.reportService;
const result = dashboardReportService.pageHeight();
console.log('Result:', result);
```

**10. waitForLayoutReady**

```javascript
const dashboardReportService = self.ctx.reportService;
dashboardReportService.waitForLayoutReady().subscribe(waitForLayoutReady => {
  console.log('Wait For Layout Ready:', waitForLayoutReady);
});
```

**11. waitForReportPage**

```javascript
const dashboardReportService = self.ctx.reportService;
const result = dashboardReportService.waitForReportPage();
console.log('Result:', result);
```

**12. waitForWebsocketData**

```javascript
const dashboardReportService = self.ctx.reportService;
const result = dashboardReportService.waitForWebsocketData();
console.log('Result:', result);
```

**13. waitWidgets**

```javascript
const dashboardReportService = self.ctx.reportService;
dashboardReportService.waitWidgets().subscribe(waitWidgets => {
  console.log('Wait Widgets:', waitWidgets);
});
```

**14. waitForWidgetsLoaded**

```javascript
const dashboardReportService = self.ctx.reportService;
const result = dashboardReportService.waitForWidgetsLoaded();
console.log('Result:', result);
```

**15. isReportPageDomReady**

```javascript
const dashboardReportService = self.ctx.reportService;
const result = dashboardReportService.isReportPageDomReady();
console.log('Result:', result);
```

**16. clearReport**

```javascript
const dashboardReportService = self.ctx.reportService;
dashboardReportService.clearReport().subscribe(clearReport => {
  console.log('Clear Report:', clearReport);
});
```

**17. loadUser**

```javascript
const dashboardReportService = self.ctx.reportService;
const accessToken = 'your-access-token';
const publicId = 'your-public-id';
dashboardReportService.loadUser(accessToken, publicId).subscribe(user => {
  console.log('Load User:', user);
});
```

**18. downloadReport**

```javascript
const dashboardReportService = self.ctx.reportService;
const url = 'your-url';
const reportParams = {  // DashboardReportParams object
  // ... set the fields you need
};
const params = 'value';
dashboardReportService.downloadReport(url, reportParams, params).subscribe(downloadReport => {
  console.log('Download Report:', downloadReport);
});
```

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
const dashboardService = self.ctx.dashboardService;
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
dashboardService.getTenantDashboards(pageLink).subscribe(tenantDashboards => {
  console.log('List of Tenant Dashboards:', tenantDashboards);
});
```

**2. getTenantDashboardsByTenantId**

```javascript
const dashboardService = self.ctx.dashboardService;
const tenantId = 'your-tenant-id';
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
dashboardService.getTenantDashboardsByTenantId(tenantId, pageLink).subscribe(tenantDashboardsByTenants => {
  console.log('List of Tenant Dashboards By Tenant Ids:', tenantDashboardsByTenants);
});
```

**3. getDashboards**

```javascript
const dashboardService = self.ctx.dashboardService;
const dashboardIds = ['your-dashboard-i-1', 'your-dashboard-i-2'];
dashboardService.getDashboards(dashboardIds).subscribe(dashboards => {
  console.log('List of Dashboards:', dashboards);
});
```

**4. getUserDashboards**

```javascript
const dashboardService = self.ctx.dashboardService;
const userId = 'your-user-id';
const operation = {  // Operation object
  // ... set the fields you need
};
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
dashboardService.getUserDashboards(userId, operation, pageLink).subscribe(userDashboards => {
  console.log('List of User Dashboards:', userDashboards);
});
```

**5. getAllDashboards**

```javascript
const dashboardService = self.ctx.dashboardService;
const includeCustomers = true;
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
dashboardService.getAllDashboards(includeCustomers, pageLink).subscribe(allDashboards => {
  console.log('List of All Dashboards:', allDashboards);
});
```

**6. getCustomerDashboards**

```javascript
const dashboardService = self.ctx.dashboardService;
const includeCustomers = true;
const customerId = 'your-customer-id';
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
dashboardService.getCustomerDashboards(includeCustomers, customerId, pageLink).subscribe(customerDashboards => {
  console.log('List of Customer Dashboards:', customerDashboards);
});
```

**7. getGroupDashboards**

```javascript
const dashboardService = self.ctx.dashboardService;
const groupId = 'your-group-id';
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
dashboardService.getGroupDashboards(groupId, pageLink).subscribe(groupDashboards => {
  console.log('List of Group Dashboards:', groupDashboards);
});
```

**8. getDashboard**

```javascript
const dashboardService = self.ctx.dashboardService;
const dashboardId = 'your-dashboard-id';
dashboardService.getDashboard(dashboardId).subscribe(dashboard => {
  console.log('Get Dashboard:', dashboard);
});
```

**9. exportDashboard**

```javascript
const dashboardService = self.ctx.dashboardService;
const dashboardId = 'your-dashboard-id';
dashboardService.exportDashboard(dashboardId).subscribe(exportDashboard => {
  console.log('Export Dashboard:', exportDashboard);
});
```

**10. getDashboardInfo**

```javascript
const dashboardService = self.ctx.dashboardService;
const dashboardId = 'your-dashboard-id';
dashboardService.getDashboardInfo(dashboardId).subscribe(dashboardInfo => {
  console.log('Get Dashboard Info:', dashboardInfo);
});
```

**11. saveDashboard**

```javascript
const dashboardService = self.ctx.dashboardService;
const dashboard = {  // Dashboard object
  // ... set the fields you need
};
const entityGroupIds = ['your-entity-group-i-1', 'your-entity-group-i-2'];
dashboardService.saveDashboard(dashboard, entityGroupIds).subscribe(savedDashboard => {
  console.log('Saved Dashboard:', savedDashboard);
});
```

**12. getPublicDashboardLink**

```javascript
const dashboardService = self.ctx.dashboardService;
const dashboard = 'dashboard';  // e.g. one of the allowed DashboardInfo
const entityGroup = {  // EntityGroup object
  // ... set the fields you need
};
const result = dashboardService.getPublicDashboardLink(dashboard, entityGroup);
console.log('Result:', result);
```

### **DEVICE PROFILE SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const deviceProfileService = $injector.get(self.ctx.servicesMap.get('deviceProfileService'));
```

**1. getDeviceProfiles**

```javascript
const $injector = self.ctx.$scope.$injector;
const deviceProfileService = $injector.get(self.ctx.servicesMap.get('deviceProfileService'));
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
deviceProfileService.getDeviceProfiles(pageLink).subscribe(deviceProfiles => {
  console.log('List of Device Profiles:', deviceProfiles);
});
```

**2. getDeviceProfile**

```javascript
const $injector = self.ctx.$scope.$injector;
const deviceProfileService = $injector.get(self.ctx.servicesMap.get('deviceProfileService'));
const deviceProfileId = 'your-device-profile-id';
deviceProfileService.getDeviceProfile(deviceProfileId).subscribe(deviceProfile => {
  console.log('Get Device Profile:', deviceProfile);
});
```

**3. exportDeviceProfile**

```javascript
const $injector = self.ctx.$scope.$injector;
const deviceProfileService = $injector.get(self.ctx.servicesMap.get('deviceProfileService'));
const deviceProfileId = 'your-device-profile-id';
deviceProfileService.exportDeviceProfile(deviceProfileId).subscribe(exportDeviceProfile => {
  console.log('Export Device Profile:', exportDeviceProfile);
});
```

**4. getLwm2mObjects**

```javascript
const $injector = self.ctx.$scope.$injector;
const deviceProfileService = $injector.get(self.ctx.servicesMap.get('deviceProfileService'));
const sortOrder = {  // SortOrder object
  // ... set the fields you need
};
const objectIds = ['your-object-i-1', 'your-object-i-2'];
const searchText = 'searchText';
deviceProfileService.getLwm2mObjects(sortOrder, objectIds, searchText).subscribe(lwm2mObjects => {
  console.log('List of Lwm2m Objects:', lwm2mObjects);
});
```

**5. getLwm2mBootstrapSecurityInfo**

```javascript
const $injector = self.ctx.$scope.$injector;
const deviceProfileService = $injector.get(self.ctx.servicesMap.get('deviceProfileService'));
const isBootstrapServer = true;
deviceProfileService.getLwm2mBootstrapSecurityInfo(isBootstrapServer).subscribe(lwm2mBootstrapSecurityInfo => {
  console.log('Get Lwm2m Bootstrap Security Info:', lwm2mBootstrapSecurityInfo);
});
```

**6. getLwm2mBootstrapSecurityInfoBySecurityType**

```javascript
const $injector = self.ctx.$scope.$injector;
const deviceProfileService = $injector.get(self.ctx.servicesMap.get('deviceProfileService'));
const isBootstrapServer = true;
deviceProfileService.getLwm2mBootstrapSecurityInfoBySecurityType(isBootstrapServer).subscribe(lwm2mBootstrapSecurityInfoBySecurityType => {
  console.log('Get Lwm2m Bootstrap Security Info By Security Type:', lwm2mBootstrapSecurityInfoBySecurityType);
});
```

**7. getLwm2mObjectsPage**

```javascript
const $injector = self.ctx.$scope.$injector;
const deviceProfileService = $injector.get(self.ctx.servicesMap.get('deviceProfileService'));
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
deviceProfileService.getLwm2mObjectsPage(pageLink).subscribe(lwm2mObjectsPages => {
  console.log('List of Lwm2m Objects Pages:', lwm2mObjectsPages);
});
```

**8. saveDeviceProfileAndConfirmOtaChange**

```javascript
const $injector = self.ctx.$scope.$injector;
const deviceProfileService = $injector.get(self.ctx.servicesMap.get('deviceProfileService'));
const originDeviceProfile = {  // DeviceProfile object
  // ... set the fields you need
};
const deviceProfile = {  // DeviceProfile object
  // ... set the fields you need
};
deviceProfileService.saveDeviceProfileAndConfirmOtaChange(originDeviceProfile, deviceProfile).subscribe(savedDeviceProfileAndConfirmOtaChange => {
  console.log('Saved Device Profile And Confirm Ota Change:', savedDeviceProfileAndConfirmOtaChange);
});
```

**9. saveDeviceProfile**

```javascript
const $injector = self.ctx.$scope.$injector;
const deviceProfileService = $injector.get(self.ctx.servicesMap.get('deviceProfileService'));
const result = deviceProfileService.saveDeviceProfile();
console.log('Result:', result);
```

**10. setDefaultDeviceProfile**

```javascript
const $injector = self.ctx.$scope.$injector;
const deviceProfileService = $injector.get(self.ctx.servicesMap.get('deviceProfileService'));
const deviceProfileId = 'your-device-profile-id';
deviceProfileService.setDefaultDeviceProfile(deviceProfileId).subscribe(setDefaultDeviceProfile => {
  console.log('Set Default Device Profile:', setDefaultDeviceProfile);
});
```

**11. getDefaultDeviceProfileInfo**

```javascript
const $injector = self.ctx.$scope.$injector;
const deviceProfileService = $injector.get(self.ctx.servicesMap.get('deviceProfileService'));
deviceProfileService.getDefaultDeviceProfileInfo().subscribe(defaultDeviceProfileInfo => {
  console.log('Get Default Device Profile Info:', defaultDeviceProfileInfo);
});
```

**12. getDeviceProfileInfo**

```javascript
const $injector = self.ctx.$scope.$injector;
const deviceProfileService = $injector.get(self.ctx.servicesMap.get('deviceProfileService'));
const deviceProfileId = 'your-device-profile-id';
deviceProfileService.getDeviceProfileInfo(deviceProfileId).subscribe(deviceProfileInfo => {
  console.log('Get Device Profile Info:', deviceProfileInfo);
});
```

**13. getDeviceProfileInfos**

```javascript
const $injector = self.ctx.$scope.$injector;
const deviceProfileService = $injector.get(self.ctx.servicesMap.get('deviceProfileService'));
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const transportType = {  // DeviceTransportType object
  // ... set the fields you need
};
deviceProfileService.getDeviceProfileInfos(pageLink, transportType).subscribe(deviceProfileInfos => {
  console.log('List of Device Profile Infos:', deviceProfileInfos);
});
```

**14. getDeviceProfilesByIds**

```javascript
const $injector = self.ctx.$scope.$injector;
const deviceProfileService = $injector.get(self.ctx.servicesMap.get('deviceProfileService'));
const deviceProfileIds = ['your-device-profile-i-1', 'your-device-profile-i-2'];
deviceProfileService.getDeviceProfilesByIds(deviceProfileIds).subscribe(deviceProfilesBys => {
  console.log('List of Device Profiles By Ids:', deviceProfilesBys);
});
```

**15. getDeviceProfileDevicesAttributesKeys**

```javascript
const $injector = self.ctx.$scope.$injector;
const deviceProfileService = $injector.get(self.ctx.servicesMap.get('deviceProfileService'));
const deviceProfileId = 'your-device-profile-id';
deviceProfileService.getDeviceProfileDevicesAttributesKeys(deviceProfileId).subscribe(deviceProfileDevicesAttributesKeys => {
  console.log('List of Device Profile Devices Attributes Keys:', deviceProfileDevicesAttributesKeys);
});
```

**16. getDeviceProfileDevicesTimeseriesKeys**

```javascript
const $injector = self.ctx.$scope.$injector;
const deviceProfileService = $injector.get(self.ctx.servicesMap.get('deviceProfileService'));
const deviceProfileId = 'your-device-profile-id';
deviceProfileService.getDeviceProfileDevicesTimeseriesKeys(deviceProfileId).subscribe(deviceProfileDevicesTimeseriesKeys => {
  console.log('List of Device Profile Devices Timeseries Keys:', deviceProfileDevicesTimeseriesKeys);
});
```

**17. getDeviceProfileNames**

```javascript
const $injector = self.ctx.$scope.$injector;
const deviceProfileService = $injector.get(self.ctx.servicesMap.get('deviceProfileService'));
const activeOnly = 'value';
deviceProfileService.getDeviceProfileNames(activeOnly).subscribe(deviceProfileNames => {
  console.log('List of Device Profile Names:', deviceProfileNames);
});
```

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
const deviceService = self.ctx.deviceService;
const deviceInfoQuery = {  // DeviceInfoQuery object
  // ... set the fields you need
};
deviceService.getDeviceInfosByQuery(deviceInfoQuery).subscribe(deviceInfosByQuerys => {
  console.log('List of Device Infos By Querys:', deviceInfosByQuerys);
});
```

**2. getTenantDevices**

```javascript
const deviceService = self.ctx.deviceService;
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const type = 'value';
deviceService.getTenantDevices(pageLink, type).subscribe(tenantDevices => {
  console.log('List of Tenant Devices:', tenantDevices);
});
```

**3. getCustomerDevices**

```javascript
const deviceService = self.ctx.deviceService;
const customerId = 'your-customer-id';
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const type = 'value';
deviceService.getCustomerDevices(customerId, pageLink, type).subscribe(customerDevices => {
  console.log('List of Customer Devices:', customerDevices);
});
```

**4. getDevice**

```javascript
const deviceService = self.ctx.deviceService;
const deviceId = 'your-device-id';
deviceService.getDevice(deviceId).subscribe(device => {
  console.log('Get Device:', device);
});
```

**5. getDevices**

```javascript
const deviceService = self.ctx.deviceService;
const deviceIds = ['your-device-i-1', 'your-device-i-2'];
deviceService.getDevices(deviceIds).subscribe(devices => {
  console.log('List of Devices:', devices);
});
```

**6. getUserDevices**

```javascript
const deviceService = self.ctx.deviceService;
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const type = 'value';
deviceService.getUserDevices(pageLink, type).subscribe(userDevices => {
  console.log('List of User Devices:', userDevices);
});
```

**7. getAllDeviceInfos**

```javascript
const deviceService = self.ctx.deviceService;
const includeCustomers = true;
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const deviceProfileId = 'value';
deviceService.getAllDeviceInfos(includeCustomers, pageLink, deviceProfileId).subscribe(allDeviceInfos => {
  console.log('List of All Device Infos:', allDeviceInfos);
});
```

**8. getCustomerDeviceInfos**

```javascript
const deviceService = self.ctx.deviceService;
const includeCustomers = true;
const customerId = 'your-customer-id';
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const deviceProfileId = 'value';
deviceService.getCustomerDeviceInfos(includeCustomers, customerId, pageLink, deviceProfileId).subscribe(customerDeviceInfos => {
  console.log('List of Customer Device Infos:', customerDeviceInfos);
});
```

**9. getDeviceInfo**

```javascript
const deviceService = self.ctx.deviceService;
const deviceId = 'your-device-id';
deviceService.getDeviceInfo(deviceId).subscribe(deviceInfo => {
  console.log('Get Device Info:', deviceInfo);
});
```

**10. saveDevice**

```javascript
const deviceService = self.ctx.deviceService;
const device = {  // Device object
  // ... set the fields you need
};
const entityGroupIds = ['your-entity-group-i-1', 'your-entity-group-i-2'];
const result = deviceService.saveDevice(device, entityGroupIds);
console.log('Result:', result);
```

**11. saveDeviceWithCredentials**

```javascript
const deviceService = self.ctx.deviceService;
const device = {  // Device object
  // ... set the fields you need
};
const credentials = {  // DeviceCredentials object
  // ... set the fields you need
};
const entityGroupIds = ['your-entity-group-i-1', 'your-entity-group-i-2'];
const result = deviceService.saveDeviceWithCredentials(device, credentials, entityGroupIds);
console.log('Result:', result);
```

**12. getDeviceTypes**

```javascript
const deviceService = self.ctx.deviceService;
deviceService.getDeviceTypes().subscribe(deviceTypes => {
  console.log('List of Device Types:', deviceTypes);
});
```

**13. getDeviceCredentials**

```javascript
const deviceService = self.ctx.deviceService;
const deviceId = 'your-device-id';
const sync = 'value';
deviceService.getDeviceCredentials(deviceId, sync).subscribe(deviceCredentials => {
  console.log('Get Device Credentials:', deviceCredentials);
});
```

### **DOMAIN SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const domainService = $injector.get(self.ctx.servicesMap.get('domainService'));
```

**1. saveDomain**

```javascript
const $injector = self.ctx.$scope.$injector;
const domainService = $injector.get(self.ctx.servicesMap.get('domainService'));
const domain = {  // Domain object
  // ... set the fields you need
};
const oauth2ClientIds = ['your-oauth2-client-i-1', 'your-oauth2-client-i-2'];
domainService.saveDomain(domain, oauth2ClientIds).subscribe(savedDomain => {
  console.log('Saved Domain:', savedDomain);
});
```

**2. updateOauth2Clients**

```javascript
const $injector = self.ctx.$scope.$injector;
const domainService = $injector.get(self.ctx.servicesMap.get('domainService'));
const id = 'your-id';
const oauth2ClientIds = ['your-oauth2-client-i-1', 'your-oauth2-client-i-2'];
domainService.updateOauth2Clients(id, oauth2ClientIds).subscribe(savedOauth2Clients => {
  console.log('Saved Oauth2 Clients:', savedOauth2Clients);
});
```

**3. getDomainInfos**

```javascript
const $injector = self.ctx.$scope.$injector;
const domainService = $injector.get(self.ctx.servicesMap.get('domainService'));
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
domainService.getDomainInfos(pageLink).subscribe(domainInfos => {
  console.log('List of Domain Infos:', domainInfos);
});
```

**4. getDomainInfoById**

```javascript
const $injector = self.ctx.$scope.$injector;
const domainService = $injector.get(self.ctx.servicesMap.get('domainService'));
const id = 'your-id';
domainService.getDomainInfoById(id).subscribe(domainInfoBy => {
  console.log('Get Domain Info By Id:', domainInfoBy);
});
```

**5. deleteDomain**

```javascript
const $injector = self.ctx.$scope.$injector;
const domainService = $injector.get(self.ctx.servicesMap.get('domainService'));
const id = 'your-id';
domainService.deleteDomain(id).subscribe(result => {
  console.log('Delete Domain result:', result);
});
```

### **EDGE SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const edgeService = $injector.get(self.ctx.servicesMap.get('edgeService'));
```

**1. getEdges**

```javascript
const $injector = self.ctx.$scope.$injector;
const edgeService = $injector.get(self.ctx.servicesMap.get('edgeService'));
const edgeIds = ['your-edge-i-1', 'your-edge-i-2'];
edgeService.getEdges(edgeIds).subscribe(edges => {
  console.log('List of Edges:', edges);
});
```

**2. getEdge**

```javascript
const $injector = self.ctx.$scope.$injector;
const edgeService = $injector.get(self.ctx.servicesMap.get('edgeService'));
const edgeId = 'your-edge-id';
edgeService.getEdge(edgeId).subscribe(edge => {
  console.log('Get Edge:', edge);
});
```

**3. getEdgeInfo**

```javascript
const $injector = self.ctx.$scope.$injector;
const edgeService = $injector.get(self.ctx.servicesMap.get('edgeService'));
const edgeId = 'your-edge-id';
edgeService.getEdgeInfo(edgeId).subscribe(edgeInfo => {
  console.log('Get Edge Info:', edgeInfo);
});
```

**4. saveEdge**

```javascript
const $injector = self.ctx.$scope.$injector;
const edgeService = $injector.get(self.ctx.servicesMap.get('edgeService'));
const edge = {  // Edge object
  // ... set the fields you need
};
const entityGroupIds = ['your-entity-group-i-1', 'your-entity-group-i-2'];
edgeService.saveEdge(edge, entityGroupIds).subscribe(savedEdge => {
  console.log('Saved Edge:', savedEdge);
});
```

**5. getEdgeTypes**

```javascript
const $injector = self.ctx.$scope.$injector;
const edgeService = $injector.get(self.ctx.servicesMap.get('edgeService'));
edgeService.getEdgeTypes().subscribe(edgeTypes => {
  console.log('List of Edge Types:', edgeTypes);
});
```

**6. assignEdgeToCustomer**

```javascript
const $injector = self.ctx.$scope.$injector;
const edgeService = $injector.get(self.ctx.servicesMap.get('edgeService'));
const customerId = 'your-customer-id';
const edgeId = 'your-edge-id';
edgeService.assignEdgeToCustomer(customerId, edgeId).subscribe(assignEdgeToCustomer => {
  console.log('Assign Edge To Customer:', assignEdgeToCustomer);
});
```

**7. makeEdgePublic**

```javascript
const $injector = self.ctx.$scope.$injector;
const edgeService = $injector.get(self.ctx.servicesMap.get('edgeService'));
const edgeId = 'your-edge-id';
edgeService.makeEdgePublic(edgeId).subscribe(makeEdgePublic => {
  console.log('Make Edge Public:', makeEdgePublic);
});
```

**8. getTenantEdges**

```javascript
const $injector = self.ctx.$scope.$injector;
const edgeService = $injector.get(self.ctx.servicesMap.get('edgeService'));
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const type = 'value';
edgeService.getTenantEdges(pageLink, type).subscribe(tenantEdges => {
  console.log('List of Tenant Edges:', tenantEdges);
});
```

**9. getTenantEdgeInfos**

```javascript
const $injector = self.ctx.$scope.$injector;
const edgeService = $injector.get(self.ctx.servicesMap.get('edgeService'));
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const type = 'value';
edgeService.getTenantEdgeInfos(pageLink, type).subscribe(tenantEdgeInfos => {
  console.log('List of Tenant Edge Infos:', tenantEdgeInfos);
});
```

**10. getUserEdges**

```javascript
const $injector = self.ctx.$scope.$injector;
const edgeService = $injector.get(self.ctx.servicesMap.get('edgeService'));
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const type = 'value';
edgeService.getUserEdges(pageLink, type).subscribe(userEdges => {
  console.log('List of User Edges:', userEdges);
});
```

**11. getAllEdgeInfos**

```javascript
const $injector = self.ctx.$scope.$injector;
const edgeService = $injector.get(self.ctx.servicesMap.get('edgeService'));
const includeCustomers = true;
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const type = 'value';
edgeService.getAllEdgeInfos(includeCustomers, pageLink, type).subscribe(allEdgeInfos => {
  console.log('List of All Edge Infos:', allEdgeInfos);
});
```

**12. getCustomerEdgeInfos**

```javascript
const $injector = self.ctx.$scope.$injector;
const edgeService = $injector.get(self.ctx.servicesMap.get('edgeService'));
const includeCustomers = true;
const customerId = 'your-customer-id';
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const type = 'value';
edgeService.getCustomerEdgeInfos(includeCustomers, customerId, pageLink, type).subscribe(customerEdgeInfos => {
  console.log('List of Customer Edge Infos:', customerEdgeInfos);
});
```

**13. findByQuery**

```javascript
const $injector = self.ctx.$scope.$injector;
const edgeService = $injector.get(self.ctx.servicesMap.get('edgeService'));
const query = {  // EdgeSearchQuery object
  // ... set the fields you need
};
edgeService.findByQuery(query).subscribe(byQuerys => {
  console.log('List of By Querys:', byQuerys);
});
```

**14. getEdgeEvents**

```javascript
const $injector = self.ctx.$scope.$injector;
const edgeService = $injector.get(self.ctx.servicesMap.get('edgeService'));
const entityId = {  // EntityId object
  // ... set the fields you need
};
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
edgeService.getEdgeEvents(entityId, pageLink).subscribe(edgeEvents => {
  console.log('List of Edge Events:', edgeEvents);
});
```

**15. findMissingToRelatedRuleChains**

```javascript
const $injector = self.ctx.$scope.$injector;
const edgeService = $injector.get(self.ctx.servicesMap.get('edgeService'));
const edgeId = 'your-edge-id';
edgeService.findMissingToRelatedRuleChains(edgeId).subscribe(missingToRelatedRuleChains => {
  console.log('Find Missing To Related Rule Chains:', missingToRelatedRuleChains);
});
```

**16. findByName**

```javascript
const $injector = self.ctx.$scope.$injector;
const edgeService = $injector.get(self.ctx.servicesMap.get('edgeService'));
const edgeName = 'your-edge-name';
edgeService.findByName(edgeName).subscribe(byName => {
  console.log('Find By Name:', byName);
});
```

**17. bulkImportEdges**

```javascript
const $injector = self.ctx.$scope.$injector;
const edgeService = $injector.get(self.ctx.servicesMap.get('edgeService'));
const entitiesData = {  // BulkImportRequest object
  // ... set the fields you need
};
edgeService.bulkImportEdges(entitiesData).subscribe(bulkImportEdges => {
  console.log('Bulk Import Edges:', bulkImportEdges);
});
```

**18. getEdgeInstallInstructions**

```javascript
const $injector = self.ctx.$scope.$injector;
const edgeService = $injector.get(self.ctx.servicesMap.get('edgeService'));
const edgeId = 'your-edge-id';
const method = 'value';
edgeService.getEdgeInstallInstructions(edgeId, method).subscribe(edgeInstallInstructions => {
  console.log('Get Edge Install Instructions:', edgeInstallInstructions);
});
```

**19. getEdgeUpgradeInstructions**

```javascript
const $injector = self.ctx.$scope.$injector;
const edgeService = $injector.get(self.ctx.servicesMap.get('edgeService'));
const edgeVersion = 'your-edge-version';
const method = 'value';
edgeService.getEdgeUpgradeInstructions(edgeVersion, method).subscribe(edgeUpgradeInstructions => {
  console.log('Get Edge Upgrade Instructions:', edgeUpgradeInstructions);
});
```

**20. findAllRelatedEdgesMissingAttributes**

```javascript
const $injector = self.ctx.$scope.$injector;
const edgeService = $injector.get(self.ctx.servicesMap.get('edgeService'));
const integrationId = 'your-integration-id';
edgeService.findAllRelatedEdgesMissingAttributes(integrationId).subscribe(allRelatedEdgesMissingAttributes => {
  console.log('Find All Related Edges Missing Attributes:', allRelatedEdgesMissingAttributes);
});
```

**21. findEdgeMissingAttributes**

```javascript
const $injector = self.ctx.$scope.$injector;
const edgeService = $injector.get(self.ctx.servicesMap.get('edgeService'));
const integrationIds = ['your-integration-i-1', 'your-integration-i-2'];
const edgeId = 'your-edge-id';
edgeService.findEdgeMissingAttributes(integrationIds, edgeId).subscribe(edgeMissingAttributes => {
  console.log('Find Edge Missing Attributes:', edgeMissingAttributes);
});
```

**22. isEdgeUpgradeAvailable**

```javascript
const $injector = self.ctx.$scope.$injector;
const edgeService = $injector.get(self.ctx.servicesMap.get('edgeService'));
const edgeId = 'your-edge-id';
edgeService.isEdgeUpgradeAvailable(edgeId).subscribe(isEdgeUpgradeAvailable => {
  console.log('Is Edge Upgrade Available:', isEdgeUpgradeAvailable);
});
```

### **ENTITIES VERSION CONTROL SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const entitiesVersionControlService = $injector.get(self.ctx.servicesMap.get('entitiesVersionControlService'));
```

**1. clearBranchList**

```javascript
const $injector = self.ctx.$scope.$injector;
const entitiesVersionControlService = $injector.get(self.ctx.servicesMap.get('entitiesVersionControlService'));
const result = entitiesVersionControlService.clearBranchList();
console.log('Result:', result);
```

**2. listBranches**

```javascript
const $injector = self.ctx.$scope.$injector;
const entitiesVersionControlService = $injector.get(self.ctx.servicesMap.get('entitiesVersionControlService'));
entitiesVersionControlService.listBranches().subscribe(listBranches => {
  console.log('List Branches:', listBranches);
});
```

**3. getEntityDataInfo**

```javascript
const $injector = self.ctx.$scope.$injector;
const entitiesVersionControlService = $injector.get(self.ctx.servicesMap.get('entitiesVersionControlService'));
const externalEntityId = {  // EntityId object
  // ... set the fields you need
};
const internalEntityId = {  // EntityId object
  // ... set the fields you need
};
const versionId = 'your-version-id';
entitiesVersionControlService.getEntityDataInfo(externalEntityId, internalEntityId, versionId).subscribe(entityDataInfo => {
  console.log('Get Entity Data Info:', entityDataInfo);
});
```

**4. saveEntitiesVersion**

```javascript
const $injector = self.ctx.$scope.$injector;
const entitiesVersionControlService = $injector.get(self.ctx.servicesMap.get('entitiesVersionControlService'));
const request = {  // VersionCreateRequest object
  // ... set the fields you need
};
entitiesVersionControlService.saveEntitiesVersion(request).subscribe(savedEntitiesVersion => {
  console.log('Saved Entities Version:', savedEntitiesVersion);
});
```

**5. getVersionCreateRequestStatus**

```javascript
const $injector = self.ctx.$scope.$injector;
const entitiesVersionControlService = $injector.get(self.ctx.servicesMap.get('entitiesVersionControlService'));
const requestId = 'your-request-id';
entitiesVersionControlService.getVersionCreateRequestStatus(requestId).subscribe(versionCreateRequestStatus => {
  console.log('Get Version Create Request Status:', versionCreateRequestStatus);
});
```

**6. listEntityVersions**

```javascript
const $injector = self.ctx.$scope.$injector;
const entitiesVersionControlService = $injector.get(self.ctx.servicesMap.get('entitiesVersionControlService'));
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const branch = 'your-branch';
const externalEntityId = {  // EntityId object
  // ... set the fields you need
};
const internalEntityId = {  // EntityId object
  // ... set the fields you need
};
entitiesVersionControlService.listEntityVersions(pageLink, branch, externalEntityId, internalEntityId).subscribe(listEntityVersions => {
  console.log('List Entity Versions:', listEntityVersions);
});
```

**7. listEntityTypeVersions**

```javascript
const $injector = self.ctx.$scope.$injector;
const entitiesVersionControlService = $injector.get(self.ctx.servicesMap.get('entitiesVersionControlService'));
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const branch = 'your-branch';
const entityType = {  // EntityType object
  // ... set the fields you need
};
entitiesVersionControlService.listEntityTypeVersions(pageLink, branch, entityType).subscribe(listEntityTypeVersions => {
  console.log('List Entity Type Versions:', listEntityTypeVersions);
});
```

**8. listVersions**

```javascript
const $injector = self.ctx.$scope.$injector;
const entitiesVersionControlService = $injector.get(self.ctx.servicesMap.get('entitiesVersionControlService'));
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const branch = 'your-branch';
entitiesVersionControlService.listVersions(pageLink, branch).subscribe(listVersions => {
  console.log('List Versions:', listVersions);
});
```

**9. loadEntitiesVersion**

```javascript
const $injector = self.ctx.$scope.$injector;
const entitiesVersionControlService = $injector.get(self.ctx.servicesMap.get('entitiesVersionControlService'));
const request = {  // VersionLoadRequest object
  // ... set the fields you need
};
entitiesVersionControlService.loadEntitiesVersion(request).subscribe(entitiesVersion => {
  console.log('Load Entities Version:', entitiesVersion);
});
```

**10. getVersionLoadRequestStatus**

```javascript
const $injector = self.ctx.$scope.$injector;
const entitiesVersionControlService = $injector.get(self.ctx.servicesMap.get('entitiesVersionControlService'));
const requestId = 'your-request-id';
entitiesVersionControlService.getVersionLoadRequestStatus(requestId).subscribe(versionLoadRequestStatus => {
  console.log('Get Version Load Request Status:', versionLoadRequestStatus);
});
```

**11. compareEntityDataToVersion**

```javascript
const $injector = self.ctx.$scope.$injector;
const entitiesVersionControlService = $injector.get(self.ctx.servicesMap.get('entitiesVersionControlService'));
const entityId = {  // EntityId object
  // ... set the fields you need
};
const versionId = 'your-version-id';
entitiesVersionControlService.compareEntityDataToVersion(entityId, versionId).subscribe(compareEntityDataToVersion => {
  console.log('Compare Entity Data To Version:', compareEntityDataToVersion);
});
```

**12. entityLoadErrorToMessage**

```javascript
const $injector = self.ctx.$scope.$injector;
const entitiesVersionControlService = $injector.get(self.ctx.servicesMap.get('entitiesVersionControlService'));
const entityLoadError = {  // EntityLoadError object
  // ... set the fields you need
};
const result = entitiesVersionControlService.entityLoadErrorToMessage(entityLoadError);
console.log('Result:', result);
```

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
const entityGroupService = self.ctx.entityGroupService;
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
entityGroupService.getOwners(pageLink).subscribe(owners => {
  console.log('List of Owners:', owners);
});
```

**2. getOwnerInfos**

```javascript
const entityGroupService = self.ctx.entityGroupService;
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
entityGroupService.getOwnerInfos(pageLink).subscribe(ownerInfos => {
  console.log('List of Owner Infos:', ownerInfos);
});
```

**3. getOwnerInfo**

```javascript
const entityGroupService = self.ctx.entityGroupService;
const ownerId = {  // EntityId object
  // ... set the fields you need
};
entityGroupService.getOwnerInfo(ownerId).subscribe(ownerInfo => {
  console.log('Get Owner Info:', ownerInfo);
});
```

**4. getEntityGroup**

```javascript
const entityGroupService = self.ctx.entityGroupService;
const entityGroupId = 'your-entity-group-id';
entityGroupService.getEntityGroup(entityGroupId).subscribe(entityGroup => {
  console.log('Get Entity Group:', entityGroup);
});
```

**5. getDeviceEntityGroup**

```javascript
const entityGroupService = self.ctx.entityGroupService;
const entityGroupId = 'your-entity-group-id';
entityGroupService.getDeviceEntityGroup(entityGroupId).subscribe(deviceEntityGroup => {
  console.log('Get Device Entity Group:', deviceEntityGroup);
});
```

**6. fetchOtaPackageGroupInfo**

```javascript
const entityGroupService = self.ctx.entityGroupService;
const group = {  // EntityGroupInfo object
  // ... set the fields you need
};
entityGroupService.fetchOtaPackageGroupInfo(group).subscribe(otaPackageGroupInfo => {
  console.log('Fetch Ota Package Group Info:', otaPackageGroupInfo);
});
```

**7. updateDeviceGroupOtaPackage**

```javascript
const entityGroupService = self.ctx.entityGroupService;
const deviceGroupOtaPackage = {  // DeviceGroupOtaPackage object
  // ... set the fields you need
};
const otaPackageId = 'otaPackageId';  // e.g. one of the allowed OtaPackageId
const groupId = {  // EntityGroupId object
  // ... set the fields you need
};
const otaPackageType = {  // OtaUpdateType object
  // ... set the fields you need
};
entityGroupService.updateDeviceGroupOtaPackage(deviceGroupOtaPackage, otaPackageId, groupId, otaPackageType).subscribe(savedDeviceGroupOtaPackage => {
  console.log('Saved Device Group Ota Package:', savedDeviceGroupOtaPackage);
});
```

**8. saveDeviceGroupOtaPackage**

```javascript
const entityGroupService = self.ctx.entityGroupService;
const deviceGroupOtaPackage = {  // DeviceGroupOtaPackage object
  // ... set the fields you need
};
entityGroupService.saveDeviceGroupOtaPackage(deviceGroupOtaPackage).subscribe(savedDeviceGroupOtaPackage => {
  console.log('Saved Device Group Ota Package:', savedDeviceGroupOtaPackage);
});
```

**9. saveDeviceEntityGroup**

```javascript
const entityGroupService = self.ctx.entityGroupService;
const entityGroup = {  // DeviceEntityGroupInfo object
  // ... set the fields you need
};
const originalEntityGroup = {  // DeviceEntityGroupInfo object
  // ... set the fields you need
};
entityGroupService.saveDeviceEntityGroup(entityGroup, originalEntityGroup).subscribe(savedDeviceEntityGroup => {
  console.log('Saved Device Entity Group:', savedDeviceEntityGroup);
});
```

**10. getEntityGroupEntityInfo**

```javascript
const entityGroupService = self.ctx.entityGroupService;
const entityGroupId = 'your-entity-group-id';
entityGroupService.getEntityGroupEntityInfo(entityGroupId).subscribe(entityGroupEntityInfo => {
  console.log('Get Entity Group Entity Info:', entityGroupEntityInfo);
});
```

**11. saveEntityGroup**

```javascript
const entityGroupService = self.ctx.entityGroupService;
const entityGroup = {  // EntityGroup object
  // ... set the fields you need
};
entityGroupService.saveEntityGroup(entityGroup).subscribe(savedEntityGroup => {
  console.log('Saved Entity Group:', savedEntityGroup);
});
```

**12. makeEntityGroupPublic**

```javascript
const entityGroupService = self.ctx.entityGroupService;
const entityGroupId = 'your-entity-group-id';
entityGroupService.makeEntityGroupPublic(entityGroupId).subscribe(makeEntityGroupPublic => {
  console.log('Make Entity Group Public:', makeEntityGroupPublic);
});
```

**13. makeEntityGroupPrivate**

```javascript
const entityGroupService = self.ctx.entityGroupService;
const entityGroupId = 'your-entity-group-id';
entityGroupService.makeEntityGroupPrivate(entityGroupId).subscribe(makeEntityGroupPrivate => {
  console.log('Make Entity Group Private:', makeEntityGroupPrivate);
});
```

**14. shareEntityGroup**

```javascript
const entityGroupService = self.ctx.entityGroupService;
const entityGroupId = 'your-entity-group-id';
const shareGroupRequest = {  // ShareGroupRequest object
  // ... set the fields you need
};
entityGroupService.shareEntityGroup(entityGroupId, shareGroupRequest).subscribe(shareEntityGroup => {
  console.log('Share Entity Group:', shareEntityGroup);
});
```

**15. shareEntityGroupV2**

```javascript
const entityGroupService = self.ctx.entityGroupService;
const entityGroupId = 'your-entity-group-id';
const shareGroupRequest = {  // ShareGroupRequest object
  // ... set the fields you need
};
entityGroupService.shareEntityGroupV2(entityGroupId, shareGroupRequest).subscribe(shareEntityGroupV2 => {
  console.log('Share Entity Group V2:', shareEntityGroupV2);
});
```

**16. getEntityGroups**

```javascript
const entityGroupService = self.ctx.entityGroupService;
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const groupType = {  // EntityType object
  // ... set the fields you need
};
entityGroupService.getEntityGroups(pageLink, groupType).subscribe(entityGroups => {
  console.log('List of Entity Groups:', entityGroups);
});
```

**17. getEntityGroupEntityInfos**

```javascript
const entityGroupService = self.ctx.entityGroupService;
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const groupType = {  // EntityType object
  // ... set the fields you need
};
entityGroupService.getEntityGroupEntityInfos(pageLink, groupType).subscribe(entityGroupEntityInfos => {
  console.log('List of Entity Group Entity Infos:', entityGroupEntityInfos);
});
```

**18. getAllEntityGroups**

```javascript
const entityGroupService = self.ctx.entityGroupService;
const pageSize = 10;
const groupType = {  // EntityType object
  // ... set the fields you need
};
entityGroupService.getAllEntityGroups(pageSize, groupType).subscribe(allEntityGroups => {
  console.log('List of All Entity Groups:', allEntityGroups);
});
```

**19. getAllEntityGroupsByPageLink**

```javascript
const entityGroupService = self.ctx.entityGroupService;
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const groupType = {  // EntityType object
  // ... set the fields you need
};
entityGroupService.getAllEntityGroupsByPageLink(pageLink, groupType).subscribe(allEntityGroupsByPageLinks => {
  console.log('List of All Entity Groups By Page Links:', allEntityGroupsByPageLinks);
});
```

**20. getSharedEntityGroups**

```javascript
const entityGroupService = self.ctx.entityGroupService;
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const groupType = {  // EntityType object
  // ... set the fields you need
};
entityGroupService.getSharedEntityGroups(pageLink, groupType).subscribe(sharedEntityGroups => {
  console.log('List of Shared Entity Groups:', sharedEntityGroups);
});
```

**21. getSharedEntityGroupEntityInfos**

```javascript
const entityGroupService = self.ctx.entityGroupService;
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const groupType = {  // EntityType object
  // ... set the fields you need
};
entityGroupService.getSharedEntityGroupEntityInfos(pageLink, groupType).subscribe(sharedEntityGroupEntityInfos => {
  console.log('List of Shared Entity Group Entity Infos:', sharedEntityGroupEntityInfos);
});
```

**22. getEntityGroupIdsForEntityId**

```javascript
const entityGroupService = self.ctx.entityGroupService;
const entityType = {  // EntityType object
  // ... set the fields you need
};
const entityId = 'your-entity-id';
entityGroupService.getEntityGroupIdsForEntityId(entityType, entityId).subscribe(entityGroupIdsForEntitys => {
  console.log('List of Entity Group Ids For Entity Ids:', entityGroupIdsForEntitys);
});
```

**23. getEntityGroupsByIds**

```javascript
const entityGroupService = self.ctx.entityGroupService;
const entityGroupIds = ['your-entity-group-i-1', 'your-entity-group-i-2'];
entityGroupService.getEntityGroupsByIds(entityGroupIds).subscribe(entityGroupsBys => {
  console.log('List of Entity Groups By Ids:', entityGroupsBys);
});
```

**24. getEntityGroupEntityInfosByIds**

```javascript
const entityGroupService = self.ctx.entityGroupService;
const entityGroupIds = ['your-entity-group-i-1', 'your-entity-group-i-2'];
entityGroupService.getEntityGroupEntityInfosByIds(entityGroupIds).subscribe(entityGroupEntityInfosBys => {
  console.log('List of Entity Group Entity Infos By Ids:', entityGroupEntityInfosBys);
});
```

**25. getEntityGroupsHierarchyByOwnerId**

```javascript
const entityGroupService = self.ctx.entityGroupService;
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const ownerType = {  // EntityType object
  // ... set the fields you need
};
const ownerId = 'your-owner-id';
const groupType = {  // EntityType object
  // ... set the fields you need
};
entityGroupService.getEntityGroupsHierarchyByOwnerId(pageLink, ownerType, ownerId, groupType).subscribe(entityGroupsHierarchyByOwners => {
  console.log('List of Entity Groups Hierarchy By Owner Ids:', entityGroupsHierarchyByOwners);
});
```

**26. getEntityGroupEntityInfosHierarchyByOwnerId**

```javascript
const entityGroupService = self.ctx.entityGroupService;
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const ownerType = {  // EntityType object
  // ... set the fields you need
};
const ownerId = 'your-owner-id';
const groupType = {  // EntityType object
  // ... set the fields you need
};
entityGroupService.getEntityGroupEntityInfosHierarchyByOwnerId(pageLink, ownerType, ownerId, groupType).subscribe(entityGroupEntityInfosHierarchyByOwners => {
  console.log('List of Entity Group Entity Infos Hierarchy By Owner Ids:', entityGroupEntityInfosHierarchyByOwners);
});
```

**27. getEntityGroupsByOwnerIdAndPageLink**

```javascript
const entityGroupService = self.ctx.entityGroupService;
const ownerType = {  // EntityType object
  // ... set the fields you need
};
const ownerId = 'your-owner-id';
const groupType = {  // EntityType object
  // ... set the fields you need
};
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
entityGroupService.getEntityGroupsByOwnerIdAndPageLink(ownerType, ownerId, groupType, pageLink).subscribe(entityGroupsByOwnerIdAndPageLinks => {
  console.log('List of Entity Groups By Owner Id And Page Links:', entityGroupsByOwnerIdAndPageLinks);
});
```

**28. getEntityGroupsByOwnerId**

```javascript
const entityGroupService = self.ctx.entityGroupService;
const ownerType = {  // EntityType object
  // ... set the fields you need
};
const ownerId = 'your-owner-id';
const groupType = {  // EntityType object
  // ... set the fields you need
};
entityGroupService.getEntityGroupsByOwnerId(ownerType, ownerId, groupType).subscribe(entityGroupsByOwners => {
  console.log('List of Entity Groups By Owner Ids:', entityGroupsByOwners);
});
```

**29. getEntityGroupEntityInfosByOwnerId**

```javascript
const entityGroupService = self.ctx.entityGroupService;
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const ownerType = {  // EntityType object
  // ... set the fields you need
};
const ownerId = 'your-owner-id';
const groupType = {  // EntityType object
  // ... set the fields you need
};
entityGroupService.getEntityGroupEntityInfosByOwnerId(pageLink, ownerType, ownerId, groupType).subscribe(entityGroupEntityInfosByOwners => {
  console.log('List of Entity Group Entity Infos By Owner Ids:', entityGroupEntityInfosByOwners);
});
```

**30. getAllEntityGroupsByOwnerId**

```javascript
const entityGroupService = self.ctx.entityGroupService;
const pageSize = 10;
const ownerType = {  // EntityType object
  // ... set the fields you need
};
const ownerId = 'your-owner-id';
const groupType = {  // EntityType object
  // ... set the fields you need
};
entityGroupService.getAllEntityGroupsByOwnerId(pageSize, ownerType, ownerId, groupType).subscribe(allEntityGroupsByOwners => {
  console.log('List of All Entity Groups By Owner Ids:', allEntityGroupsByOwners);
});
```

**31. getAllEntityGroupsByOwnerIdAndPageLink**

```javascript
const entityGroupService = self.ctx.entityGroupService;
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const ownerType = {  // EntityType object
  // ... set the fields you need
};
const ownerId = 'your-owner-id';
const groupType = {  // EntityType object
  // ... set the fields you need
};
entityGroupService.getAllEntityGroupsByOwnerIdAndPageLink(pageLink, ownerType, ownerId, groupType).subscribe(allEntityGroupsByOwnerIdAndPageLinks => {
  console.log('List of All Entity Groups By Owner Id And Page Links:', allEntityGroupsByOwnerIdAndPageLinks);
});
```

**32. getEntityGroupsByPageLink**

```javascript
const entityGroupService = self.ctx.entityGroupService;
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const groupType = {  // EntityType object
  // ... set the fields you need
};
entityGroupService.getEntityGroupsByPageLink(pageLink, groupType).subscribe(entityGroupsByPageLinks => {
  console.log('List of Entity Groups By Page Links:', entityGroupsByPageLinks);
});
```

**33. getEntityGroupAllByOwnerId**

```javascript
const entityGroupService = self.ctx.entityGroupService;
const ownerType = {  // EntityType object
  // ... set the fields you need
};
const ownerId = 'your-owner-id';
const groupType = {  // EntityType object
  // ... set the fields you need
};
entityGroupService.getEntityGroupAllByOwnerId(ownerType, ownerId, groupType).subscribe(entityGroupAllByOwner => {
  console.log('Get Entity Group All By Owner Id:', entityGroupAllByOwner);
});
```

**34. addEntityToEntityGroup**

```javascript
const entityGroupService = self.ctx.entityGroupService;
const entityGroupId = 'your-entity-group-id';
const entityId = 'your-entity-id';
entityGroupService.addEntityToEntityGroup(entityGroupId, entityId).subscribe(addEntityToEntityGroup => {
  console.log('Add Entity To Entity Group:', addEntityToEntityGroup);
});
```

**35. addEntitiesToEntityGroup**

```javascript
const entityGroupService = self.ctx.entityGroupService;
const entityGroupId = 'your-entity-group-id';
const entityIds = ['your-entity-i-1', 'your-entity-i-2'];
entityGroupService.addEntitiesToEntityGroup(entityGroupId, entityIds).subscribe(addEntitiesToEntityGroup => {
  console.log('Add Entities To Entity Group:', addEntitiesToEntityGroup);
});
```

**36. changeEntityOwner**

```javascript
const entityGroupService = self.ctx.entityGroupService;
const ownerId = {  // EntityId object
  // ... set the fields you need
};
const entityId = {  // EntityId object
  // ... set the fields you need
};
const entityGroupIds = ['your-entity-group-i-1', 'your-entity-group-i-2'];
entityGroupService.changeEntityOwner(ownerId, entityId, entityGroupIds).subscribe(changeEntityOwner => {
  console.log('Change Entity Owner:', changeEntityOwner);
});
```

**37. removeEntityFromEntityGroup**

```javascript
const entityGroupService = self.ctx.entityGroupService;
const entityGroupId = 'your-entity-group-id';
const entityId = 'your-entity-id';
entityGroupService.removeEntityFromEntityGroup(entityGroupId, entityId).subscribe(result => {
  console.log('Delete Entity From Entity Group result:', result);
});
```

**38. removeEntitiesFromEntityGroup**

```javascript
const entityGroupService = self.ctx.entityGroupService;
const entityGroupId = 'your-entity-group-id';
const entityIds = ['your-entity-i-1', 'your-entity-i-2'];
entityGroupService.removeEntitiesFromEntityGroup(entityGroupId, entityIds).subscribe(result => {
  console.log('Delete Entities From Entity Group result:', result);
});
```

**39. getEntityGroupEntity**

```javascript
const entityGroupService = self.ctx.entityGroupService;
const entityGroupId = 'your-entity-group-id';
const entityId = 'your-entity-id';
entityGroupService.getEntityGroupEntity(entityGroupId, entityId).subscribe(entityGroupEntity => {
  console.log('Get Entity Group Entity:', entityGroupEntity);
});
```

**40. getEdgeEntityGroups**

```javascript
const entityGroupService = self.ctx.entityGroupService;
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const edgeId = 'your-edge-id';
const groupType = {  // EntityType object
  // ... set the fields you need
};
entityGroupService.getEdgeEntityGroups(pageLink, edgeId, groupType).subscribe(edgeEntityGroups => {
  console.log('List of Edge Entity Groups:', edgeEntityGroups);
});
```

**41. getAllEdgeEntityGroups**

```javascript
const entityGroupService = self.ctx.entityGroupService;
const pageSize = 10;
const edgeId = 'your-edge-id';
const groupType = {  // EntityType object
  // ... set the fields you need
};
entityGroupService.getAllEdgeEntityGroups(pageSize, edgeId, groupType).subscribe(allEdgeEntityGroups => {
  console.log('List of All Edge Entity Groups:', allEdgeEntityGroups);
});
```

**42. getAllEdgeEntityGroupsByPageLink**

```javascript
const entityGroupService = self.ctx.entityGroupService;
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const edgeId = 'your-edge-id';
const groupType = {  // EntityType object
  // ... set the fields you need
};
entityGroupService.getAllEdgeEntityGroupsByPageLink(pageLink, edgeId, groupType).subscribe(allEdgeEntityGroupsByPageLinks => {
  console.log('List of All Edge Entity Groups By Page Links:', allEdgeEntityGroupsByPageLinks);
});
```

**43. assignEntityGroupToEdge**

```javascript
const entityGroupService = self.ctx.entityGroupService;
const edgeId = 'your-edge-id';
const entityGroupId = 'your-entity-group-id';
const groupType = 'your-group-type';
entityGroupService.assignEntityGroupToEdge(edgeId, entityGroupId, groupType).subscribe(assignEntityGroupToEdge => {
  console.log('Assign Entity Group To Edge:', assignEntityGroupToEdge);
});
```

**44. unassignEntityGroupFromEdge**

```javascript
const entityGroupService = self.ctx.entityGroupService;
const edgeId = 'your-edge-id';
const entityGroupId = 'your-entity-group-id';
const groupType = 'your-group-type';
entityGroupService.unassignEntityGroupFromEdge(edgeId, entityGroupId, groupType).subscribe(unassignEntityGroupFromEdge => {
  console.log('Unassign Entity Group From Edge:', unassignEntityGroupFromEdge);
});
```

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
const entityRelationService = self.ctx.entityRelationService;
const relation = {  // EntityRelation object
  // ... set the fields you need
};
entityRelationService.saveRelation(relation).subscribe(savedRelation => {
  console.log('Saved Relation:', savedRelation);
});
```

**2. getRelation**

```javascript
const entityRelationService = self.ctx.entityRelationService;
const fromId = {  // EntityId object
  // ... set the fields you need
};
const relationType = 'your-relation-type';
const toId = {  // EntityId object
  // ... set the fields you need
};
entityRelationService.getRelation(fromId, relationType, toId).subscribe(relation => {
  console.log('Get Relation:', relation);
});
```

**3. findByFrom**

```javascript
const entityRelationService = self.ctx.entityRelationService;
const fromId = {  // EntityId object
  // ... set the fields you need
};
entityRelationService.findByFrom(fromId).subscribe(byFroms => {
  console.log('List of By Froms:', byFroms);
});
```

**4. findInfoByFrom**

```javascript
const entityRelationService = self.ctx.entityRelationService;
const fromId = {  // EntityId object
  // ... set the fields you need
};
entityRelationService.findInfoByFrom(fromId).subscribe(infoByFroms => {
  console.log('List of Info By Froms:', infoByFroms);
});
```

**5. findByFromAndType**

```javascript
const entityRelationService = self.ctx.entityRelationService;
const fromId = {  // EntityId object
  // ... set the fields you need
};
const relationType = 'your-relation-type';
entityRelationService.findByFromAndType(fromId, relationType).subscribe(byFromAndTypes => {
  console.log('List of By From And Types:', byFromAndTypes);
});
```

**6. findByTo**

```javascript
const entityRelationService = self.ctx.entityRelationService;
const toId = {  // EntityId object
  // ... set the fields you need
};
entityRelationService.findByTo(toId).subscribe(byTos => {
  console.log('List of By Tos:', byTos);
});
```

**7. findInfoByTo**

```javascript
const entityRelationService = self.ctx.entityRelationService;
const toId = {  // EntityId object
  // ... set the fields you need
};
entityRelationService.findInfoByTo(toId).subscribe(infoByTos => {
  console.log('List of Info By Tos:', infoByTos);
});
```

**8. findByToAndType**

```javascript
const entityRelationService = self.ctx.entityRelationService;
const toId = {  // EntityId object
  // ... set the fields you need
};
const relationType = 'your-relation-type';
entityRelationService.findByToAndType(toId, relationType).subscribe(byToAndTypes => {
  console.log('List of By To And Types:', byToAndTypes);
});
```

**9. findByQuery**

```javascript
const entityRelationService = self.ctx.entityRelationService;
const query = {  // EntityRelationsQuery object
  // ... set the fields you need
};
entityRelationService.findByQuery(query).subscribe(byQuerys => {
  console.log('List of By Querys:', byQuerys);
});
```

**10. findInfoByQuery**

```javascript
const entityRelationService = self.ctx.entityRelationService;
const query = {  // EntityRelationsQuery object
  // ... set the fields you need
};
entityRelationService.findInfoByQuery(query).subscribe(infoByQuerys => {
  console.log('List of Info By Querys:', infoByQuerys);
});
```

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
const entityService = self.ctx.entityService;
const entityType = {  // EntityType object
  // ... set the fields you need
};
const entityId = 'your-entity-id';
entityService.getEntityObservable(entityType, entityId).subscribe(entityObservable => {
  console.log('Get Entity Observable:', entityObservable);
});
```

**2. saveEntityObservable**

```javascript
const entityService = self.ctx.entityService;
const entity = {  // BaseData<EntityId> object
  // ... set the fields you need
};
entityService.saveEntityObservable(entity).subscribe(savedEntityObservable => {
  console.log('Saved Entity Observable:', savedEntityObservable);
});
```

**3. getEntity**

```javascript
const entityService = self.ctx.entityService;
const entityType = {  // EntityType object
  // ... set the fields you need
};
const entityId = 'your-entity-id';
entityService.getEntity(entityType, entityId).subscribe(entity => {
  console.log('Get Entity:', entity);
});
```

**4. saveEntity**

```javascript
const entityService = self.ctx.entityService;
const entity = {  // BaseData<EntityId> object
  // ... set the fields you need
};
entityService.saveEntity(entity).subscribe(savedEntity => {
  console.log('Saved Entity:', savedEntity);
});
```

**5. saveGroupEntityObservable**

```javascript
const entityService = self.ctx.entityService;
const entity = {  // BaseData<EntityId> object
  // ... set the fields you need
};
const entityGroupIds = ['your-entity-group-i-1', 'your-entity-group-i-2'];
entityService.saveGroupEntityObservable(entity, entityGroupIds).subscribe(savedGroupEntityObservable => {
  console.log('Saved Group Entity Observable:', savedGroupEntityObservable);
});
```

**6. saveGroupEntity**

```javascript
const entityService = self.ctx.entityService;
const entity = {  // BaseData<EntityId> object
  // ... set the fields you need
};
const entityGroupIds = ['your-entity-group-i-1', 'your-entity-group-i-2'];
entityService.saveGroupEntity(entity, entityGroupIds).subscribe(savedGroupEntity => {
  console.log('Saved Group Entity:', savedGroupEntity);
});
```

**7. getEntitiesObservable**

```javascript
const entityService = self.ctx.entityService;
const entityType = {  // EntityType object
  // ... set the fields you need
};
const entityIds = ['your-entity-i-1', 'your-entity-i-2'];
entityService.getEntitiesObservable(entityType, entityIds).subscribe(entitiesObservables => {
  console.log('List of Entities Observables:', entitiesObservables);
});
```

**8. getEntities**

```javascript
const entityService = self.ctx.entityService;
const entityType = {  // EntityType object
  // ... set the fields you need
};
const entityIds = ['your-entity-i-1', 'your-entity-i-2'];
entityService.getEntities(entityType, entityIds).subscribe(entities => {
  console.log('List of Entities:', entities);
});
```

**9. getSingleTenantByPageLinkObservable**

```javascript
const entityService = self.ctx.entityService;
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
entityService.getSingleTenantByPageLinkObservable(pageLink).subscribe(singleTenantByPageLinkObservables => {
  console.log('List of Single Tenant By Page Link Observables:', singleTenantByPageLinkObservables);
});
```

**10. getEntitiesByPageLinkObservable**

```javascript
const entityService = self.ctx.entityService;
const entityType = {  // EntityType object
  // ... set the fields you need
};
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const subType = 'value';
entityService.getEntitiesByPageLinkObservable(entityType, pageLink, subType).subscribe(entitiesByPageLinkObservables => {
  console.log('List of Entities By Page Link Observables:', entitiesByPageLinkObservables);
});
```

**11. getEntitiesByPageLink**

```javascript
const entityService = self.ctx.entityService;
const entityType = {  // EntityType object
  // ... set the fields you need
};
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const subType = 'value';
entityService.getEntitiesByPageLink(entityType, pageLink, subType).subscribe(entitiesByPageLinks => {
  console.log('List of Entities By Page Links:', entitiesByPageLinks);
});
```

**12. getEntitiesByNameFilter**

```javascript
const entityService = self.ctx.entityService;
const entityType = {  // EntityType object
  // ... set the fields you need
};
const entityNameFilter = 'your-entity-name-filter';
const pageSize = 10;
const subType = 'value';
entityService.getEntitiesByNameFilter(entityType, entityNameFilter, pageSize, subType).subscribe(entitiesByNameFilters => {
  console.log('List of Entities By Name Filters:', entitiesByNameFilters);
});
```

**13. getEntityGroupEntitiesByPageLink**

```javascript
const entityService = self.ctx.entityService;
const entityGroupId = 'your-entity-group-id';
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const entityGroupType = {  // EntityType object
  // ... set the fields you need
};
entityService.getEntityGroupEntitiesByPageLink(entityGroupId, pageLink, entityGroupType).subscribe(entityGroupEntitiesByPageLinks => {
  console.log('List of Entity Group Entities By Page Links:', entityGroupEntitiesByPageLinks);
});
```

**14. getEntityGroupEntities**

```javascript
const entityService = self.ctx.entityService;
const entityGroupId = 'your-entity-group-id';
const entityGroupType = {  // EntityType object
  // ... set the fields you need
};
const pageSize = 10;
entityService.getEntityGroupEntities(entityGroupId, entityGroupType, pageSize).subscribe(entityGroupEntities => {
  console.log('List of Entity Group Entities:', entityGroupEntities);
});
```

**15. findEntityDataByQuery**

```javascript
const entityService = self.ctx.entityService;
const query = {  // EntityDataQuery object
  // ... set the fields you need
};
entityService.findEntityDataByQuery(query).subscribe(entityDataByQuerys => {
  console.log('List of Entity Data By Querys:', entityDataByQuerys);
});
```

**16. findEntityKeysByQuery**

```javascript
const entityService = self.ctx.entityService;
const query = {  // EntityDataQuery object
  // ... set the fields you need
};
const scope = {  // AttributeScope object
  // ... set the fields you need
};
entityService.findEntityKeysByQuery(query, scope).subscribe(entityKeysByQuery => {
  console.log('Find Entity Keys By Query:', entityKeysByQuery);
});
```

**17. findEntityKeysByQueryV2**

```javascript
const entityService = self.ctx.entityService;
const query = {  // EntityDataQuery object
  // ... set the fields you need
};
const scopes = [];  // e.g. array of scopes values
entityService.findEntityKeysByQueryV2(query, scopes).subscribe(entityKeysByQueryV2 => {
  console.log('Find Entity Keys By Query V2:', entityKeysByQueryV2);
});
```

**18. findAlarmDataByQuery**

```javascript
const entityService = self.ctx.entityService;
const query = {  // AlarmDataQuery object
  // ... set the fields you need
};
entityService.findAlarmDataByQuery(query).subscribe(alarmDataByQuerys => {
  console.log('List of Alarm Data By Querys:', alarmDataByQuerys);
});
```

**19. findEntityInfosByFilterAndName**

```javascript
const entityService = self.ctx.entityService;
const filter = {  // EntityFilter object
  // ... set the fields you need
};
const searchText = 'searchText';
entityService.findEntityInfosByFilterAndName(filter, searchText).subscribe(entityInfosByFilterAndNames => {
  console.log('List of Entity Infos By Filter And Names:', entityInfosByFilterAndNames);
});
```

**20. findSingleEntityInfoByEntityFilter**

```javascript
const entityService = self.ctx.entityService;
const filter = {  // EntityFilter object
  // ... set the fields you need
};
entityService.findSingleEntityInfoByEntityFilter(filter).subscribe(singleEntityInfoByEntityFilter => {
  console.log('Find Single Entity Info By Entity Filter:', singleEntityInfoByEntityFilter);
});
```

**21. getAliasFilterTypesByEntityTypes**

```javascript
const entityService = self.ctx.entityService;
const entityTypes = [];  // e.g. array of entity-types values
const result = entityService.getAliasFilterTypesByEntityTypes(entityTypes);
console.log('Result:', result);
```

**22. filterAliasByEntityTypes**

```javascript
const entityService = self.ctx.entityService;
const entityAlias = {  // EntityAlias object
  // ... set the fields you need
};
const entityTypes = [];  // e.g. array of entity-types values
const result = entityService.filterAliasByEntityTypes(entityAlias, entityTypes);
console.log('Result:', result);
```

**23. filterAliasFilterTypeByEntityTypes**

```javascript
const entityService = self.ctx.entityService;
const aliasFilterType = {  // AliasFilterType object
  // ... set the fields you need
};
const entityTypes = [];  // e.g. array of entity-types values
const result = entityService.filterAliasFilterTypeByEntityTypes(aliasFilterType, entityTypes);
console.log('Result:', result);
```

**24. filterAliasFilterTypeByEntityType**

```javascript
const entityService = self.ctx.entityService;
const aliasFilterType = {  // AliasFilterType object
  // ... set the fields you need
};
const entityType = 'entityType';  // e.g. one of the allowed EntityType
const result = entityService.filterAliasFilterTypeByEntityType(aliasFilterType, entityType);
console.log('Result:', result);
```

**25. prepareAllowedEntityTypesList**

```javascript
const entityService = self.ctx.entityService;
const allowedEntityTypes = [];  // e.g. array of allowed-entity-types values
const useAliasEntityTypes = true;
const operation = {  // Operation object
  // ... set the fields you need
};
const result = entityService.prepareAllowedEntityTypesList(allowedEntityTypes, useAliasEntityTypes, operation);
console.log('Result:', result);
```

**26. getEntityFieldKeys**

```javascript
const entityService = self.ctx.entityService;
const entityType = {  // EntityType object
  // ... set the fields you need
};
const searchText = 'value';
const result = entityService.getEntityFieldKeys(entityType, searchText);
console.log('Result:', result);
```

**27. getAlarmKeys**

```javascript
const entityService = self.ctx.entityService;
const searchText = 'value';
const result = entityService.getAlarmKeys(searchText);
console.log('Result:', result);
```

**28. getEntityKeys**

```javascript
const entityService = self.ctx.entityService;
const entityId = {  // EntityId object
  // ... set the fields you need
};
const query = 'your-query';
const type = {  // DataKeyType object
  // ... set the fields you need
};
entityService.getEntityKeys(entityId, query, type).subscribe(entityKeys => {
  console.log('List of Entity Keys:', entityKeys);
});
```

**29. getEntityKeysByEntityFilter**

```javascript
const entityService = self.ctx.entityService;
const filter = {  // EntityFilter object
  // ... set the fields you need
};
const types = [];  // e.g. array of types values
const entityTypes = [];  // e.g. array of entity-types values
entityService.getEntityKeysByEntityFilter(filter, types, entityTypes).subscribe(entityKeysByEntityFilters => {
  console.log('List of Entity Keys By Entity Filters:', entityKeysByEntityFilters);
});
```

**30. getEntityKeysByEntityFilterAndScope**

```javascript
const entityService = self.ctx.entityService;
const filter = {  // EntityFilter object
  // ... set the fields you need
};
const types = [];  // e.g. array of types values
const entityTypes = [];  // e.g. array of entity-types values
const scope = {  // AttributeScope object
  // ... set the fields you need
};
entityService.getEntityKeysByEntityFilterAndScope(filter, types, entityTypes, scope).subscribe(entityKeysByEntityFilterAndScopes => {
  console.log('List of Entity Keys By Entity Filter And Scopes:', entityKeysByEntityFilterAndScopes);
});
```

**31. createDatasourcesFromSubscriptionsInfo**

```javascript
const entityService = self.ctx.entityService;
const subscriptionsInfo = [];  // e.g. array of subscriptions-info values
const result = entityService.createDatasourcesFromSubscriptionsInfo(subscriptionsInfo);
console.log('Result:', result);
```

**32. createAlarmSourceFromSubscriptionInfo**

```javascript
const entityService = self.ctx.entityService;
const subscriptionInfo = {  // SubscriptionInfo object
  // ... set the fields you need
};
const result = entityService.createAlarmSourceFromSubscriptionInfo(subscriptionInfo);
console.log('Result:', result);
```

**33. getAssignedToEdgeEntitiesByType**

```javascript
const entityService = self.ctx.entityService;
const edgeId = 'your-edge-id';
const entityType = {  // EntityType object
  // ... set the fields you need
};
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
entityService.getAssignedToEdgeEntitiesByType(edgeId, entityType, pageLink).subscribe(assignedToEdgeEntitiesByType => {
  console.log('Get Assigned To Edge Entities By Type:', assignedToEdgeEntitiesByType);
});
```

**34. getEdgeEventContent**

```javascript
const entityService = self.ctx.entityService;
const entity = {  // EdgeEvent object
  // ... set the fields you need
};
entityService.getEdgeEventContent(entity).subscribe(edgeEventContent => {
  console.log('Get Edge Event Content:', edgeEventContent);
});
```

**35. getEntitySubtypesObservable**

```javascript
const entityService = self.ctx.entityService;
const entityType = {  // EntityType object
  // ... set the fields you need
};
entityService.getEntitySubtypesObservable(entityType).subscribe(entitySubtypesObservables => {
  console.log('List of Entity Subtypes Observables:', entitySubtypesObservables);
});
```

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
const entityViewService = self.ctx.entityViewService;
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const type = 'value';
entityViewService.getTenantEntityViews(pageLink, type).subscribe(tenantEntityViews => {
  console.log('List of Tenant Entity Views:', tenantEntityViews);
});
```

**2. getCustomerEntityViews**

```javascript
const entityViewService = self.ctx.entityViewService;
const customerId = 'your-customer-id';
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const type = 'value';
entityViewService.getCustomerEntityViews(customerId, pageLink, type).subscribe(customerEntityViews => {
  console.log('List of Customer Entity Views:', customerEntityViews);
});
```

**3. getEntityView**

```javascript
const entityViewService = self.ctx.entityViewService;
const entityViewId = 'your-entity-view-id';
entityViewService.getEntityView(entityViewId).subscribe(entityView => {
  console.log('Get Entity View:', entityView);
});
```

**4. getEntityViews**

```javascript
const entityViewService = self.ctx.entityViewService;
const entityViewIds = ['your-entity-view-i-1', 'your-entity-view-i-2'];
entityViewService.getEntityViews(entityViewIds).subscribe(entityViews => {
  console.log('List of Entity Views:', entityViews);
});
```

**5. getUserEntityViews**

```javascript
const entityViewService = self.ctx.entityViewService;
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const type = 'value';
entityViewService.getUserEntityViews(pageLink, type).subscribe(userEntityViews => {
  console.log('List of User Entity Views:', userEntityViews);
});
```

**6. getAllEntityViewInfos**

```javascript
const entityViewService = self.ctx.entityViewService;
const includeCustomers = true;
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const type = 'value';
entityViewService.getAllEntityViewInfos(includeCustomers, pageLink, type).subscribe(allEntityViewInfos => {
  console.log('List of All Entity View Infos:', allEntityViewInfos);
});
```

**7. getCustomerEntityViewInfos**

```javascript
const entityViewService = self.ctx.entityViewService;
const includeCustomers = true;
const customerId = 'your-customer-id';
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const type = 'value';
entityViewService.getCustomerEntityViewInfos(includeCustomers, customerId, pageLink, type).subscribe(customerEntityViewInfos => {
  console.log('List of Customer Entity View Infos:', customerEntityViewInfos);
});
```

**8. getEntityViewInfo**

```javascript
const entityViewService = self.ctx.entityViewService;
const entityViewId = 'your-entity-view-id';
entityViewService.getEntityViewInfo(entityViewId).subscribe(entityViewInfo => {
  console.log('Get Entity View Info:', entityViewInfo);
});
```

**9. saveEntityView**

```javascript
const entityViewService = self.ctx.entityViewService;
const entityView = {  // EntityView object
  // ... set the fields you need
};
const entityGroupIds = ['your-entity-group-i-1', 'your-entity-group-i-2'];
const result = entityViewService.saveEntityView(entityView, entityGroupIds);
console.log('Result:', result);
```

**10. getEntityViewTypes**

```javascript
const entityViewService = self.ctx.entityViewService;
entityViewService.getEntityViewTypes().subscribe(entityViewTypes => {
  console.log('List of Entity View Types:', entityViewTypes);
});
```

**11. findByQuery**

```javascript
const entityViewService = self.ctx.entityViewService;
const query = {  // EntityViewSearchQuery object
  // ... set the fields you need
};
entityViewService.findByQuery(query).subscribe(byQuerys => {
  console.log('List of By Querys:', byQuerys);
});
```

### **EVENT SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const eventService = $injector.get(self.ctx.servicesMap.get('eventService'));
```

**1. getEvents**

```javascript
const $injector = self.ctx.$scope.$injector;
const eventService = $injector.get(self.ctx.servicesMap.get('eventService'));
const entityId = {  // EntityId object
  // ... set the fields you need
};
const eventType = 'eventType';  // e.g. one of the allowed EventType
const tenantId = 'your-tenant-id';
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
eventService.getEvents(entityId, eventType, tenantId, pageLink).subscribe(events => {
  console.log('List of Events:', events);
});
```

**2. getFilterEvents**

```javascript
const $injector = self.ctx.$scope.$injector;
const eventService = $injector.get(self.ctx.servicesMap.get('eventService'));
const entityId = {  // EntityId object
  // ... set the fields you need
};
const eventType = 'eventType';  // e.g. one of the allowed EventType
const tenantId = 'your-tenant-id';
const filters = {  // FilterEventBody object
  // ... set the fields you need
};
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
eventService.getFilterEvents(entityId, eventType, tenantId, filters, pageLink).subscribe(filterEvents => {
  console.log('List of Filter Events:', filterEvents);
});
```

### **GIT HUB SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const gitHubService = $injector.get(self.ctx.servicesMap.get('gitHubService'));
```

**1. getGitHubStar**

```javascript
const $injector = self.ctx.$scope.$injector;
const gitHubService = $injector.get(self.ctx.servicesMap.get('gitHubService'));
gitHubService.getGitHubStar().subscribe(gitHubStar => {
  console.log('Get Git Hub Star:', gitHubStar);
});
```

### **IMAGE SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const imageService = $injector.get(self.ctx.servicesMap.get('imageService'));
```

**1. uploadImage**

```javascript
const $injector = self.ctx.$scope.$injector;
const imageService = $injector.get(self.ctx.servicesMap.get('imageService'));
const file = {  // File object
  // ... set the fields you need
};
const title = 'title-value';
const imageSubType = 'value';
imageService.uploadImage(file, title, imageSubType).subscribe(savedImage => {
  console.log('Saved Image:', savedImage);
});
```

**2. updateImage**

```javascript
const $injector = self.ctx.$scope.$injector;
const imageService = $injector.get(self.ctx.servicesMap.get('imageService'));
const type = {  // ImageResourceType object
  // ... set the fields you need
};
const key = 'key-value';
const file = {  // File object
  // ... set the fields you need
};
imageService.updateImage(type, key, file).subscribe(savedImage => {
  console.log('Saved Image:', savedImage);
});
```

**3. updateImageInfo**

```javascript
const $injector = self.ctx.$scope.$injector;
const imageService = $injector.get(self.ctx.servicesMap.get('imageService'));
const imageInfo = {  // ImageResourceInfo object
  // ... set the fields you need
};
imageService.updateImageInfo(imageInfo).subscribe(savedImageInfo => {
  console.log('Saved Image Info:', savedImageInfo);
});
```

**4. updateImagePublicStatus**

```javascript
const $injector = self.ctx.$scope.$injector;
const imageService = $injector.get(self.ctx.servicesMap.get('imageService'));
const imageInfo = {  // ImageResourceInfo object
  // ... set the fields you need
};
const isPublic = true;
imageService.updateImagePublicStatus(imageInfo, isPublic).subscribe(savedImagePublicStatus => {
  console.log('Saved Image Public Status:', savedImagePublicStatus);
});
```

**5. getImages**

```javascript
const $injector = self.ctx.$scope.$injector;
const imageService = $injector.get(self.ctx.servicesMap.get('imageService'));
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const imageSubType = 'value';
imageService.getImages(pageLink, imageSubType).subscribe(images => {
  console.log('List of Images:', images);
});
```

**6. getImageInfo**

```javascript
const $injector = self.ctx.$scope.$injector;
const imageService = $injector.get(self.ctx.servicesMap.get('imageService'));
const type = {  // ImageResourceType object
  // ... set the fields you need
};
const key = 'key-value';
imageService.getImageInfo(type, key).subscribe(imageInfo => {
  console.log('Get Image Info:', imageInfo);
});
```

**7. getImageDataUrl**

```javascript
const $injector = self.ctx.$scope.$injector;
const imageService = $injector.get(self.ctx.servicesMap.get('imageService'));
const imageUrl = 'your-image-url';
imageService.getImageDataUrl(imageUrl).subscribe(imageDataUrl => {
  console.log('Get Image Data Url:', imageDataUrl);
});
```

**8. getLoginImageDataUrl**

```javascript
const $injector = self.ctx.$scope.$injector;
const imageService = $injector.get(self.ctx.servicesMap.get('imageService'));
const imageUrl = 'your-image-url';
const faviconElseLogo = true;
imageService.getLoginImageDataUrl(imageUrl, faviconElseLogo).subscribe(loginImageDataUrl => {
  console.log('Get Login Image Data Url:', loginImageDataUrl);
});
```

**9. loadImageDataUrl**

```javascript
const $injector = self.ctx.$scope.$injector;
const imageService = $injector.get(self.ctx.servicesMap.get('imageService'));
const imageLink = 'your-image-link';
imageService.loadImageDataUrl(imageLink).subscribe(imageDataUrl => {
  console.log('Load Image Data Url:', imageDataUrl);
});
```

**10. getImageString**

```javascript
const $injector = self.ctx.$scope.$injector;
const imageService = $injector.get(self.ctx.servicesMap.get('imageService'));
const imageUrl = 'your-image-url';
imageService.getImageString(imageUrl).subscribe(imageString => {
  console.log('Get Image String:', imageString);
});
```

**11. resolveImageUrl**

```javascript
const $injector = self.ctx.$scope.$injector;
const imageService = $injector.get(self.ctx.servicesMap.get('imageService'));
const imageUrl = 'your-image-url';
imageService.resolveImageUrl(imageUrl).subscribe(resolveImageUrl => {
  console.log('Resolve Image Url:', resolveImageUrl);
});
```

**12. resolveLoginImageUrl**

```javascript
const $injector = self.ctx.$scope.$injector;
const imageService = $injector.get(self.ctx.servicesMap.get('imageService'));
const imageUrl = 'your-image-url';
const faviconElseLogo = true;
imageService.resolveLoginImageUrl(imageUrl, faviconElseLogo).subscribe(resolveLoginImageUrl => {
  console.log('Resolve Login Image Url:', resolveLoginImageUrl);
});
```

**13. downloadImage**

```javascript
const $injector = self.ctx.$scope.$injector;
const imageService = $injector.get(self.ctx.servicesMap.get('imageService'));
const type = {  // ImageResourceType object
  // ... set the fields you need
};
const key = 'key-value';
imageService.downloadImage(type, key).subscribe(downloadImage => {
  console.log('Download Image:', downloadImage);
});
```

**14. exportImage**

```javascript
const $injector = self.ctx.$scope.$injector;
const imageService = $injector.get(self.ctx.servicesMap.get('imageService'));
const type = {  // ImageResourceType object
  // ... set the fields you need
};
const key = 'key-value';
imageService.exportImage(type, key).subscribe(exportImage => {
  console.log('Export Image:', exportImage);
});
```

**15. importImage**

```javascript
const $injector = self.ctx.$scope.$injector;
const imageService = $injector.get(self.ctx.servicesMap.get('imageService'));
const imageData = {  // ImageExportData object
  // ... set the fields you need
};
imageService.importImage(imageData).subscribe(importImage => {
  console.log('Import Image:', importImage);
});
```

### **INTEGRATION SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const integrationService = $injector.get(self.ctx.servicesMap.get('integrationService'));
```

**1. getIntegrations**

```javascript
const $injector = self.ctx.$scope.$injector;
const integrationService = $injector.get(self.ctx.servicesMap.get('integrationService'));
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
integrationService.getIntegrations(pageLink).subscribe(integrations => {
  console.log('List of Integrations:', integrations);
});
```

**2. getIntegrationsConvertersInfo**

```javascript
const $injector = self.ctx.$scope.$injector;
const integrationService = $injector.get(self.ctx.servicesMap.get('integrationService'));
integrationService.getIntegrationsConvertersInfo().subscribe(integrationsConvertersInfo => {
  console.log('Get Integrations Converters Info:', integrationsConvertersInfo);
});
```

**3. getIntegrationsConvertersInfoCached**

```javascript
const $injector = self.ctx.$scope.$injector;
const integrationService = $injector.get(self.ctx.servicesMap.get('integrationService'));
integrationService.getIntegrationsConvertersInfoCached().subscribe(integrationsConvertersInfoCached => {
  console.log('Get Integrations Converters Info Cached:', integrationsConvertersInfoCached);
});
```

**4. getIntegrationsInfo**

```javascript
const $injector = self.ctx.$scope.$injector;
const integrationService = $injector.get(self.ctx.servicesMap.get('integrationService'));
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const isEdgeTemplate = true;
integrationService.getIntegrationsInfo(pageLink, isEdgeTemplate).subscribe(integrationsInfos => {
  console.log('List of Integrations Infos:', integrationsInfos);
});
```

**5. getIntegrationsByEdgeTemplate**

```javascript
const $injector = self.ctx.$scope.$injector;
const integrationService = $injector.get(self.ctx.servicesMap.get('integrationService'));
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const isEdgeTemplate = true;
integrationService.getIntegrationsByEdgeTemplate(pageLink, isEdgeTemplate).subscribe(integrationsByEdgeTemplates => {
  console.log('List of Integrations By Edge Templates:', integrationsByEdgeTemplates);
});
```

**6. getIntegrationsByIds**

```javascript
const $injector = self.ctx.$scope.$injector;
const integrationService = $injector.get(self.ctx.servicesMap.get('integrationService'));
const integrationIds = ['your-integration-i-1', 'your-integration-i-2'];
integrationService.getIntegrationsByIds(integrationIds).subscribe(integrationsBys => {
  console.log('List of Integrations By Ids:', integrationsBys);
});
```

**7. getIntegration**

```javascript
const $injector = self.ctx.$scope.$injector;
const integrationService = $injector.get(self.ctx.servicesMap.get('integrationService'));
const integrationId = 'your-integration-id';
integrationService.getIntegration(integrationId).subscribe(integration => {
  console.log('Get Integration:', integration);
});
```

**8. saveIntegration**

```javascript
const $injector = self.ctx.$scope.$injector;
const integrationService = $injector.get(self.ctx.servicesMap.get('integrationService'));
const integration = {  // Integration object
  // ... set the fields you need
};
integrationService.saveIntegration(integration).subscribe(savedIntegration => {
  console.log('Saved Integration:', savedIntegration);
});
```

**9. getIntegrationHttpEndpointLink**

```javascript
const $injector = self.ctx.$scope.$injector;
const integrationService = $injector.get(self.ctx.servicesMap.get('integrationService'));
const configuration = {  // any object
  // ... set the fields you need
};
const integrationType = {  // IntegrationType object
  // ... set the fields you need
};
const routingKey = 'your-routing-key';
const result = integrationService.getIntegrationHttpEndpointLink(configuration, integrationType, routingKey);
console.log('Result:', result);
```

**10. toLowerCase**

```javascript
const $injector = self.ctx.$scope.$injector;
const integrationService = $injector.get(self.ctx.servicesMap.get('integrationService'));
const result = integrationService.toLowerCase();
console.log('Result:', result);
```

**11. assignIntegrationToEdge**

```javascript
const $injector = self.ctx.$scope.$injector;
const integrationService = $injector.get(self.ctx.servicesMap.get('integrationService'));
const edgeId = 'your-edge-id';
const integrationId = 'your-integration-id';
integrationService.assignIntegrationToEdge(edgeId, integrationId).subscribe(assignIntegrationToEdge => {
  console.log('Assign Integration To Edge:', assignIntegrationToEdge);
});
```

**12. getEdgeIntegrations**

```javascript
const $injector = self.ctx.$scope.$injector;
const integrationService = $injector.get(self.ctx.servicesMap.get('integrationService'));
const edgeId = 'your-edge-id';
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
integrationService.getEdgeIntegrations(edgeId, pageLink).subscribe(edgeIntegrations => {
  console.log('List of Edge Integrations:', edgeIntegrations);
});
```

**13. exportIntegrationPackage**

```javascript
const $injector = self.ctx.$scope.$injector;
const integrationService = $injector.get(self.ctx.servicesMap.get('integrationService'));
const integrationId = 'your-integration-id';
integrationService.exportIntegrationPackage(integrationId).subscribe(exportIntegrationPackage => {
  console.log('Export Integration Package:', exportIntegrationPackage);
});
```

### **JOB SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const jobService = $injector.get(self.ctx.servicesMap.get('jobService'));
```

**1. getJobById**

```javascript
const $injector = self.ctx.$scope.$injector;
const jobService = $injector.get(self.ctx.servicesMap.get('jobService'));
const id = 'your-id';
jobService.getJobById(id).subscribe(jobBy => {
  console.log('Get Job By Id:', jobBy);
});
```

**2. getJobs**

```javascript
const $injector = self.ctx.$scope.$injector;
const jobService = $injector.get(self.ctx.servicesMap.get('jobService'));
const query = {  // JobQuery object
  // ... set the fields you need
};
jobService.getJobs(query).subscribe(jobs => {
  console.log('List of Jobs:', jobs);
});
```

**3. cancelJob**

```javascript
const $injector = self.ctx.$scope.$injector;
const jobService = $injector.get(self.ctx.servicesMap.get('jobService'));
const id = 'your-id';
jobService.cancelJob(id).subscribe(cancelJob => {
  console.log('Cancel Job:', cancelJob);
});
```

**4. reprocessJob**

```javascript
const $injector = self.ctx.$scope.$injector;
const jobService = $injector.get(self.ctx.servicesMap.get('jobService'));
const id = 'your-id';
jobService.reprocessJob(id).subscribe(reprocessJob => {
  console.log('Reprocess Job:', reprocessJob);
});
```

**5. deleteJob**

```javascript
const $injector = self.ctx.$scope.$injector;
const jobService = $injector.get(self.ctx.servicesMap.get('jobService'));
const id = 'your-id';
jobService.deleteJob(id).subscribe(result => {
  console.log('Delete Job result:', result);
});
```

### **MOBILE APP SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const mobileAppService = $injector.get(self.ctx.servicesMap.get('mobileAppService'));
```

**1. saveMobileApp**

```javascript
const $injector = self.ctx.$scope.$injector;
const mobileAppService = $injector.get(self.ctx.servicesMap.get('mobileAppService'));
const mobileApp = {  // MobileApp object
  // ... set the fields you need
};
mobileAppService.saveMobileApp(mobileApp).subscribe(savedMobileApp => {
  console.log('Saved Mobile App:', savedMobileApp);
});
```

**2. getTenantMobileAppInfos**

```javascript
const $injector = self.ctx.$scope.$injector;
const mobileAppService = $injector.get(self.ctx.servicesMap.get('mobileAppService'));
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const platformType = {  // PlatformType object
  // ... set the fields you need
};
mobileAppService.getTenantMobileAppInfos(pageLink, platformType).subscribe(tenantMobileAppInfos => {
  console.log('List of Tenant Mobile App Infos:', tenantMobileAppInfos);
});
```

**3. getMobileAppInfoById**

```javascript
const $injector = self.ctx.$scope.$injector;
const mobileAppService = $injector.get(self.ctx.servicesMap.get('mobileAppService'));
const id = 'your-id';
mobileAppService.getMobileAppInfoById(id).subscribe(mobileAppInfoBy => {
  console.log('Get Mobile App Info By Id:', mobileAppInfoBy);
});
```

**4. deleteMobileApp**

```javascript
const $injector = self.ctx.$scope.$injector;
const mobileAppService = $injector.get(self.ctx.servicesMap.get('mobileAppService'));
const id = 'your-id';
mobileAppService.deleteMobileApp(id).subscribe(result => {
  console.log('Delete Mobile App result:', result);
});
```

**5. getTenantMobileAppBundleInfos**

```javascript
const $injector = self.ctx.$scope.$injector;
const mobileAppService = $injector.get(self.ctx.servicesMap.get('mobileAppService'));
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
mobileAppService.getTenantMobileAppBundleInfos(pageLink).subscribe(tenantMobileAppBundleInfos => {
  console.log('List of Tenant Mobile App Bundle Infos:', tenantMobileAppBundleInfos);
});
```

**6. getMobileAppBundleInfoById**

```javascript
const $injector = self.ctx.$scope.$injector;
const mobileAppService = $injector.get(self.ctx.servicesMap.get('mobileAppService'));
const id = 'your-id';
mobileAppService.getMobileAppBundleInfoById(id).subscribe(mobileAppBundleInfoBy => {
  console.log('Get Mobile App Bundle Info By Id:', mobileAppBundleInfoBy);
});
```

**7. deleteMobileAppBundle**

```javascript
const $injector = self.ctx.$scope.$injector;
const mobileAppService = $injector.get(self.ctx.servicesMap.get('mobileAppService'));
const id = 'your-id';
mobileAppService.deleteMobileAppBundle(id).subscribe(result => {
  console.log('Delete Mobile App Bundle result:', result);
});
```

### **MOBILE APPLICATION SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const mobileApplicationService = $injector.get(self.ctx.servicesMap.get('mobileApplicationService'));
```

**1. getMobileAppSettings**

```javascript
const $injector = self.ctx.$scope.$injector;
const mobileApplicationService = $injector.get(self.ctx.servicesMap.get('mobileApplicationService'));
mobileApplicationService.getMobileAppSettings().subscribe(mobileAppSettings => {
  console.log('Get Mobile App Settings:', mobileAppSettings);
});
```

**2. getMergedMobileAppSettings**

```javascript
const $injector = self.ctx.$scope.$injector;
const mobileApplicationService = $injector.get(self.ctx.servicesMap.get('mobileApplicationService'));
mobileApplicationService.getMergedMobileAppSettings().subscribe(mergedMobileAppSettings => {
  console.log('Get Merged Mobile App Settings:', mergedMobileAppSettings);
});
```

**3. saveMobileAppSettings**

```javascript
const $injector = self.ctx.$scope.$injector;
const mobileApplicationService = $injector.get(self.ctx.servicesMap.get('mobileApplicationService'));
const mobileAppSettings = {  // QrCodeSettings object
  // ... set the fields you need
};
mobileApplicationService.saveMobileAppSettings(mobileAppSettings).subscribe(savedMobileAppSettings => {
  console.log('Saved Mobile App Settings:', savedMobileAppSettings);
});
```

**4. getMobileAppDeepLink**

```javascript
const $injector = self.ctx.$scope.$injector;
const mobileApplicationService = $injector.get(self.ctx.servicesMap.get('mobileApplicationService'));
mobileApplicationService.getMobileAppDeepLink().subscribe(mobileAppDeepLink => {
  console.log('Get Mobile App Deep Link:', mobileAppDeepLink);
});
```

### **NOTIFICATION SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const notificationService = $injector.get(self.ctx.servicesMap.get('notificationService'));
```

**1. getNotifications**

```javascript
const $injector = self.ctx.$scope.$injector;
const notificationService = $injector.get(self.ctx.servicesMap.get('notificationService'));
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
notificationService.getNotifications(pageLink).subscribe(notifications => {
  console.log('List of Notifications:', notifications);
});
```

**2. deleteNotification**

```javascript
const $injector = self.ctx.$scope.$injector;
const notificationService = $injector.get(self.ctx.servicesMap.get('notificationService'));
const id = 'your-id';
notificationService.deleteNotification(id).subscribe(result => {
  console.log('Delete Notification result:', result);
});
```

**3. markNotificationAsRead**

```javascript
const $injector = self.ctx.$scope.$injector;
const notificationService = $injector.get(self.ctx.servicesMap.get('notificationService'));
const id = 'your-id';
notificationService.markNotificationAsRead(id).subscribe(markNotificationAsRead => {
  console.log('Mark Notification As Read:', markNotificationAsRead);
});
```

**4. markAllNotificationsAsRead**

```javascript
const $injector = self.ctx.$scope.$injector;
const notificationService = $injector.get(self.ctx.servicesMap.get('notificationService'));
notificationService.markAllNotificationsAsRead().subscribe(markAllNotificationsAsRead => {
  console.log('Mark All Notifications As Read:', markAllNotificationsAsRead);
});
```

**5. createNotificationRequest**

```javascript
const $injector = self.ctx.$scope.$injector;
const notificationService = $injector.get(self.ctx.servicesMap.get('notificationService'));
const notification = {  // NotificationRequest object
  // ... set the fields you need
};
notificationService.createNotificationRequest(notification).subscribe(createNotificationRequest => {
  console.log('Create Notification Request:', createNotificationRequest);
});
```

**6. sendEntitiesLimitIncreaseRequest**

```javascript
const $injector = self.ctx.$scope.$injector;
const notificationService = $injector.get(self.ctx.servicesMap.get('notificationService'));
const entityType = {  // EntityType object
  // ... set the fields you need
};
notificationService.sendEntitiesLimitIncreaseRequest(entityType).subscribe(sendEntitiesLimitIncreaseRequest => {
  console.log('Send Entities Limit Increase Request:', sendEntitiesLimitIncreaseRequest);
});
```

**7. sendAddonAccessRequest**

```javascript
const $injector = self.ctx.$scope.$injector;
const notificationService = $injector.get(self.ctx.servicesMap.get('notificationService'));
const addonType = {  // AddonType object
  // ... set the fields you need
};
notificationService.sendAddonAccessRequest(addonType).subscribe(sendAddonAccessRequest => {
  console.log('Send Addon Access Request:', sendAddonAccessRequest);
});
```

**8. sendPlanUpgradeRequest**

```javascript
const $injector = self.ctx.$scope.$injector;
const notificationService = $injector.get(self.ctx.servicesMap.get('notificationService'));
const planName = 'your-plan-name';
notificationService.sendPlanUpgradeRequest(planName).subscribe(sendPlanUpgradeRequest => {
  console.log('Send Plan Upgrade Request:', sendPlanUpgradeRequest);
});
```

**9. getNotificationRequestById**

```javascript
const $injector = self.ctx.$scope.$injector;
const notificationService = $injector.get(self.ctx.servicesMap.get('notificationService'));
const id = 'your-id';
notificationService.getNotificationRequestById(id).subscribe(notificationRequestBy => {
  console.log('Get Notification Request By Id:', notificationRequestBy);
});
```

**10. getAvailableDeliveryMethods**

```javascript
const $injector = self.ctx.$scope.$injector;
const notificationService = $injector.get(self.ctx.servicesMap.get('notificationService'));
notificationService.getAvailableDeliveryMethods().subscribe(availableDeliveryMethods => {
  console.log('List of Available Delivery Methods:', availableDeliveryMethods);
});
```

**11. deleteNotificationRequest**

```javascript
const $injector = self.ctx.$scope.$injector;
const notificationService = $injector.get(self.ctx.servicesMap.get('notificationService'));
const id = 'your-id';
notificationService.deleteNotificationRequest(id).subscribe(result => {
  console.log('Delete Notification Request result:', result);
});
```

**12. getNotificationRequestPreview**

```javascript
const $injector = self.ctx.$scope.$injector;
const notificationService = $injector.get(self.ctx.servicesMap.get('notificationService'));
const notification = {  // NotificationRequest object
  // ... set the fields you need
};
notificationService.getNotificationRequestPreview(notification).subscribe(notificationRequestPreview => {
  console.log('Get Notification Request Preview:', notificationRequestPreview);
});
```

**13. getNotificationRequests**

```javascript
const $injector = self.ctx.$scope.$injector;
const notificationService = $injector.get(self.ctx.servicesMap.get('notificationService'));
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
notificationService.getNotificationRequests(pageLink).subscribe(notificationRequests => {
  console.log('List of Notification Requests:', notificationRequests);
});
```

**14. getNotificationSettings**

```javascript
const $injector = self.ctx.$scope.$injector;
const notificationService = $injector.get(self.ctx.servicesMap.get('notificationService'));
notificationService.getNotificationSettings().subscribe(notificationSettings => {
  console.log('Get Notification Settings:', notificationSettings);
});
```

**15. saveNotificationSettings**

```javascript
const $injector = self.ctx.$scope.$injector;
const notificationService = $injector.get(self.ctx.servicesMap.get('notificationService'));
const notificationSettings = {  // NotificationSettings object
  // ... set the fields you need
};
notificationService.saveNotificationSettings(notificationSettings).subscribe(savedNotificationSettings => {
  console.log('Saved Notification Settings:', savedNotificationSettings);
});
```

**16. listSlackConversations**

```javascript
const $injector = self.ctx.$scope.$injector;
const notificationService = $injector.get(self.ctx.servicesMap.get('notificationService'));
const type = {  // SlackChanelType object
  // ... set the fields you need
};
const token = 'your-token';
notificationService.listSlackConversations(type, token).subscribe(listSlackConversations => {
  console.log('List Slack Conversations:', listSlackConversations);
});
```

**17. saveNotificationRule**

```javascript
const $injector = self.ctx.$scope.$injector;
const notificationService = $injector.get(self.ctx.servicesMap.get('notificationService'));
const notificationRule = {  // NotificationRule object
  // ... set the fields you need
};
notificationService.saveNotificationRule(notificationRule).subscribe(savedNotificationRule => {
  console.log('Saved Notification Rule:', savedNotificationRule);
});
```

**18. getNotificationRuleById**

```javascript
const $injector = self.ctx.$scope.$injector;
const notificationService = $injector.get(self.ctx.servicesMap.get('notificationService'));
const id = 'your-id';
notificationService.getNotificationRuleById(id).subscribe(notificationRuleBy => {
  console.log('Get Notification Rule By Id:', notificationRuleBy);
});
```

**19. deleteNotificationRule**

```javascript
const $injector = self.ctx.$scope.$injector;
const notificationService = $injector.get(self.ctx.servicesMap.get('notificationService'));
const id = 'your-id';
notificationService.deleteNotificationRule(id).subscribe(result => {
  console.log('Delete Notification Rule result:', result);
});
```

**20. getNotificationRules**

```javascript
const $injector = self.ctx.$scope.$injector;
const notificationService = $injector.get(self.ctx.servicesMap.get('notificationService'));
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
notificationService.getNotificationRules(pageLink).subscribe(notificationRules => {
  console.log('List of Notification Rules:', notificationRules);
});
```

**21. saveNotificationTarget**

```javascript
const $injector = self.ctx.$scope.$injector;
const notificationService = $injector.get(self.ctx.servicesMap.get('notificationService'));
const notificationTarget = {  // NotificationTarget object
  // ... set the fields you need
};
notificationService.saveNotificationTarget(notificationTarget).subscribe(savedNotificationTarget => {
  console.log('Saved Notification Target:', savedNotificationTarget);
});
```

**22. getNotificationTargetById**

```javascript
const $injector = self.ctx.$scope.$injector;
const notificationService = $injector.get(self.ctx.servicesMap.get('notificationService'));
const id = 'your-id';
notificationService.getNotificationTargetById(id).subscribe(notificationTargetBy => {
  console.log('Get Notification Target By Id:', notificationTargetBy);
});
```

**23. deleteNotificationTarget**

```javascript
const $injector = self.ctx.$scope.$injector;
const notificationService = $injector.get(self.ctx.servicesMap.get('notificationService'));
const id = 'your-id';
notificationService.deleteNotificationTarget(id).subscribe(result => {
  console.log('Delete Notification Target result:', result);
});
```

**24. getNotificationTargetsByIds**

```javascript
const $injector = self.ctx.$scope.$injector;
const notificationService = $injector.get(self.ctx.servicesMap.get('notificationService'));
const ids = [];  // e.g. array of ids values
notificationService.getNotificationTargetsByIds(ids).subscribe(notificationTargetsBys => {
  console.log('List of Notification Targets By Ids:', notificationTargetsBys);
});
```

**25. getNotificationTargets**

```javascript
const $injector = self.ctx.$scope.$injector;
const notificationService = $injector.get(self.ctx.servicesMap.get('notificationService'));
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const type = {  // NotificationType object
  // ... set the fields you need
};
notificationService.getNotificationTargets(pageLink, type).subscribe(notificationTargets => {
  console.log('List of Notification Targets:', notificationTargets);
});
```

**26. getRecipientsForNotificationTargetConfig**

```javascript
const $injector = self.ctx.$scope.$injector;
const notificationService = $injector.get(self.ctx.servicesMap.get('notificationService'));
const notificationTarget = {  // NotificationTarget object
  // ... set the fields you need
};
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
notificationService.getRecipientsForNotificationTargetConfig(notificationTarget, pageLink).subscribe(recipientsForNotificationTargetConfigs => {
  console.log('List of Recipients For Notification Target Configs:', recipientsForNotificationTargetConfigs);
});
```

**27. saveNotificationTemplate**

```javascript
const $injector = self.ctx.$scope.$injector;
const notificationService = $injector.get(self.ctx.servicesMap.get('notificationService'));
const notificationTarget = {  // NotificationTemplate object
  // ... set the fields you need
};
notificationService.saveNotificationTemplate(notificationTarget).subscribe(savedNotificationTemplate => {
  console.log('Saved Notification Template:', savedNotificationTemplate);
});
```

**28. getNotificationTemplateById**

```javascript
const $injector = self.ctx.$scope.$injector;
const notificationService = $injector.get(self.ctx.servicesMap.get('notificationService'));
const id = 'your-id';
notificationService.getNotificationTemplateById(id).subscribe(notificationTemplateBy => {
  console.log('Get Notification Template By Id:', notificationTemplateBy);
});
```

**29. deleteNotificationTemplate**

```javascript
const $injector = self.ctx.$scope.$injector;
const notificationService = $injector.get(self.ctx.servicesMap.get('notificationService'));
const id = 'your-id';
notificationService.deleteNotificationTemplate(id).subscribe(result => {
  console.log('Delete Notification Template result:', result);
});
```

**30. getNotificationTemplates**

```javascript
const $injector = self.ctx.$scope.$injector;
const notificationService = $injector.get(self.ctx.servicesMap.get('notificationService'));
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const notificationTypes = {  // NotificationType object
  // ... set the fields you need
};
notificationService.getNotificationTemplates(pageLink, notificationTypes).subscribe(notificationTemplates => {
  console.log('List of Notification Templates:', notificationTemplates);
});
```

**31. getNotificationUserSettings**

```javascript
const $injector = self.ctx.$scope.$injector;
const notificationService = $injector.get(self.ctx.servicesMap.get('notificationService'));
notificationService.getNotificationUserSettings().subscribe(notificationUserSettings => {
  console.log('Get Notification User Settings:', notificationUserSettings);
});
```

**32. saveNotificationUserSettings**

```javascript
const $injector = self.ctx.$scope.$injector;
const notificationService = $injector.get(self.ctx.servicesMap.get('notificationService'));
const settings = {  // NotificationUserSettings object
  // ... set the fields you need
};
notificationService.saveNotificationUserSettings(settings).subscribe(savedNotificationUserSettings => {
  console.log('Saved Notification User Settings:', savedNotificationUserSettings);
});
```

**33. sendAddonAccessError**

```javascript
const $injector = self.ctx.$scope.$injector;
const notificationService = $injector.get(self.ctx.servicesMap.get('notificationService'));
const addonType = {  // AddonType object
  // ... set the fields you need
};
notificationService.sendAddonAccessError(addonType).subscribe(sendAddonAccessError => {
  console.log('Send Addon Access Error:', sendAddonAccessError);
});
```

### **O AUTH2 SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const oAuth2Service = $injector.get(self.ctx.servicesMap.get('oAuth2Service'));
```

**1. getOAuth2Template**

```javascript
const $injector = self.ctx.$scope.$injector;
const oAuth2Service = $injector.get(self.ctx.servicesMap.get('oAuth2Service'));
oAuth2Service.getOAuth2Template().subscribe(oAuth2Templates => {
  console.log('List of OAuth2 Templates:', oAuth2Templates);
});
```

**2. saveOAuth2Client**

```javascript
const $injector = self.ctx.$scope.$injector;
const oAuth2Service = $injector.get(self.ctx.servicesMap.get('oAuth2Service'));
const oAuth2Client = {  // OAuth2Client object
  // ... set the fields you need
};
oAuth2Service.saveOAuth2Client(oAuth2Client).subscribe(savedOAuth2Client => {
  console.log('Saved OAuth2 Client:', savedOAuth2Client);
});
```

**3. findTenantOAuth2ClientInfos**

```javascript
const $injector = self.ctx.$scope.$injector;
const oAuth2Service = $injector.get(self.ctx.servicesMap.get('oAuth2Service'));
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
oAuth2Service.findTenantOAuth2ClientInfos(pageLink).subscribe(tenantOAuth2ClientInfos => {
  console.log('List of Tenant OAuth2 Client Infos:', tenantOAuth2ClientInfos);
});
```

**4. findTenantOAuth2ClientInfosByIds**

```javascript
const $injector = self.ctx.$scope.$injector;
const oAuth2Service = $injector.get(self.ctx.servicesMap.get('oAuth2Service'));
const clientIds = ['your-client-i-1', 'your-client-i-2'];
oAuth2Service.findTenantOAuth2ClientInfosByIds(clientIds).subscribe(tenantOAuth2ClientInfosBys => {
  console.log('List of Tenant OAuth2 Client Infos By Ids:', tenantOAuth2ClientInfosBys);
});
```

**5. getOAuth2ClientById**

```javascript
const $injector = self.ctx.$scope.$injector;
const oAuth2Service = $injector.get(self.ctx.servicesMap.get('oAuth2Service'));
const id = 'your-id';
oAuth2Service.getOAuth2ClientById(id).subscribe(oAuth2ClientBy => {
  console.log('Get OAuth2 Client By Id:', oAuth2ClientBy);
});
```

**6. deleteOauth2Client**

```javascript
const $injector = self.ctx.$scope.$injector;
const oAuth2Service = $injector.get(self.ctx.servicesMap.get('oAuth2Service'));
const id = 'your-id';
oAuth2Service.deleteOauth2Client(id).subscribe(result => {
  console.log('Delete Oauth2 Client result:', result);
});
```

**7. getLoginProcessingUrl**

```javascript
const $injector = self.ctx.$scope.$injector;
const oAuth2Service = $injector.get(self.ctx.servicesMap.get('oAuth2Service'));
oAuth2Service.getLoginProcessingUrl().subscribe(loginProcessingUrl => {
  console.log('Get Login Processing Url:', loginProcessingUrl);
});
```

### **OTA PACKAGE SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const otaPackageService = $injector.get(self.ctx.servicesMap.get('otaPackageService'));
```

**1. getOtaPackages**

```javascript
const $injector = self.ctx.$scope.$injector;
const otaPackageService = $injector.get(self.ctx.servicesMap.get('otaPackageService'));
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
otaPackageService.getOtaPackages(pageLink).subscribe(otaPackages => {
  console.log('List of Ota Packages:', otaPackages);
});
```

**2. getOtaPackagesInfoByDeviceProfileId**

```javascript
const $injector = self.ctx.$scope.$injector;
const otaPackageService = $injector.get(self.ctx.servicesMap.get('otaPackageService'));
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const deviceProfileId = 'your-device-profile-id';
const type = {  // OtaUpdateType object
  // ... set the fields you need
};
otaPackageService.getOtaPackagesInfoByDeviceProfileId(pageLink, deviceProfileId, type).subscribe(otaPackagesInfoByDeviceProfiles => {
  console.log('List of Ota Packages Info By Device Profile Ids:', otaPackagesInfoByDeviceProfiles);
});
```

**3. getOtaPackage**

```javascript
const $injector = self.ctx.$scope.$injector;
const otaPackageService = $injector.get(self.ctx.servicesMap.get('otaPackageService'));
const otaPackageId = 'your-ota-package-id';
otaPackageService.getOtaPackage(otaPackageId).subscribe(otaPackage => {
  console.log('Get Ota Package:', otaPackage);
});
```

**4. getOtaPackageInfo**

```javascript
const $injector = self.ctx.$scope.$injector;
const otaPackageService = $injector.get(self.ctx.servicesMap.get('otaPackageService'));
const otaPackageId = 'your-ota-package-id';
otaPackageService.getOtaPackageInfo(otaPackageId).subscribe(otaPackageInfo => {
  console.log('Get Ota Package Info:', otaPackageInfo);
});
```

**5. downloadOtaPackage**

```javascript
const $injector = self.ctx.$scope.$injector;
const otaPackageService = $injector.get(self.ctx.servicesMap.get('otaPackageService'));
const otaPackageId = 'your-ota-package-id';
otaPackageService.downloadOtaPackage(otaPackageId).subscribe(downloadOtaPackage => {
  console.log('Download Ota Package:', downloadOtaPackage);
});
```

**6. saveOtaPackage**

```javascript
const $injector = self.ctx.$scope.$injector;
const otaPackageService = $injector.get(self.ctx.servicesMap.get('otaPackageService'));
const otaPackage = {  // OtaPackage object
  // ... set the fields you need
};
otaPackageService.saveOtaPackage(otaPackage).subscribe(savedOtaPackage => {
  console.log('Saved Ota Package:', savedOtaPackage);
});
```

**7. saveOtaPackageInfo**

```javascript
const $injector = self.ctx.$scope.$injector;
const otaPackageService = $injector.get(self.ctx.servicesMap.get('otaPackageService'));
const otaPackageInfo = {  // OtaPackageInfo object
  // ... set the fields you need
};
otaPackageService.saveOtaPackageInfo(otaPackageInfo).subscribe(savedOtaPackageInfo => {
  console.log('Saved Ota Package Info:', savedOtaPackageInfo);
});
```

**8. uploadOtaPackageFile**

```javascript
const $injector = self.ctx.$scope.$injector;
const otaPackageService = $injector.get(self.ctx.servicesMap.get('otaPackageService'));
const otaPackageId = 'your-ota-package-id';
const file = {  // File object
  // ... set the fields you need
};
const checksumAlgorithm = {  // ChecksumAlgorithm object
  // ... set the fields you need
};
const checksum = 'your-checksum';
otaPackageService.uploadOtaPackageFile(otaPackageId, file, checksumAlgorithm, checksum).subscribe(savedOtaPackageFile => {
  console.log('Saved Ota Package File:', savedOtaPackageFile);
});
```

**9. getOtaPackageInfoByDeviceGroupId**

```javascript
const $injector = self.ctx.$scope.$injector;
const otaPackageService = $injector.get(self.ctx.servicesMap.get('otaPackageService'));
const deviceGroupId = 'your-device-group-id';
const type = {  // OtaUpdateType object
  // ... set the fields you need
};
otaPackageService.getOtaPackageInfoByDeviceGroupId(deviceGroupId, type).subscribe(otaPackageInfoByDeviceGroup => {
  console.log('Get Ota Package Info By Device Group Id:', otaPackageInfoByDeviceGroup);
});
```

**10. getOtaPackagesInfoByDeviceGroupId**

```javascript
const $injector = self.ctx.$scope.$injector;
const otaPackageService = $injector.get(self.ctx.servicesMap.get('otaPackageService'));
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const deviceGroupId = 'your-device-group-id';
const type = {  // OtaUpdateType object
  // ... set the fields you need
};
otaPackageService.getOtaPackagesInfoByDeviceGroupId(pageLink, deviceGroupId, type).subscribe(otaPackagesInfoByDeviceGroups => {
  console.log('List of Ota Packages Info By Device Group Ids:', otaPackagesInfoByDeviceGroups);
});
```

**11. countUpdateDeviceAfterChangePackage**

```javascript
const $injector = self.ctx.$scope.$injector;
const otaPackageService = $injector.get(self.ctx.servicesMap.get('otaPackageService'));
const type = {  // OtaUpdateType object
  // ... set the fields you need
};
const entityId = {  // EntityId object
  // ... set the fields you need
};
const packageId = 'your-package-id';
otaPackageService.countUpdateDeviceAfterChangePackage(type, entityId, packageId).subscribe(countUpdateDeviceAfterChangePackage => {
  console.log('Count Update Device After Change Package:', countUpdateDeviceAfterChangePackage);
});
```

**12. confirmDialogUpdatePackage**

```javascript
const $injector = self.ctx.$scope.$injector;
const otaPackageService = $injector.get(self.ctx.servicesMap.get('otaPackageService'));
const entity = {  // BaseData<EntityId>&OtaPagesIds object
  // ... set the fields you need
};
const originEntity = {  // BaseData<EntityId>&OtaPagesIds object
  // ... set the fields you need
};
otaPackageService.confirmDialogUpdatePackage(entity, originEntity).subscribe(confirmDialogUpdatePackage => {
  console.log('Confirm Dialog Update Package:', confirmDialogUpdatePackage);
});
```

### **QUEUE SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const queueService = $injector.get(self.ctx.servicesMap.get('queueService'));
```

**1. getQueueById**

```javascript
const $injector = self.ctx.$scope.$injector;
const queueService = $injector.get(self.ctx.servicesMap.get('queueService'));
const queueId = 'your-queue-id';
queueService.getQueueById(queueId).subscribe(queueBy => {
  console.log('Get Queue By Id:', queueBy);
});
```

**2. getQueueByName**

```javascript
const $injector = self.ctx.$scope.$injector;
const queueService = $injector.get(self.ctx.servicesMap.get('queueService'));
const queueName = 'your-queue-name';
queueService.getQueueByName(queueName).subscribe(queueByName => {
  console.log('Get Queue By Name:', queueByName);
});
```

**3. getTenantQueuesByServiceType**

```javascript
const $injector = self.ctx.$scope.$injector;
const queueService = $injector.get(self.ctx.servicesMap.get('queueService'));
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const serviceType = {  // ServiceType object
  // ... set the fields you need
};
queueService.getTenantQueuesByServiceType(pageLink, serviceType).subscribe(tenantQueuesByServiceTypes => {
  console.log('List of Tenant Queues By Service Types:', tenantQueuesByServiceTypes);
});
```

**4. saveQueue**

```javascript
const $injector = self.ctx.$scope.$injector;
const queueService = $injector.get(self.ctx.servicesMap.get('queueService'));
const queue = {  // QueueInfo object
  // ... set the fields you need
};
const serviceType = {  // ServiceType object
  // ... set the fields you need
};
queueService.saveQueue(queue, serviceType).subscribe(savedQueue => {
  console.log('Saved Queue:', savedQueue);
});
```

**5. getQueueStatistics**

```javascript
const $injector = self.ctx.$scope.$injector;
const queueService = $injector.get(self.ctx.servicesMap.get('queueService'));
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
queueService.getQueueStatistics(pageLink).subscribe(queueStatistics => {
  console.log('List of Queue Statistics:', queueStatistics);
});
```

**6. getQueueStatisticsById**

```javascript
const $injector = self.ctx.$scope.$injector;
const queueService = $injector.get(self.ctx.servicesMap.get('queueService'));
const queueStatId = 'your-queue-stat-id';
queueService.getQueueStatisticsById(queueStatId).subscribe(queueStatisticsBy => {
  console.log('Get Queue Statistics By Id:', queueStatisticsBy);
});
```

**7. getQueueStatisticsByIds**

```javascript
const $injector = self.ctx.$scope.$injector;
const queueService = $injector.get(self.ctx.servicesMap.get('queueService'));
const queueStatIds = ['your-queue-stat-i-1', 'your-queue-stat-i-2'];
queueService.getQueueStatisticsByIds(queueStatIds).subscribe(queueStatisticsBys => {
  console.log('List of Queue Statistics By Ids:', queueStatisticsBys);
});
```

### **REPORT SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const reportService = $injector.get(self.ctx.servicesMap.get('reportService'));
```

**1. getReport**

```javascript
const $injector = self.ctx.$scope.$injector;
const reportService = $injector.get(self.ctx.servicesMap.get('reportService'));
const reportId = 'your-report-id';
reportService.getReport(reportId).subscribe(report => {
  console.log('Get Report:', report);
});
```

**2. getReports**

```javascript
const $injector = self.ctx.$scope.$injector;
const reportService = $injector.get(self.ctx.servicesMap.get('reportService'));
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
reportService.getReports(pageLink).subscribe(reports => {
  console.log('List of Reports:', reports);
});
```

**3. getReportInfos**

```javascript
const $injector = self.ctx.$scope.$injector;
const reportService = $injector.get(self.ctx.servicesMap.get('reportService'));
const query = {  // ReportQuery object
  // ... set the fields you need
};
reportService.getReportInfos(query).subscribe(reportInfos => {
  console.log('List of Report Infos:', reportInfos);
});
```

**4. downloadReport**

```javascript
const $injector = self.ctx.$scope.$injector;
const reportService = $injector.get(self.ctx.servicesMap.get('reportService'));
const reportId = 'your-report-id';
reportService.downloadReport(reportId).subscribe(downloadReport => {
  console.log('Download Report:', downloadReport);
});
```

**5. requestReport**

```javascript
const $injector = self.ctx.$scope.$injector;
const reportService = $injector.get(self.ctx.servicesMap.get('reportService'));
const reportRequest = {  // ReportRequest object
  // ... set the fields you need
};
reportService.requestReport(reportRequest).subscribe(requestReport => {
  console.log('Request Report:', requestReport);
});
```

**6. downloadTestReport**

```javascript
const $injector = self.ctx.$scope.$injector;
const reportService = $injector.get(self.ctx.servicesMap.get('reportService'));
const reportRequest = {  // ReportRequest object
  // ... set the fields you need
};
reportService.downloadTestReport(reportRequest).subscribe(downloadTestReport => {
  console.log('Download Test Report:', downloadTestReport);
});
```

**7. updateReportPublicStatus**

```javascript
const $injector = self.ctx.$scope.$injector;
const reportService = $injector.get(self.ctx.servicesMap.get('reportService'));
const reportId = 'your-report-id';
const isPublic = true;
reportService.updateReportPublicStatus(reportId, isPublic).subscribe(savedReportPublicStatus => {
  console.log('Saved Report Public Status:', savedReportPublicStatus);
});
```

**8. getPublicReportDownloadUrl**

```javascript
const $injector = self.ctx.$scope.$injector;
const reportService = $injector.get(self.ctx.servicesMap.get('reportService'));
const publicKey = 'your-public-key';
const result = reportService.getPublicReportDownloadUrl(publicKey);
console.log('Result:', result);
```

**9. getReportsInfosByIds**

```javascript
const $injector = self.ctx.$scope.$injector;
const reportService = $injector.get(self.ctx.servicesMap.get('reportService'));
const reportIds = ['your-report-i-1', 'your-report-i-2'];
reportService.getReportsInfosByIds(reportIds).subscribe(reportsInfosBys => {
  console.log('List of Reports Infos By Ids:', reportsInfosBys);
});
```

**10. processDownloadReportResponse**

```javascript
const $injector = self.ctx.$scope.$injector;
const reportService = $injector.get(self.ctx.servicesMap.get('reportService'));
const response = {  // Observable<HttpResponse<ArrayBuffer>> object
  // ... set the fields you need
};
reportService.processDownloadReportResponse(response).subscribe(processDownloadReportResponse => {
  console.log('Process Download Report Response:', processDownloadReportResponse);
});
```

### **REPORT TEMPLATE SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const reportTemplateService = $injector.get(self.ctx.servicesMap.get('reportTemplateService'));
```

**1. getReportTemplateInfo**

```javascript
const $injector = self.ctx.$scope.$injector;
const reportTemplateService = $injector.get(self.ctx.servicesMap.get('reportTemplateService'));
const reportTemplateId = 'your-report-template-id';
reportTemplateService.getReportTemplateInfo(reportTemplateId).subscribe(reportTemplateInfo => {
  console.log('Get Report Template Info:', reportTemplateInfo);
});
```

**2. getAllReportTemplateInfos**

```javascript
const $injector = self.ctx.$scope.$injector;
const reportTemplateService = $injector.get(self.ctx.servicesMap.get('reportTemplateService'));
const query = {  // ReportTemplateQuery object
  // ... set the fields you need
};
reportTemplateService.getAllReportTemplateInfos(query).subscribe(allReportTemplateInfos => {
  console.log('List of All Report Template Infos:', allReportTemplateInfos);
});
```

**3. getReportTemplatesByIds**

```javascript
const $injector = self.ctx.$scope.$injector;
const reportTemplateService = $injector.get(self.ctx.servicesMap.get('reportTemplateService'));
const reportTemplateIds = ['your-report-template-i-1', 'your-report-template-i-2'];
reportTemplateService.getReportTemplatesByIds(reportTemplateIds).subscribe(reportTemplatesBys => {
  console.log('List of Report Templates By Ids:', reportTemplatesBys);
});
```

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
const resourceService = self.ctx.resourceService;
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const resourceType = [];  // e.g. array of resource-type values
const resourceSubType = {  // ResourceSubType object
  // ... set the fields you need
};
resourceService.getResources(pageLink, resourceType, resourceSubType).subscribe(resources => {
  console.log('List of Resources:', resources);
});
```

**2. getTenantResources**

```javascript
const resourceService = self.ctx.resourceService;
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
resourceService.getTenantResources(pageLink).subscribe(tenantResources => {
  console.log('List of Tenant Resources:', tenantResources);
});
```

**3. getResource**

```javascript
const resourceService = self.ctx.resourceService;
const resourceId = 'your-resource-id';
resourceService.getResource(resourceId).subscribe(resource => {
  console.log('Get Resource:', resource);
});
```

**4. getResourceInfoById**

```javascript
const resourceService = self.ctx.resourceService;
const resourceId = 'your-resource-id';
resourceService.getResourceInfoById(resourceId).subscribe(resourceInfoBy => {
  console.log('Get Resource Info By Id:', resourceInfoBy);
});
```

**5. getResourceInfo**

```javascript
const resourceService = self.ctx.resourceService;
const type = {  // ResourceType object
  // ... set the fields you need
};
const scope = {  // TBResourceScope object
  // ... set the fields you need
};
const key = 'key-value';
resourceService.getResourceInfo(type, scope, key).subscribe(resourceInfo => {
  console.log('Get Resource Info:', resourceInfo);
});
```

**6. downloadResource**

```javascript
const resourceService = self.ctx.resourceService;
const resourceId = 'your-resource-id';
resourceService.downloadResource(resourceId).subscribe(downloadResource => {
  console.log('Download Resource:', downloadResource);
});
```

**7. saveResources**

```javascript
const resourceService = self.ctx.resourceService;
const resources = [];  // e.g. array of resources values
resourceService.saveResources(resources).subscribe(savedResources => {
  console.log('Saved Resources:', savedResources);
});
```

**8. saveResource**

```javascript
const resourceService = self.ctx.resourceService;
const resource = {  // Resource object
  // ... set the fields you need
};
resourceService.saveResource(resource).subscribe(savedResource => {
  console.log('Saved Resource:', savedResource);
});
```

**9. uploadResources**

```javascript
const resourceService = self.ctx.resourceService;
const resources = [];  // e.g. array of resources values
resourceService.uploadResources(resources).subscribe(savedResources => {
  console.log('Saved Resources:', savedResources);
});
```

**10. uploadResource**

```javascript
const resourceService = self.ctx.resourceService;
const resource = {  // Resource object
  // ... set the fields you need
};
resourceService.uploadResource(resource).subscribe(savedResource => {
  console.log('Saved Resource:', savedResource);
});
```

**11. updatedResourceInfo**

```javascript
const resourceService = self.ctx.resourceService;
const resourceId = 'your-resource-id';
const updatedResources = {  // Partial<Omit<Resource object
  // ... set the fields you need
};
resourceService.updatedResourceInfo(resourceId, updatedResources).subscribe(saveddResourceInfo => {
  console.log('Saved Updated Resource Info:', saveddResourceInfo);
});
```

**12. updatedResourceData**

```javascript
const resourceService = self.ctx.resourceService;
const resourceId = 'your-resource-id';
const data = {  // File object
  // ... set the fields you need
};
resourceService.updatedResourceData(resourceId, data).subscribe(saveddResourceData => {
  console.log('Saved Updated Resource Data:', saveddResourceData);
});
```

**13. getResourcesByIds**

```javascript
const resourceService = self.ctx.resourceService;
const ids = [];  // e.g. array of ids values
resourceService.getResourcesByIds(ids).subscribe(resourcesBys => {
  console.log('List of Resources By Ids:', resourcesBys);
});
```

### **ROLE SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const roleService = $injector.get(self.ctx.servicesMap.get('roleService'));
```

**1. getRoles**

```javascript
const $injector = self.ctx.$scope.$injector;
const roleService = $injector.get(self.ctx.servicesMap.get('roleService'));
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const type = {  // RoleType object
  // ... set the fields you need
};
roleService.getRoles(pageLink, type).subscribe(roles => {
  console.log('List of Roles:', roles);
});
```

**2. getRolesByIds**

```javascript
const $injector = self.ctx.$scope.$injector;
const roleService = $injector.get(self.ctx.servicesMap.get('roleService'));
const roleIds = ['your-role-i-1', 'your-role-i-2'];
roleService.getRolesByIds(roleIds).subscribe(rolesBys => {
  console.log('List of Roles By Ids:', rolesBys);
});
```

**3. getRole**

```javascript
const $injector = self.ctx.$scope.$injector;
const roleService = $injector.get(self.ctx.servicesMap.get('roleService'));
const roleId = 'your-role-id';
roleService.getRole(roleId).subscribe(role => {
  console.log('Get Role:', role);
});
```

**4. saveRole**

```javascript
const $injector = self.ctx.$scope.$injector;
const roleService = $injector.get(self.ctx.servicesMap.get('roleService'));
const role = {  // Role object
  // ... set the fields you need
};
roleService.saveRole(role).subscribe(savedRole => {
  console.log('Saved Role:', savedRole);
});
```

**5. saveGroupPermission**

```javascript
const $injector = self.ctx.$scope.$injector;
const roleService = $injector.get(self.ctx.servicesMap.get('roleService'));
const groupPermission = {  // GroupPermission object
  // ... set the fields you need
};
roleService.saveGroupPermission(groupPermission).subscribe(savedGroupPermission => {
  console.log('Saved Group Permission:', savedGroupPermission);
});
```

**6. deleteGroupPermissions**

```javascript
const $injector = self.ctx.$scope.$injector;
const roleService = $injector.get(self.ctx.servicesMap.get('roleService'));
const groupPermissionIds = ['your-group-permission-i-1', 'your-group-permission-i-2'];
roleService.deleteGroupPermissions(groupPermissionIds).subscribe(result => {
  console.log('Delete Group Permissions result:', result);
});
```

**7. deleteGroupPermission**

```javascript
const $injector = self.ctx.$scope.$injector;
const roleService = $injector.get(self.ctx.servicesMap.get('roleService'));
const groupPermissionId = 'your-group-permission-id';
roleService.deleteGroupPermission(groupPermissionId).subscribe(result => {
  console.log('Delete Group Permission result:', result);
});
```

**8. getUserGroupPermissions**

```javascript
const $injector = self.ctx.$scope.$injector;
const roleService = $injector.get(self.ctx.servicesMap.get('roleService'));
const userGroupId = 'your-user-group-id';
roleService.getUserGroupPermissions(userGroupId).subscribe(userGroupPermissions => {
  console.log('List of User Group Permissions:', userGroupPermissions);
});
```

**9. getEntityGroupPermissions**

```javascript
const $injector = self.ctx.$scope.$injector;
const roleService = $injector.get(self.ctx.servicesMap.get('roleService'));
const entityGroupId = 'your-entity-group-id';
roleService.getEntityGroupPermissions(entityGroupId).subscribe(entityGroupPermissions => {
  console.log('List of Entity Group Permissions:', entityGroupPermissions);
});
```

**10. getGroupPermissionInfo**

```javascript
const $injector = self.ctx.$scope.$injector;
const roleService = $injector.get(self.ctx.servicesMap.get('roleService'));
const groupPermissionId = 'your-group-permission-id';
const isUserGroup = true;
roleService.getGroupPermissionInfo(groupPermissionId, isUserGroup).subscribe(groupPermissionInfo => {
  console.log('Get Group Permission Info:', groupPermissionInfo);
});
```

**11. loadUserGroupPermissionInfos**

```javascript
const $injector = self.ctx.$scope.$injector;
const roleService = $injector.get(self.ctx.servicesMap.get('roleService'));
const groupPermissions = [];  // e.g. array of group-permissions values
roleService.loadUserGroupPermissionInfos(groupPermissions).subscribe(userGroupPermissionInfos => {
  console.log('List of User Group Permission Infos:', userGroupPermissionInfos);
});
```

### **RULE CHAIN SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const ruleChainService = $injector.get(self.ctx.servicesMap.get('ruleChainService'));
```

**1. getRuleChains**

```javascript
const $injector = self.ctx.$scope.$injector;
const ruleChainService = $injector.get(self.ctx.servicesMap.get('ruleChainService'));
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const type = 'value';
ruleChainService.getRuleChains(pageLink, type).subscribe(ruleChains => {
  console.log('List of Rule Chains:', ruleChains);
});
```

**2. getRuleChainsByIds**

```javascript
const $injector = self.ctx.$scope.$injector;
const ruleChainService = $injector.get(self.ctx.servicesMap.get('ruleChainService'));
const ruleChainIds = ['your-rule-chain-i-1', 'your-rule-chain-i-2'];
ruleChainService.getRuleChainsByIds(ruleChainIds).subscribe(ruleChainsBys => {
  console.log('List of Rule Chains By Ids:', ruleChainsBys);
});
```

**3. getRuleChain**

```javascript
const $injector = self.ctx.$scope.$injector;
const ruleChainService = $injector.get(self.ctx.servicesMap.get('ruleChainService'));
const ruleChainId = 'your-rule-chain-id';
ruleChainService.getRuleChain(ruleChainId).subscribe(ruleChain => {
  console.log('Get Rule Chain:', ruleChain);
});
```

**4. getRuleChainOutputLabels**

```javascript
const $injector = self.ctx.$scope.$injector;
const ruleChainService = $injector.get(self.ctx.servicesMap.get('ruleChainService'));
const ruleChainId = 'your-rule-chain-id';
ruleChainService.getRuleChainOutputLabels(ruleChainId).subscribe(ruleChainOutputLabels => {
  console.log('List of Rule Chain Output Labels:', ruleChainOutputLabels);
});
```

**5. createDefaultRuleChain**

```javascript
const $injector = self.ctx.$scope.$injector;
const ruleChainService = $injector.get(self.ctx.servicesMap.get('ruleChainService'));
const ruleChainName = 'your-rule-chain-name';
ruleChainService.createDefaultRuleChain(ruleChainName).subscribe(createDefaultRuleChain => {
  console.log('Create Default Rule Chain:', createDefaultRuleChain);
});
```

**6. saveRuleChain**

```javascript
const $injector = self.ctx.$scope.$injector;
const ruleChainService = $injector.get(self.ctx.servicesMap.get('ruleChainService'));
const ruleChain = {  // RuleChain object
  // ... set the fields you need
};
ruleChainService.saveRuleChain(ruleChain).subscribe(savedRuleChain => {
  console.log('Saved Rule Chain:', savedRuleChain);
});
```

**7. setRootRuleChain**

```javascript
const $injector = self.ctx.$scope.$injector;
const ruleChainService = $injector.get(self.ctx.servicesMap.get('ruleChainService'));
const ruleChainId = 'your-rule-chain-id';
ruleChainService.setRootRuleChain(ruleChainId).subscribe(setRootRuleChain => {
  console.log('Set Root Rule Chain:', setRootRuleChain);
});
```

**8. getRuleChainMetadata**

```javascript
const $injector = self.ctx.$scope.$injector;
const ruleChainService = $injector.get(self.ctx.servicesMap.get('ruleChainService'));
const ruleChainId = 'your-rule-chain-id';
ruleChainService.getRuleChainMetadata(ruleChainId).subscribe(ruleChainMetadata => {
  console.log('Get Rule Chain Metadata:', ruleChainMetadata);
});
```

**9. saveRuleChainMetadata**

```javascript
const $injector = self.ctx.$scope.$injector;
const ruleChainService = $injector.get(self.ctx.servicesMap.get('ruleChainService'));
const ruleChainMetaData = {  // RuleChainMetaData object
  // ... set the fields you need
};
ruleChainService.saveRuleChainMetadata(ruleChainMetaData).subscribe(savedRuleChainMetadata => {
  console.log('Saved Rule Chain Metadata:', savedRuleChainMetadata);
});
```

**10. getRuleNodeComponents**

```javascript
const $injector = self.ctx.$scope.$injector;
const ruleChainService = $injector.get(self.ctx.servicesMap.get('ruleChainService'));
const modulesMap = {  // IModulesMap object
  // ... set the fields you need
};
const ruleChainType = {  // RuleChainType object
  // ... set the fields you need
};
ruleChainService.getRuleNodeComponents(modulesMap, ruleChainType).subscribe(ruleNodeComponents => {
  console.log('List of Rule Node Components:', ruleNodeComponents);
});
```

**11. getRuleNodeConfigComponent**

```javascript
const $injector = self.ctx.$scope.$injector;
const ruleChainService = $injector.get(self.ctx.servicesMap.get('ruleChainService'));
const directive = 'your-directive';
const result = ruleChainService.getRuleNodeConfigComponent(directive);
console.log('Result:', result);
```

**12. getRuleNodeComponentByClazz**

```javascript
const $injector = self.ctx.$scope.$injector;
const ruleChainService = $injector.get(self.ctx.servicesMap.get('ruleChainService'));
const ruleChainType = 'value';
const clazz = 'your-clazz';
const result = ruleChainService.getRuleNodeComponentByClazz(ruleChainType, clazz);
console.log('Result:', result);
```

**13. getRuleNodeSupportedLinks**

```javascript
const $injector = self.ctx.$scope.$injector;
const ruleChainService = $injector.get(self.ctx.servicesMap.get('ruleChainService'));
const component = {  // RuleNodeComponentDescriptor object
  // ... set the fields you need
};
const result = ruleChainService.getRuleNodeSupportedLinks(component);
console.log('Result:', result);
```

**14. ruleNodeAllowCustomLinks**

```javascript
const $injector = self.ctx.$scope.$injector;
const ruleChainService = $injector.get(self.ctx.servicesMap.get('ruleChainService'));
const component = {  // RuleNodeComponentDescriptor object
  // ... set the fields you need
};
const result = ruleChainService.ruleNodeAllowCustomLinks(component);
console.log('Result:', result);
```

**15. ruleNodeSourceRuleChainId**

```javascript
const $injector = self.ctx.$scope.$injector;
const ruleChainService = $injector.get(self.ctx.servicesMap.get('ruleChainService'));
const component = {  // RuleNodeComponentDescriptor object
  // ... set the fields you need
};
const config = {  // RuleNodeConfiguration object
  // ... set the fields you need
};
const result = ruleChainService.ruleNodeSourceRuleChainId(component, config);
console.log('Result:', result);
```

**16. getLatestRuleNodeDebugInput**

```javascript
const $injector = self.ctx.$scope.$injector;
const ruleChainService = $injector.get(self.ctx.servicesMap.get('ruleChainService'));
const ruleNodeId = 'your-rule-node-id';
ruleChainService.getLatestRuleNodeDebugInput(ruleNodeId).subscribe(latestRuleNodeDebugInput => {
  console.log('Get Latest Rule Node Debug Input:', latestRuleNodeDebugInput);
});
```

**17. testScript**

```javascript
const $injector = self.ctx.$scope.$injector;
const ruleChainService = $injector.get(self.ctx.servicesMap.get('ruleChainService'));
const inputParams = {  // TestScriptInputParams object
  // ... set the fields you need
};
const scriptLang = {  // ScriptLanguage object
  // ... set the fields you need
};
ruleChainService.testScript(inputParams, scriptLang).subscribe(testScript => {
  console.log('Test Script:', testScript);
});
```

**18. loadRuleNodeComponents**

```javascript
const $injector = self.ctx.$scope.$injector;
const ruleChainService = $injector.get(self.ctx.servicesMap.get('ruleChainService'));
const ruleChainType = {  // RuleChainType object
  // ... set the fields you need
};
ruleChainService.loadRuleNodeComponents(ruleChainType).subscribe(ruleNodeComponents => {
  console.log('List of Rule Node Components:', ruleNodeComponents);
});
```

**19. resolveRuleNodeComponentsUiResources**

```javascript
const $injector = self.ctx.$scope.$injector;
const ruleChainService = $injector.get(self.ctx.servicesMap.get('ruleChainService'));
const components = [];  // e.g. array of components values
const modulesMap = {  // IModulesMap object
  // ... set the fields you need
};
ruleChainService.resolveRuleNodeComponentsUiResources(components, modulesMap).subscribe(resolveRuleNodeComponentsUiResources => {
  console.log('List of Resolve Rule Node Components Ui Resources:', resolveRuleNodeComponentsUiResources);
});
```

**20. resolveRuleNodeComponentUiResources**

```javascript
const $injector = self.ctx.$scope.$injector;
const ruleChainService = $injector.get(self.ctx.servicesMap.get('ruleChainService'));
const component = {  // RuleNodeComponentDescriptor object
  // ... set the fields you need
};
const modulesMap = {  // IModulesMap object
  // ... set the fields you need
};
ruleChainService.resolveRuleNodeComponentUiResources(component, modulesMap).subscribe(resolveRuleNodeComponentUiResources => {
  console.log('Resolve Rule Node Component Ui Resources:', resolveRuleNodeComponentUiResources);
});
```

**21. getEdgeRuleChains**

```javascript
const $injector = self.ctx.$scope.$injector;
const ruleChainService = $injector.get(self.ctx.servicesMap.get('ruleChainService'));
const edgeId = 'your-edge-id';
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
ruleChainService.getEdgeRuleChains(edgeId, pageLink).subscribe(edgeRuleChains => {
  console.log('List of Edge Rule Chains:', edgeRuleChains);
});
```

**22. assignRuleChainToEdge**

```javascript
const $injector = self.ctx.$scope.$injector;
const ruleChainService = $injector.get(self.ctx.servicesMap.get('ruleChainService'));
const edgeId = 'your-edge-id';
const ruleChainId = 'your-rule-chain-id';
ruleChainService.assignRuleChainToEdge(edgeId, ruleChainId).subscribe(assignRuleChainToEdge => {
  console.log('Assign Rule Chain To Edge:', assignRuleChainToEdge);
});
```

**23. setEdgeTemplateRootRuleChain**

```javascript
const $injector = self.ctx.$scope.$injector;
const ruleChainService = $injector.get(self.ctx.servicesMap.get('ruleChainService'));
const ruleChainId = 'your-rule-chain-id';
ruleChainService.setEdgeTemplateRootRuleChain(ruleChainId).subscribe(setEdgeTemplateRootRuleChain => {
  console.log('Set Edge Template Root Rule Chain:', setEdgeTemplateRootRuleChain);
});
```

**24. setAutoAssignToEdgeRuleChain**

```javascript
const $injector = self.ctx.$scope.$injector;
const ruleChainService = $injector.get(self.ctx.servicesMap.get('ruleChainService'));
const ruleChainId = 'your-rule-chain-id';
ruleChainService.setAutoAssignToEdgeRuleChain(ruleChainId).subscribe(setAutoAssignToEdgeRuleChain => {
  console.log('Set Auto Assign To Edge Rule Chain:', setAutoAssignToEdgeRuleChain);
});
```

**25. unsetAutoAssignToEdgeRuleChain**

```javascript
const $injector = self.ctx.$scope.$injector;
const ruleChainService = $injector.get(self.ctx.servicesMap.get('ruleChainService'));
const ruleChainId = 'your-rule-chain-id';
ruleChainService.unsetAutoAssignToEdgeRuleChain(ruleChainId).subscribe(unsetAutoAssignToEdgeRuleChain => {
  console.log('Unset Auto Assign To Edge Rule Chain:', unsetAutoAssignToEdgeRuleChain);
});
```

**26. getAutoAssignToEdgeRuleChains**

```javascript
const $injector = self.ctx.$scope.$injector;
const ruleChainService = $injector.get(self.ctx.servicesMap.get('ruleChainService'));
ruleChainService.getAutoAssignToEdgeRuleChains().subscribe(autoAssignToEdgeRuleChains => {
  console.log('List of Auto Assign To Edge Rule Chains:', autoAssignToEdgeRuleChains);
});
```

**27. setEdgeRootRuleChain**

```javascript
const $injector = self.ctx.$scope.$injector;
const ruleChainService = $injector.get(self.ctx.servicesMap.get('ruleChainService'));
const edgeId = 'your-edge-id';
const ruleChainId = 'your-rule-chain-id';
ruleChainService.setEdgeRootRuleChain(edgeId, ruleChainId).subscribe(setEdgeRootRuleChain => {
  console.log('Set Edge Root Rule Chain:', setEdgeRootRuleChain);
});
```

### **SCHEDULER EVENT SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const schedulerEventService = $injector.get(self.ctx.servicesMap.get('schedulerEventService'));
```

**1. getSchedulerEvents**

```javascript
const $injector = self.ctx.$scope.$injector;
const schedulerEventService = $injector.get(self.ctx.servicesMap.get('schedulerEventService'));
const type = 'value';
schedulerEventService.getSchedulerEvents(type).subscribe(schedulerEvents => {
  console.log('List of Scheduler Events:', schedulerEvents);
});
```

**2. getSchedulerEventsByPageLink**

```javascript
const $injector = self.ctx.$scope.$injector;
const schedulerEventService = $injector.get(self.ctx.servicesMap.get('schedulerEventService'));
const type = 'type-value';
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const edgeId = 'your-edge-id';
schedulerEventService.getSchedulerEventsByPageLink(type, pageLink, edgeId).subscribe(schedulerEventsByPageLinks => {
  console.log('List of Scheduler Events By Page Links:', schedulerEventsByPageLinks);
});
```

**3. getCalendarSchedulerEvents**

```javascript
const $injector = self.ctx.$scope.$injector;
const schedulerEventService = $injector.get(self.ctx.servicesMap.get('schedulerEventService'));
const type = 'type-value';
const startTime = 10;
const endTime = 10;
const textSearch = 'your-text-search';
const edgeId = 'your-edge-id';
schedulerEventService.getCalendarSchedulerEvents(type, startTime, endTime, textSearch, edgeId).subscribe(calendarSchedulerEvents => {
  console.log('List of Calendar Scheduler Events:', calendarSchedulerEvents);
});
```

**4. getSchedulerEventsByIds**

```javascript
const $injector = self.ctx.$scope.$injector;
const schedulerEventService = $injector.get(self.ctx.servicesMap.get('schedulerEventService'));
const schedulerEventIds = ['your-scheduler-event-i-1', 'your-scheduler-event-i-2'];
schedulerEventService.getSchedulerEventsByIds(schedulerEventIds).subscribe(schedulerEventsBys => {
  console.log('List of Scheduler Events By Ids:', schedulerEventsBys);
});
```

**5. getSchedulerEventInfo**

```javascript
const $injector = self.ctx.$scope.$injector;
const schedulerEventService = $injector.get(self.ctx.servicesMap.get('schedulerEventService'));
const schedulerEventId = 'your-scheduler-event-id';
schedulerEventService.getSchedulerEventInfo(schedulerEventId).subscribe(schedulerEventInfo => {
  console.log('Get Scheduler Event Info:', schedulerEventInfo);
});
```

**6. getSchedulerEvent**

```javascript
const $injector = self.ctx.$scope.$injector;
const schedulerEventService = $injector.get(self.ctx.servicesMap.get('schedulerEventService'));
const schedulerEventId = 'your-scheduler-event-id';
schedulerEventService.getSchedulerEvent(schedulerEventId).subscribe(schedulerEvent => {
  console.log('Get Scheduler Event:', schedulerEvent);
});
```

**7. saveSchedulerEvent**

```javascript
const $injector = self.ctx.$scope.$injector;
const schedulerEventService = $injector.get(self.ctx.servicesMap.get('schedulerEventService'));
const schedulerEvent = {  // SchedulerEvent object
  // ... set the fields you need
};
schedulerEventService.saveSchedulerEvent(schedulerEvent).subscribe(savedSchedulerEvent => {
  console.log('Saved Scheduler Event:', savedSchedulerEvent);
});
```

**8. getEdgeSchedulerEvents**

```javascript
const $injector = self.ctx.$scope.$injector;
const schedulerEventService = $injector.get(self.ctx.servicesMap.get('schedulerEventService'));
const edgeId = 'your-edge-id';
schedulerEventService.getEdgeSchedulerEvents(edgeId).subscribe(edgeSchedulerEvents => {
  console.log('List of Edge Scheduler Events:', edgeSchedulerEvents);
});
```

**9. assignSchedulerEventToEdge**

```javascript
const $injector = self.ctx.$scope.$injector;
const schedulerEventService = $injector.get(self.ctx.servicesMap.get('schedulerEventService'));
const edgeId = 'your-edge-id';
const schedulerEventId = 'your-scheduler-event-id';
schedulerEventService.assignSchedulerEventToEdge(edgeId, schedulerEventId).subscribe(assignSchedulerEventToEdge => {
  console.log('Assign Scheduler Event To Edge:', assignSchedulerEventToEdge);
});
```

**10. getScheduledReports**

```javascript
const $injector = self.ctx.$scope.$injector;
const schedulerEventService = $injector.get(self.ctx.servicesMap.get('schedulerEventService'));
const query = {  // ReportQuery object
  // ... set the fields you need
};
schedulerEventService.getScheduledReports(query).subscribe(scheduledReports => {
  console.log('List of Scheduled Reports:', scheduledReports);
});
```

### **SECRET STORAGE SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const secretStorageService = $injector.get(self.ctx.servicesMap.get('secretStorageService'));
```

**1. getSecrets**

```javascript
const $injector = self.ctx.$scope.$injector;
const secretStorageService = $injector.get(self.ctx.servicesMap.get('secretStorageService'));
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
secretStorageService.getSecrets(pageLink).subscribe(secrets => {
  console.log('List of Secrets:', secrets);
});
```

**2. saveSecret**

```javascript
const $injector = self.ctx.$scope.$injector;
const secretStorageService = $injector.get(self.ctx.servicesMap.get('secretStorageService'));
const secret = {  // SecretStorageInfo object
  // ... set the fields you need
};
secretStorageService.saveSecret(secret).subscribe(savedSecret => {
  console.log('Saved Secret:', savedSecret);
});
```

**3. updateSecretDescription**

```javascript
const $injector = self.ctx.$scope.$injector;
const secretStorageService = $injector.get(self.ctx.servicesMap.get('secretStorageService'));
const secretId = 'your-secret-id';
const description = 'your-description';
secretStorageService.updateSecretDescription(secretId, description).subscribe(savedSecretDescription => {
  console.log('Saved Secret Description:', savedSecretDescription);
});
```

**4. updateSecretValue**

```javascript
const $injector = self.ctx.$scope.$injector;
const secretStorageService = $injector.get(self.ctx.servicesMap.get('secretStorageService'));
const secretId = 'your-secret-id';
const value = 'your-value';
secretStorageService.updateSecretValue(secretId, value).subscribe(savedSecretValue => {
  console.log('Saved Secret Value:', savedSecretValue);
});
```

**5. getSecretByName**

```javascript
const $injector = self.ctx.$scope.$injector;
const secretStorageService = $injector.get(self.ctx.servicesMap.get('secretStorageService'));
const name = 'name-value';
secretStorageService.getSecretByName(name).subscribe(secretByName => {
  console.log('Get Secret By Name:', secretByName);
});
```

### **SELF REGISTRATION SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const selfRegistrationService = $injector.get(self.ctx.servicesMap.get('selfRegistrationService'));
```

**1. getRegistrationLink**

```javascript
const $injector = self.ctx.$scope.$injector;
const selfRegistrationService = $injector.get(self.ctx.servicesMap.get('selfRegistrationService'));
const domainName = 'your-domain-name';
const result = selfRegistrationService.getRegistrationLink(domainName);
console.log('Result:', result);
```

**2. loadSelfRegistrationParams**

```javascript
const $injector = self.ctx.$scope.$injector;
const selfRegistrationService = $injector.get(self.ctx.servicesMap.get('selfRegistrationService'));
selfRegistrationService.loadSelfRegistrationParams().subscribe(selfRegistrationParams => {
  console.log('Load Self Registration Params:', selfRegistrationParams);
});
```

**3. loadPrivacyPolicy**

```javascript
const $injector = self.ctx.$scope.$injector;
const selfRegistrationService = $injector.get(self.ctx.servicesMap.get('selfRegistrationService'));
selfRegistrationService.loadPrivacyPolicy().subscribe(privacyPolicy => {
  console.log('Load Privacy Policy:', privacyPolicy);
});
```

**4. loadTermsOfUse**

```javascript
const $injector = self.ctx.$scope.$injector;
const selfRegistrationService = $injector.get(self.ctx.servicesMap.get('selfRegistrationService'));
selfRegistrationService.loadTermsOfUse().subscribe(termsOfUse => {
  console.log('Load Terms Of Use:', termsOfUse);
});
```

**5. isAvailablePage**

```javascript
const $injector = self.ctx.$scope.$injector;
const selfRegistrationService = $injector.get(self.ctx.servicesMap.get('selfRegistrationService'));
selfRegistrationService.isAvailablePage().subscribe(isAvailablePage => {
  console.log('Is Available Page:', isAvailablePage);
});
```

**6. saveSelfRegistrationParams**

```javascript
const $injector = self.ctx.$scope.$injector;
const selfRegistrationService = $injector.get(self.ctx.servicesMap.get('selfRegistrationService'));
const selfRegistrationParams = {  // WebSelfRegistrationParams object
  // ... set the fields you need
};
selfRegistrationService.saveSelfRegistrationParams(selfRegistrationParams).subscribe(savedSelfRegistrationParams => {
  console.log('Saved Self Registration Params:', savedSelfRegistrationParams);
});
```

**7. getSelfRegistrationParams**

```javascript
const $injector = self.ctx.$scope.$injector;
const selfRegistrationService = $injector.get(self.ctx.servicesMap.get('selfRegistrationService'));
selfRegistrationService.getSelfRegistrationParams().subscribe(selfRegistrationParams => {
  console.log('Get Self Registration Params:', selfRegistrationParams);
});
```

### **SIGNUP SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const signupService = $injector.get(self.ctx.servicesMap.get('signupService'));
```

**1. signup**

```javascript
const $injector = self.ctx.$scope.$injector;
const signupService = $injector.get(self.ctx.servicesMap.get('signupService'));
const signupRequest = {  // SignupRequestValues object
  // ... set the fields you need
};
signupService.signup(signupRequest).subscribe(signup => {
  console.log('Signup:', signup);
});
```

**2. acceptPrivacyPolicy**

```javascript
const $injector = self.ctx.$scope.$injector;
const signupService = $injector.get(self.ctx.servicesMap.get('signupService'));
signupService.acceptPrivacyPolicy().subscribe(acceptPrivacyPolicy => {
  console.log('Accept Privacy Policy:', acceptPrivacyPolicy);
});
```

**3. deleteTenantAccount**

```javascript
const $injector = self.ctx.$scope.$injector;
const signupService = $injector.get(self.ctx.servicesMap.get('signupService'));
signupService.deleteTenantAccount().subscribe(result => {
  console.log('Delete Tenant Account result:', result);
});
```

**4. isDisplayWelcome**

```javascript
const $injector = self.ctx.$scope.$injector;
const signupService = $injector.get(self.ctx.servicesMap.get('signupService'));
signupService.isDisplayWelcome().subscribe(isDisplayWelcome => {
  console.log('Is Display Welcome:', isDisplayWelcome);
});
```

**5. setNotDisplayWelcome**

```javascript
const $injector = self.ctx.$scope.$injector;
const signupService = $injector.get(self.ctx.servicesMap.get('signupService'));
signupService.setNotDisplayWelcome().subscribe(setNotDisplayWelcome => {
  console.log('Set Not Display Welcome:', setNotDisplayWelcome);
});
```

### **SOLUTIONS CREATOR SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const solutionsCreatorService = $injector.get(self.ctx.servicesMap.get('solutionsCreatorService'));
```

**1. getSolutionById**

```javascript
const $injector = self.ctx.$scope.$injector;
const solutionsCreatorService = $injector.get(self.ctx.servicesMap.get('solutionsCreatorService'));
const solutionId = 'your-solution-id';
solutionsCreatorService.getSolutionById(solutionId).subscribe(solutionBy => {
  console.log('Get Solution By Id:', solutionBy);
});
```

**2. startSolution**

```javascript
const $injector = self.ctx.$scope.$injector;
const solutionsCreatorService = $injector.get(self.ctx.servicesMap.get('solutionsCreatorService'));
solutionsCreatorService.startSolution().subscribe(startSolution => {
  console.log('Start Solution:', startSolution);
});
```

**3. clearStep**

```javascript
const $injector = self.ctx.$scope.$injector;
const solutionsCreatorService = $injector.get(self.ctx.servicesMap.get('solutionsCreatorService'));
const solutionId = 'your-solution-id';
const step = {  // SolutionStep object
  // ... set the fields you need
};
solutionsCreatorService.clearStep(solutionId, step).subscribe(clearStep => {
  console.log('Clear Step:', clearStep);
});
```

**4. createSolution**

```javascript
const $injector = self.ctx.$scope.$injector;
const solutionsCreatorService = $injector.get(self.ctx.servicesMap.get('solutionsCreatorService'));
const solutionId = 'your-solution-id';
solutionsCreatorService.createSolution(solutionId).subscribe(createSolution => {
  console.log('Create Solution:', createSolution);
});
```

**5. chatSolution**

```javascript
const $injector = self.ctx.$scope.$injector;
const solutionsCreatorService = $injector.get(self.ctx.servicesMap.get('solutionsCreatorService'));
const solutionId = 'your-solution-id';
const step = {  // SolutionStep object
  // ... set the fields you need
};
const msg = 'your-msg';
solutionsCreatorService.chatSolution(solutionId, step, msg).subscribe(chatSolution => {
  console.log('Chat Solution:', chatSolution);
});
```

**6. updateSolutionData**

```javascript
const $injector = self.ctx.$scope.$injector;
const solutionsCreatorService = $injector.get(self.ctx.servicesMap.get('solutionsCreatorService'));
const solutionId = 'your-solution-id';
const dataKey = {  // SolutionDataKey object
  // ... set the fields you need
};
const msg = {  // SolutionDataValues object
  // ... set the fields you need
};
solutionsCreatorService.updateSolutionData(solutionId, dataKey, msg).subscribe(savedSolutionData => {
  console.log('Saved Solution Data:', savedSolutionData);
});
```

**7. installSolution**

```javascript
const $injector = self.ctx.$scope.$injector;
const solutionsCreatorService = $injector.get(self.ctx.servicesMap.get('solutionsCreatorService'));
const solutionId = 'your-solution-id';
solutionsCreatorService.installSolution(solutionId).subscribe(installSolution => {
  console.log('Install Solution:', installSolution);
});
```

**8. uninstallSolution**

```javascript
const $injector = self.ctx.$scope.$injector;
const solutionsCreatorService = $injector.get(self.ctx.servicesMap.get('solutionsCreatorService'));
const solutionId = 'your-solution-id';
solutionsCreatorService.uninstallSolution(solutionId).subscribe(uninstallSolution => {
  console.log('Uninstall Solution:', uninstallSolution);
});
```

**9. getSolutions**

```javascript
const $injector = self.ctx.$scope.$injector;
const solutionsCreatorService = $injector.get(self.ctx.servicesMap.get('solutionsCreatorService'));
solutionsCreatorService.getSolutions().subscribe(solutions => {
  console.log('List of Solutions:', solutions);
});
```

**10. deleteSolution**

```javascript
const $injector = self.ctx.$scope.$injector;
const solutionsCreatorService = $injector.get(self.ctx.servicesMap.get('solutionsCreatorService'));
const solutionId = 'your-solution-id';
solutionsCreatorService.deleteSolution(solutionId).subscribe(result => {
  console.log('Delete Solution result:', result);
});
```

### **SYSTEM SETUP SERVICE**

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

### **TENANT PROFILE SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const tenantProfileService = $injector.get(self.ctx.servicesMap.get('tenantProfileService'));
```

**1. getTenantProfiles**

```javascript
const $injector = self.ctx.$scope.$injector;
const tenantProfileService = $injector.get(self.ctx.servicesMap.get('tenantProfileService'));
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
tenantProfileService.getTenantProfiles(pageLink).subscribe(tenantProfiles => {
  console.log('List of Tenant Profiles:', tenantProfiles);
});
```

**2. getTenantProfile**

```javascript
const $injector = self.ctx.$scope.$injector;
const tenantProfileService = $injector.get(self.ctx.servicesMap.get('tenantProfileService'));
const tenantProfileId = 'your-tenant-profile-id';
tenantProfileService.getTenantProfile(tenantProfileId).subscribe(tenantProfile => {
  console.log('Get Tenant Profile:', tenantProfile);
});
```

**3. saveTenantProfile**

```javascript
const $injector = self.ctx.$scope.$injector;
const tenantProfileService = $injector.get(self.ctx.servicesMap.get('tenantProfileService'));
const tenantProfile = {  // TenantProfile object
  // ... set the fields you need
};
tenantProfileService.saveTenantProfile(tenantProfile).subscribe(savedTenantProfile => {
  console.log('Saved Tenant Profile:', savedTenantProfile);
});
```

**4. setDefaultTenantProfile**

```javascript
const $injector = self.ctx.$scope.$injector;
const tenantProfileService = $injector.get(self.ctx.servicesMap.get('tenantProfileService'));
const tenantProfileId = 'your-tenant-profile-id';
tenantProfileService.setDefaultTenantProfile(tenantProfileId).subscribe(setDefaultTenantProfile => {
  console.log('Set Default Tenant Profile:', setDefaultTenantProfile);
});
```

**5. getDefaultTenantProfileInfo**

```javascript
const $injector = self.ctx.$scope.$injector;
const tenantProfileService = $injector.get(self.ctx.servicesMap.get('tenantProfileService'));
tenantProfileService.getDefaultTenantProfileInfo().subscribe(defaultTenantProfileInfo => {
  console.log('Get Default Tenant Profile Info:', defaultTenantProfileInfo);
});
```

**6. getTenantProfileInfo**

```javascript
const $injector = self.ctx.$scope.$injector;
const tenantProfileService = $injector.get(self.ctx.servicesMap.get('tenantProfileService'));
const tenantProfileId = 'your-tenant-profile-id';
tenantProfileService.getTenantProfileInfo(tenantProfileId).subscribe(tenantProfileInfo => {
  console.log('Get Tenant Profile Info:', tenantProfileInfo);
});
```

**7. getTenantProfileInfos**

```javascript
const $injector = self.ctx.$scope.$injector;
const tenantProfileService = $injector.get(self.ctx.servicesMap.get('tenantProfileService'));
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
tenantProfileService.getTenantProfileInfos(pageLink).subscribe(tenantProfileInfos => {
  console.log('List of Tenant Profile Infos:', tenantProfileInfos);
});
```

**8. getTenantProfilesByIds**

```javascript
const $injector = self.ctx.$scope.$injector;
const tenantProfileService = $injector.get(self.ctx.servicesMap.get('tenantProfileService'));
const tenantProfileIds = ['your-tenant-profile-i-1', 'your-tenant-profile-i-2'];
tenantProfileService.getTenantProfilesByIds(tenantProfileIds).subscribe(tenantProfilesBys => {
  console.log('List of Tenant Profiles By Ids:', tenantProfilesBys);
});
```

### **TENANT SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const tenantService = $injector.get(self.ctx.servicesMap.get('tenantService'));
```

**1. getTenants**

```javascript
const $injector = self.ctx.$scope.$injector;
const tenantService = $injector.get(self.ctx.servicesMap.get('tenantService'));
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
tenantService.getTenants(pageLink).subscribe(tenants => {
  console.log('List of Tenants:', tenants);
});
```

**2. getTenantsByIds**

```javascript
const $injector = self.ctx.$scope.$injector;
const tenantService = $injector.get(self.ctx.servicesMap.get('tenantService'));
const tenantIds = ['your-tenant-i-1', 'your-tenant-i-2'];
tenantService.getTenantsByIds(tenantIds).subscribe(tenantsBys => {
  console.log('List of Tenants By Ids:', tenantsBys);
});
```

**3. getTenantInfos**

```javascript
const $injector = self.ctx.$scope.$injector;
const tenantService = $injector.get(self.ctx.servicesMap.get('tenantService'));
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
tenantService.getTenantInfos(pageLink).subscribe(tenantInfos => {
  console.log('List of Tenant Infos:', tenantInfos);
});
```

**4. getTenant**

```javascript
const $injector = self.ctx.$scope.$injector;
const tenantService = $injector.get(self.ctx.servicesMap.get('tenantService'));
const tenantId = 'your-tenant-id';
tenantService.getTenant(tenantId).subscribe(tenant => {
  console.log('Get Tenant:', tenant);
});
```

**5. getTenantInfo**

```javascript
const $injector = self.ctx.$scope.$injector;
const tenantService = $injector.get(self.ctx.servicesMap.get('tenantService'));
const tenantId = 'your-tenant-id';
tenantService.getTenantInfo(tenantId).subscribe(tenantInfo => {
  console.log('Get Tenant Info:', tenantInfo);
});
```

**6. saveTenant**

```javascript
const $injector = self.ctx.$scope.$injector;
const tenantService = $injector.get(self.ctx.servicesMap.get('tenantService'));
const tenant = {  // Tenant object
  // ... set the fields you need
};
tenantService.saveTenant(tenant).subscribe(savedTenant => {
  console.log('Saved Tenant:', savedTenant);
});
```

### **TRENDZ SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const trendzService = $injector.get(self.ctx.servicesMap.get('trendzService'));
```

**1. getTrendzSummary**

```javascript
const $injector = self.ctx.$scope.$injector;
const trendzService = $injector.get(self.ctx.servicesMap.get('trendzService'));
trendzService.getTrendzSummary().subscribe(trendzSummary => {
  console.log('Get Trendz Summary:', trendzSummary);
});
```

**2. performTrendzHealthcheck**

```javascript
const $injector = self.ctx.$scope.$injector;
const trendzService = $injector.get(self.ctx.servicesMap.get('trendzService'));
trendzService.performTrendzHealthcheck().subscribe(performTrendzHealthcheck => {
  console.log('Perform Trendz Healthcheck:', performTrendzHealthcheck);
});
```

**3. getTrendzConfig**

```javascript
const $injector = self.ctx.$scope.$injector;
const trendzService = $injector.get(self.ctx.servicesMap.get('trendzService'));
trendzService.getTrendzConfig().subscribe(trendzConfig => {
  console.log('Get Trendz Config:', trendzConfig);
});
```

**4. saveTrendzConfig**

```javascript
const $injector = self.ctx.$scope.$injector;
const trendzService = $injector.get(self.ctx.servicesMap.get('trendzService'));
const trendzConfig = {  // TrendzConfiguration object
  // ... set the fields you need
};
trendzService.saveTrendzConfig(trendzConfig).subscribe(savedTrendzConfig => {
  console.log('Saved Trendz Config:', savedTrendzConfig);
});
```

**5. getTrendzSyncResult**

```javascript
const $injector = self.ctx.$scope.$injector;
const trendzService = $injector.get(self.ctx.servicesMap.get('trendzService'));
trendzService.getTrendzSyncResult().subscribe(trendzSyncResult => {
  console.log('Get Trendz Sync Result:', trendzSyncResult);
});
```

**6. connectToTrendz**

```javascript
const $injector = self.ctx.$scope.$injector;
const trendzService = $injector.get(self.ctx.servicesMap.get('trendzService'));
trendzService.connectToTrendz().subscribe(connectToTrendz => {
  console.log('Connect To Trendz:', connectToTrendz);
});
```

### **TRENDZ SETTINGS SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const trendzSettingsService = $injector.get(self.ctx.servicesMap.get('trendzSettingsService'));
```

**1. getTrendzSettings**

```javascript
const $injector = self.ctx.$scope.$injector;
const trendzSettingsService = $injector.get(self.ctx.servicesMap.get('trendzSettingsService'));
trendzSettingsService.getTrendzSettings().subscribe(trendzSettings => {
  console.log('Get Trendz Settings:', trendzSettings);
});
```

**2. saveTrendzSettings**

```javascript
const $injector = self.ctx.$scope.$injector;
const trendzSettingsService = $injector.get(self.ctx.servicesMap.get('trendzSettingsService'));
const trendzSettings = {  // TrendzSettings object
  // ... set the fields you need
};
trendzSettingsService.saveTrendzSettings(trendzSettings).subscribe(savedTrendzSettings => {
  console.log('Saved Trendz Settings:', savedTrendzSettings);
});
```

### **TWO FACTOR AUTHENTICATION SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const twoFactorAuthenticationService = $injector.get(self.ctx.servicesMap.get('twoFactorAuthenticationService'));
```

**1. getTwoFaSettings**

```javascript
const $injector = self.ctx.$scope.$injector;
const twoFactorAuthenticationService = $injector.get(self.ctx.servicesMap.get('twoFactorAuthenticationService'));
twoFactorAuthenticationService.getTwoFaSettings().subscribe(twoFaSettings => {
  console.log('Get Two Fa Settings:', twoFaSettings);
});
```

**2. saveTwoFaSettings**

```javascript
const $injector = self.ctx.$scope.$injector;
const twoFactorAuthenticationService = $injector.get(self.ctx.servicesMap.get('twoFactorAuthenticationService'));
const settings = {  // TwoFactorAuthSettings object
  // ... set the fields you need
};
twoFactorAuthenticationService.saveTwoFaSettings(settings).subscribe(savedTwoFaSettings => {
  console.log('Saved Two Fa Settings:', savedTwoFaSettings);
});
```

**3. getAvailableTwoFaProviders**

```javascript
const $injector = self.ctx.$scope.$injector;
const twoFactorAuthenticationService = $injector.get(self.ctx.servicesMap.get('twoFactorAuthenticationService'));
twoFactorAuthenticationService.getAvailableTwoFaProviders().subscribe(availableTwoFaProviders => {
  console.log('List of Available Two Fa Providers:', availableTwoFaProviders);
});
```

**4. generateTwoFaAccountConfig**

```javascript
const $injector = self.ctx.$scope.$injector;
const twoFactorAuthenticationService = $injector.get(self.ctx.servicesMap.get('twoFactorAuthenticationService'));
const providerType = {  // TwoFactorAuthProviderType object
  // ... set the fields you need
};
twoFactorAuthenticationService.generateTwoFaAccountConfig(providerType).subscribe(generateTwoFaAccountConfig => {
  console.log('Generate Two Fa Account Config:', generateTwoFaAccountConfig);
});
```

**5. getAccountTwoFaSettings**

```javascript
const $injector = self.ctx.$scope.$injector;
const twoFactorAuthenticationService = $injector.get(self.ctx.servicesMap.get('twoFactorAuthenticationService'));
twoFactorAuthenticationService.getAccountTwoFaSettings().subscribe(accountTwoFaSettings => {
  console.log('Get Account Two Fa Settings:', accountTwoFaSettings);
});
```

**6. updateTwoFaAccountConfig**

```javascript
const $injector = self.ctx.$scope.$injector;
const twoFactorAuthenticationService = $injector.get(self.ctx.servicesMap.get('twoFactorAuthenticationService'));
const providerType = {  // TwoFactorAuthProviderType object
  // ... set the fields you need
};
const useByDefault = true;
twoFactorAuthenticationService.updateTwoFaAccountConfig(providerType, useByDefault).subscribe(savedTwoFaAccountConfig => {
  console.log('Saved Two Fa Account Config:', savedTwoFaAccountConfig);
});
```

**7. submitTwoFaAccountConfig**

```javascript
const $injector = self.ctx.$scope.$injector;
const twoFactorAuthenticationService = $injector.get(self.ctx.servicesMap.get('twoFactorAuthenticationService'));
const authConfig = {  // TwoFactorAuthAccountConfig object
  // ... set the fields you need
};
twoFactorAuthenticationService.submitTwoFaAccountConfig(authConfig).subscribe(submitTwoFaAccountConfig => {
  console.log('Submit Two Fa Account Config:', submitTwoFaAccountConfig);
});
```

**8. verifyAndSaveTwoFaAccountConfig**

```javascript
const $injector = self.ctx.$scope.$injector;
const twoFactorAuthenticationService = $injector.get(self.ctx.servicesMap.get('twoFactorAuthenticationService'));
const authConfig = {  // TwoFactorAuthAccountConfig object
  // ... set the fields you need
};
const verificationCode = 10;
twoFactorAuthenticationService.verifyAndSaveTwoFaAccountConfig(authConfig, verificationCode).subscribe(verifyAndSaveTwoFaAccountConfig => {
  console.log('Verify And Save Two Fa Account Config:', verifyAndSaveTwoFaAccountConfig);
});
```

**9. deleteTwoFaAccountConfig**

```javascript
const $injector = self.ctx.$scope.$injector;
const twoFactorAuthenticationService = $injector.get(self.ctx.servicesMap.get('twoFactorAuthenticationService'));
const providerType = {  // TwoFactorAuthProviderType object
  // ... set the fields you need
};
twoFactorAuthenticationService.deleteTwoFaAccountConfig(providerType).subscribe(result => {
  console.log('Delete Two Fa Account Config result:', result);
});
```

### **UI SETTINGS SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const uiSettingsService = $injector.get(self.ctx.servicesMap.get('uiSettingsService'));
```

**1. getHelpBaseUrl**

```javascript
const $injector = self.ctx.$scope.$injector;
const uiSettingsService = $injector.get(self.ctx.servicesMap.get('uiSettingsService'));
uiSettingsService.getHelpBaseUrl().subscribe(helpBaseUrl => {
  console.log('Get Help Base Url:', helpBaseUrl);
});
```

### **USAGE INFO SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const usageInfoService = $injector.get(self.ctx.servicesMap.get('usageInfoService'));
```

**1. getUsageInfo**

```javascript
const $injector = self.ctx.$scope.$injector;
const usageInfoService = $injector.get(self.ctx.servicesMap.get('usageInfoService'));
usageInfoService.getUsageInfo().subscribe(usageInfo => {
  console.log('Get Usage Info:', usageInfo);
});
```

### **USER PERMISSIONS SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const userPermissionsService = $injector.get(self.ctx.servicesMap.get('userPermissionsService'));
```

**1. loadPermissionsInfo**

```javascript
const $injector = self.ctx.$scope.$injector;
const userPermissionsService = $injector.get(self.ctx.servicesMap.get('userPermissionsService'));
userPermissionsService.loadPermissionsInfo().subscribe(permissionsInfo => {
  console.log('Load Permissions Info:', permissionsInfo);
});
```

**2. hasEntityPermission**

```javascript
const $injector = self.ctx.$scope.$injector;
const userPermissionsService = $injector.get(self.ctx.servicesMap.get('userPermissionsService'));
const entityId = {  // EntityId object
  // ... set the fields you need
};
const operation = {  // Operation object
  // ... set the fields you need
};
userPermissionsService.hasEntityPermission(entityId, operation).subscribe(hasEntityPermission => {
  console.log('Has Entity Permission:', hasEntityPermission);
});
```

**3. getOperationsByResource**

```javascript
const $injector = self.ctx.$scope.$injector;
const userPermissionsService = $injector.get(self.ctx.servicesMap.get('userPermissionsService'));
const resource = {  // Resource object
  // ... set the fields you need
};
const result = userPermissionsService.getOperationsByResource(resource);
console.log('Result:', result);
```

**4. getAllowedGroupRoleOperations**

```javascript
const $injector = self.ctx.$scope.$injector;
const userPermissionsService = $injector.get(self.ctx.servicesMap.get('userPermissionsService'));
const result = userPermissionsService.getAllowedGroupRoleOperations();
console.log('Result:', result);
```

**5. getAllowedResources**

```javascript
const $injector = self.ctx.$scope.$injector;
const userPermissionsService = $injector.get(self.ctx.servicesMap.get('userPermissionsService'));
const result = userPermissionsService.getAllowedResources();
console.log('Result:', result);
```

**6. hasReadGroupsPermission**

```javascript
const $injector = self.ctx.$scope.$injector;
const userPermissionsService = $injector.get(self.ctx.servicesMap.get('userPermissionsService'));
const entityType = {  // EntityType object
  // ... set the fields you need
};
const result = userPermissionsService.hasReadGroupsPermission(entityType);
console.log('Result:', result);
```

**7. hasGenericReadGroupsPermission**

```javascript
const $injector = self.ctx.$scope.$injector;
const userPermissionsService = $injector.get(self.ctx.servicesMap.get('userPermissionsService'));
const entityType = {  // EntityType object
  // ... set the fields you need
};
const result = userPermissionsService.hasGenericReadGroupsPermission(entityType);
console.log('Result:', result);
```

**8. hasSharedReadGroupsPermission**

```javascript
const $injector = self.ctx.$scope.$injector;
const userPermissionsService = $injector.get(self.ctx.servicesMap.get('userPermissionsService'));
const entityType = {  // EntityType object
  // ... set the fields you need
};
const result = userPermissionsService.hasSharedReadGroupsPermission(entityType);
console.log('Result:', result);
```

**9. hasReadGenericPermission**

```javascript
const $injector = self.ctx.$scope.$injector;
const userPermissionsService = $injector.get(self.ctx.servicesMap.get('userPermissionsService'));
const resource = {  // Resource object
  // ... set the fields you need
};
const result = userPermissionsService.hasReadGenericPermission(resource);
console.log('Result:', result);
```

**10. hasGenericPermission**

```javascript
const $injector = self.ctx.$scope.$injector;
const userPermissionsService = $injector.get(self.ctx.servicesMap.get('userPermissionsService'));
const resource = {  // Resource object
  // ... set the fields you need
};
const operation = {  // Operation object
  // ... set the fields you need
};
const result = userPermissionsService.hasGenericPermission(resource, operation);
console.log('Result:', result);
```

**11. isAiEnabled**

```javascript
const $injector = self.ctx.$scope.$injector;
const userPermissionsService = $injector.get(self.ctx.servicesMap.get('userPermissionsService'));
const result = userPermissionsService.isAiEnabled();
console.log('Result:', result);
```

**12. isResourceAllowed**

```javascript
const $injector = self.ctx.$scope.$injector;
const userPermissionsService = $injector.get(self.ctx.servicesMap.get('userPermissionsService'));
const resource = {  // Resource object
  // ... set the fields you need
};
const result = userPermissionsService.isResourceAllowed(resource);
console.log('Result:', result);
```

**13. hasGenericPermissionByEntityGroupType**

```javascript
const $injector = self.ctx.$scope.$injector;
const userPermissionsService = $injector.get(self.ctx.servicesMap.get('userPermissionsService'));
const operation = {  // Operation object
  // ... set the fields you need
};
const groupType = {  // EntityType object
  // ... set the fields you need
};
const result = userPermissionsService.hasGenericPermissionByEntityGroupType(operation, groupType);
console.log('Result:', result);
```

**14. hasGenericEntityGroupTypePermission**

```javascript
const $injector = self.ctx.$scope.$injector;
const userPermissionsService = $injector.get(self.ctx.servicesMap.get('userPermissionsService'));
const operation = {  // Operation object
  // ... set the fields you need
};
const groupType = {  // EntityType object
  // ... set the fields you need
};
const result = userPermissionsService.hasGenericEntityGroupTypePermission(operation, groupType);
console.log('Result:', result);
```

**15. hasGenericEntityGroupPermission**

```javascript
const $injector = self.ctx.$scope.$injector;
const userPermissionsService = $injector.get(self.ctx.servicesMap.get('userPermissionsService'));
const operation = {  // Operation object
  // ... set the fields you need
};
const entityGroup = {  // EntityGroup object
  // ... set the fields you need
};
const result = userPermissionsService.hasGenericEntityGroupPermission(operation, entityGroup);
console.log('Result:', result);
```

**16. hasEntityGroupPermission**

```javascript
const $injector = self.ctx.$scope.$injector;
const userPermissionsService = $injector.get(self.ctx.servicesMap.get('userPermissionsService'));
const operation = {  // Operation object
  // ... set the fields you need
};
const entityGroup = {  // EntityGroupInfo object
  // ... set the fields you need
};
const result = userPermissionsService.hasEntityGroupPermission(operation, entityGroup);
console.log('Result:', result);
```

**17. hasGroupEntityPermission**

```javascript
const $injector = self.ctx.$scope.$injector;
const userPermissionsService = $injector.get(self.ctx.servicesMap.get('userPermissionsService'));
const operation = {  // Operation object
  // ... set the fields you need
};
const entityGroup = {  // EntityGroupInfo object
  // ... set the fields you need
};
const result = userPermissionsService.hasGroupEntityPermission(operation, entityGroup);
console.log('Result:', result);
```

**18. isOwnedGroup**

```javascript
const $injector = self.ctx.$scope.$injector;
const userPermissionsService = $injector.get(self.ctx.servicesMap.get('userPermissionsService'));
const entityGroup = {  // EntityGroupInfo object
  // ... set the fields you need
};
const result = userPermissionsService.isOwnedGroup(entityGroup);
console.log('Result:', result);
```

**19. getUserOwnerId**

```javascript
const $injector = self.ctx.$scope.$injector;
const userPermissionsService = $injector.get(self.ctx.servicesMap.get('userPermissionsService'));
const result = userPermissionsService.getUserOwnerId();
console.log('Result:', result);
```

**20. isDirectOwner**

```javascript
const $injector = self.ctx.$scope.$injector;
const userPermissionsService = $injector.get(self.ctx.servicesMap.get('userPermissionsService'));
const ownerId = {  // EntityId object
  // ... set the fields you need
};
const result = userPermissionsService.isDirectOwner(ownerId);
console.log('Result:', result);
```

**21. hasEntityTypeOperationPermission**

```javascript
const $injector = self.ctx.$scope.$injector;
const userPermissionsService = $injector.get(self.ctx.servicesMap.get('userPermissionsService'));
const entityType = {  // EntityType object
  // ... set the fields you need
};
const operation = {  // Operation object
  // ... set the fields you need
};
const entityGroup = {  // EntityGroupInfo object
  // ... set the fields you need
};
const result = userPermissionsService.hasEntityTypeOperationPermission(entityType, operation, entityGroup);
console.log('Result:', result);
```

**22. hasResourcesGenericPermission**

```javascript
const $injector = self.ctx.$scope.$injector;
const userPermissionsService = $injector.get(self.ctx.servicesMap.get('userPermissionsService'));
const resource = [];  // e.g. array of resource values
const operation = [];  // e.g. array of operation values
const result = userPermissionsService.hasResourcesGenericPermission(resource, operation);
console.log('Result:', result);
```

**23. hasGenericResourcesPermission**

```javascript
const $injector = self.ctx.$scope.$injector;
const userPermissionsService = $injector.get(self.ctx.servicesMap.get('userPermissionsService'));
const resources = [];  // e.g. array of resources values
const operation = [];  // e.g. array of operation values
const result = userPermissionsService.hasGenericResourcesPermission(resources, operation);
console.log('Result:', result);
```

**24. hasGenericOperationsPermission**

```javascript
const $injector = self.ctx.$scope.$injector;
const userPermissionsService = $injector.get(self.ctx.servicesMap.get('userPermissionsService'));
const resource = [];  // e.g. array of resource values
const operations = [];  // e.g. array of operations values
const result = userPermissionsService.hasGenericOperationsPermission(resource, operations);
console.log('Result:', result);
```

**25. hasGenericAllPermission**

```javascript
const $injector = self.ctx.$scope.$injector;
const userPermissionsService = $injector.get(self.ctx.servicesMap.get('userPermissionsService'));
const resource = {  // Resource object
  // ... set the fields you need
};
const operation = {  // Operation object
  // ... set the fields you need
};
const result = userPermissionsService.hasGenericAllPermission(resource, operation);
console.log('Result:', result);
```

**26. hasGenericResourcePermission**

```javascript
const $injector = self.ctx.$scope.$injector;
const userPermissionsService = $injector.get(self.ctx.servicesMap.get('userPermissionsService'));
const resource = {  // Resource object
  // ... set the fields you need
};
const operation = {  // Operation object
  // ... set the fields you need
};
const result = userPermissionsService.hasGenericResourcePermission(resource, operation);
console.log('Result:', result);
```

**27. checkOperation**

```javascript
const $injector = self.ctx.$scope.$injector;
const userPermissionsService = $injector.get(self.ctx.servicesMap.get('userPermissionsService'));
const operations = [];  // e.g. array of operations values
const operation = {  // Operation object
  // ... set the fields you need
};
const result = userPermissionsService.checkOperation(operations, operation);
console.log('Result:', result);
```

**28. checkEntityGroupPermission**

```javascript
const $injector = self.ctx.$scope.$injector;
const userPermissionsService = $injector.get(self.ctx.servicesMap.get('userPermissionsService'));
const operation = {  // Operation object
  // ... set the fields you need
};
const entityGroup = {  // EntityGroupInfo object
  // ... set the fields you need
};
const isGroup = true;
const result = userPermissionsService.checkEntityGroupPermission(operation, entityGroup, isGroup);
console.log('Result:', result);
```

**29. hasGroupPermissions**

```javascript
const $injector = self.ctx.$scope.$injector;
const userPermissionsService = $injector.get(self.ctx.servicesMap.get('userPermissionsService'));
const entityGroup = {  // EntityGroupInfo object
  // ... set the fields you need
};
const operation = {  // Operation object
  // ... set the fields you need
};
const isGroup = true;
const result = userPermissionsService.hasGroupPermissions(entityGroup, operation, isGroup);
console.log('Result:', result);
```

**30. isCurrentUserOwner**

```javascript
const $injector = self.ctx.$scope.$injector;
const userPermissionsService = $injector.get(self.ctx.servicesMap.get('userPermissionsService'));
const entityGroup = {  // EntityGroupInfo object
  // ... set the fields you need
};
const result = userPermissionsService.isCurrentUserOwner(entityGroup);
console.log('Result:', result);
```

**31. containsId**

```javascript
const $injector = self.ctx.$scope.$injector;
const userPermissionsService = $injector.get(self.ctx.servicesMap.get('userPermissionsService'));
const idsArray = [];  // e.g. array of ids-array values
const id = {  // EntityId object
  // ... set the fields you need
};
const result = userPermissionsService.containsId(idsArray, id);
console.log('Result:', result);
```

**32. idsEqual**

```javascript
const $injector = self.ctx.$scope.$injector;
const userPermissionsService = $injector.get(self.ctx.servicesMap.get('userPermissionsService'));
const id1 = {  // EntityId object
  // ... set the fields you need
};
const id2 = {  // EntityId object
  // ... set the fields you need
};
const result = userPermissionsService.idsEqual(id1, id2);
console.log('Result:', result);
```

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
const userService = self.ctx.userService;
const tenantId = 'your-tenant-id';
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
userService.getTenantAdmins(tenantId, pageLink).subscribe(tenantAdmins => {
  console.log('List of Tenant Admins:', tenantAdmins);
});
```

**2. getCustomerUsers**

```javascript
const userService = self.ctx.userService;
const customerId = 'your-customer-id';
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
userService.getCustomerUsers(customerId, pageLink).subscribe(customerUsers => {
  console.log('List of Customer Users:', customerUsers);
});
```

**3. getAllCustomerUsers**

```javascript
const userService = self.ctx.userService;
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
userService.getAllCustomerUsers(pageLink).subscribe(allCustomerUsers => {
  console.log('List of All Customer Users:', allCustomerUsers);
});
```

**4. getUsersForAssign**

```javascript
const userService = self.ctx.userService;
const alarmId = 'your-alarm-id';
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
userService.getUsersForAssign(alarmId, pageLink).subscribe(usersForAssigns => {
  console.log('List of Users For Assigns:', usersForAssigns);
});
```

**5. getUser**

```javascript
const userService = self.ctx.userService;
const userId = 'your-user-id';
userService.getUser(userId).subscribe(user => {
  console.log('Get User:', user);
});
```

**6. getUserInfo**

```javascript
const userService = self.ctx.userService;
const userId = 'your-user-id';
userService.getUserInfo(userId).subscribe(userInfo => {
  console.log('Get User Info:', userInfo);
});
```

**7. getUsers** (!!CE VERSION!!)

```javascript
const userService = self.ctx.userService;
const userIds = ['your-user-i-1', 'your-user-i-2'];
userService.getUsers(userIds).subscribe(users => {
  console.log('List of Users:', users);
});
```

**8. getUserUsers**

```javascript
const userService = self.ctx.userService;
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
userService.getUserUsers(pageLink).subscribe(userUsers => {
  console.log('List of User Users:', userUsers);
});
```

**9. getAllUserInfos**

```javascript
const userService = self.ctx.userService;
const includeCustomers = true;
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
userService.getAllUserInfos(includeCustomers, pageLink).subscribe(allUserInfos => {
  console.log('List of All User Infos:', allUserInfos);
});
```

**10. getCustomerUserInfos**

```javascript
const userService = self.ctx.userService;
const includeCustomers = true;
const customerId = 'your-customer-id';
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
userService.getCustomerUserInfos(includeCustomers, customerId, pageLink).subscribe(customerUserInfos => {
  console.log('List of Customer User Infos:', customerUserInfos);
});
```

**11. saveUser**

```javascript
const userService = self.ctx.userService;
const user = {  // User object
  // ... set the fields you need
};
const sendActivationMail = 'value';
const entityGroupIds = ['your-entity-group-i-1', 'your-entity-group-i-2'];
userService.saveUser(user, sendActivationMail, entityGroupIds).subscribe(savedUser => {
  console.log('Saved User:', savedUser);
});
```

**12. getActivationLink**

```javascript
const userService = self.ctx.userService;
const userId = 'your-user-id';
userService.getActivationLink(userId).subscribe(activationLink => {
  console.log('Get Activation Link:', activationLink);
});
```

**13. getActivationLinkInfo**

```javascript
const userService = self.ctx.userService;
const userId = 'your-user-id';
userService.getActivationLinkInfo(userId).subscribe(activationLinkInfo => {
  console.log('Get Activation Link Info:', activationLinkInfo);
});
```

**14. setUserCredentialsEnabled**

```javascript
const userService = self.ctx.userService;
const userId = 'your-user-id';
const userCredentialsEnabled = true;
userService.setUserCredentialsEnabled(userId, userCredentialsEnabled).subscribe(setUserCredentialsEnabled => {
  console.log('Set User Credentials Enabled:', setUserCredentialsEnabled);
});
```

**15. findUsersByQuery**

```javascript
const userService = self.ctx.userService;
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
userService.findUsersByQuery(pageLink).subscribe(usersByQuerys => {
  console.log('List of Users By Querys:', usersByQuerys);
});
```

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
const userSettingsService = self.ctx.userSettingsService;
userSettingsService.loadUserSettings().subscribe(userSettings => {
  console.log('Load User Settings:', userSettings);
});
```

**2. saveUserSettings**

```javascript
const userSettingsService = self.ctx.userSettingsService;
const userSettings = {  // UserSettings object
  // ... set the fields you need
};
userSettingsService.saveUserSettings(userSettings).subscribe(savedUserSettings => {
  console.log('Saved User Settings:', savedUserSettings);
});
```

**3. putUserSettings**

```javascript
const userSettingsService = self.ctx.userSettingsService;
const userSettingsData = {  // Partial<UserSettings> object
  // ... set the fields you need
};
userSettingsService.putUserSettings(userSettingsData).subscribe(putUserSettings => {
  console.log('Put User Settings:', putUserSettings);
});
```

**4. getDocumentationLinks**

```javascript
const userSettingsService = self.ctx.userSettingsService;
userSettingsService.getDocumentationLinks().subscribe(documentationLinks => {
  console.log('Get Documentation Links:', documentationLinks);
});
```

**5. updateDocumentationLinks**

```javascript
const userSettingsService = self.ctx.userSettingsService;
const documentationLinks = {  // DocumentationLinks object
  // ... set the fields you need
};
userSettingsService.updateDocumentationLinks(documentationLinks).subscribe(savedDocumentationLinks => {
  console.log('Saved Documentation Links:', savedDocumentationLinks);
});
```

**6. getQuickLinks**

```javascript
const userSettingsService = self.ctx.userSettingsService;
userSettingsService.getQuickLinks().subscribe(quickLinks => {
  console.log('Get Quick Links:', quickLinks);
});
```

**7. updateQuickLinks**

```javascript
const userSettingsService = self.ctx.userSettingsService;
const quickLinks = {  // QuickLinks object
  // ... set the fields you need
};
userSettingsService.updateQuickLinks(quickLinks).subscribe(savedQuickLinks => {
  console.log('Saved Quick Links:', savedQuickLinks);
});
```

**8. getGettingStarted**

```javascript
const userSettingsService = self.ctx.userSettingsService;
userSettingsService.getGettingStarted().subscribe(gettingStarted => {
  console.log('Get Getting Started:', gettingStarted);
});
```

**9. updateGettingStarted**

```javascript
const userSettingsService = self.ctx.userSettingsService;
const gettingStarted = {  // GettingStarted object
  // ... set the fields you need
};
userSettingsService.updateGettingStarted(gettingStarted).subscribe(savedGettingStarted => {
  console.log('Saved Getting Started:', savedGettingStarted);
});
```

**10. getUserDashboardsInfo**

```javascript
const userSettingsService = self.ctx.userSettingsService;
userSettingsService.getUserDashboardsInfo().subscribe(userDashboardsInfo => {
  console.log('Get User Dashboards Info:', userDashboardsInfo);
});
```

**11. reportUserDashboardAction**

```javascript
const userSettingsService = self.ctx.userSettingsService;
const dashboardId = 'your-dashboard-id';
const action = {  // UserDashboardAction object
  // ... set the fields you need
};
userSettingsService.reportUserDashboardAction(dashboardId, action).subscribe(reportUserDashboardAction => {
  console.log('Report User Dashboard Action:', reportUserDashboardAction);
});
```

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

### **WIDGET SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const widgetService = $injector.get(self.ctx.servicesMap.get('widgetService'));
```

**1. getWidgetScopeVariables**

```javascript
const $injector = self.ctx.$scope.$injector;
const widgetService = $injector.get(self.ctx.servicesMap.get('widgetService'));
const result = widgetService.getWidgetScopeVariables();
console.log('Result:', result);
```

**2. getAllWidgetsBundles**

```javascript
const $injector = self.ctx.$scope.$injector;
const widgetService = $injector.get(self.ctx.servicesMap.get('widgetService'));
widgetService.getAllWidgetsBundles().subscribe(allWidgetsBundles => {
  console.log('List of All Widgets Bundles:', allWidgetsBundles);
});
```

**3. getSystemWidgetsBundles**

```javascript
const $injector = self.ctx.$scope.$injector;
const widgetService = $injector.get(self.ctx.servicesMap.get('widgetService'));
widgetService.getSystemWidgetsBundles().subscribe(systemWidgetsBundles => {
  console.log('List of System Widgets Bundles:', systemWidgetsBundles);
});
```

**4. getTenantWidgetsBundles**

```javascript
const $injector = self.ctx.$scope.$injector;
const widgetService = $injector.get(self.ctx.servicesMap.get('widgetService'));
widgetService.getTenantWidgetsBundles().subscribe(tenantWidgetsBundles => {
  console.log('List of Tenant Widgets Bundles:', tenantWidgetsBundles);
});
```

**5. getWidgetBundles**

```javascript
const $injector = self.ctx.$scope.$injector;
const widgetService = $injector.get(self.ctx.servicesMap.get('widgetService'));
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
widgetService.getWidgetBundles(pageLink).subscribe(widgetBundles => {
  console.log('List of Widget Bundles:', widgetBundles);
});
```

**6. getWidgetsBundle**

```javascript
const $injector = self.ctx.$scope.$injector;
const widgetService = $injector.get(self.ctx.servicesMap.get('widgetService'));
const widgetsBundleId = 'your-widgets-bundle-id';
widgetService.getWidgetsBundle(widgetsBundleId).subscribe(widgetsBundle => {
  console.log('Get Widgets Bundle:', widgetsBundle);
});
```

**7. exportWidgetsBundle**

```javascript
const $injector = self.ctx.$scope.$injector;
const widgetService = $injector.get(self.ctx.servicesMap.get('widgetService'));
const widgetsBundleId = 'your-widgets-bundle-id';
widgetService.exportWidgetsBundle(widgetsBundleId).subscribe(exportWidgetsBundle => {
  console.log('Export Widgets Bundle:', exportWidgetsBundle);
});
```

**8. getWidgetsBundlesByIds**

```javascript
const $injector = self.ctx.$scope.$injector;
const widgetService = $injector.get(self.ctx.servicesMap.get('widgetService'));
const widgetsBundleIds = ['your-widgets-bundle-i-1', 'your-widgets-bundle-i-2'];
widgetService.getWidgetsBundlesByIds(widgetsBundleIds).subscribe(widgetsBundlesBys => {
  console.log('List of Widgets Bundles By Ids:', widgetsBundlesBys);
});
```

**9. saveWidgetsBundle**

```javascript
const $injector = self.ctx.$scope.$injector;
const widgetService = $injector.get(self.ctx.servicesMap.get('widgetService'));
const widgetsBundle = {  // WidgetsBundle object
  // ... set the fields you need
};
widgetService.saveWidgetsBundle(widgetsBundle).subscribe(savedWidgetsBundle => {
  console.log('Saved Widgets Bundle:', savedWidgetsBundle);
});
```

**10. updateWidgetsBundleWidgetTypes**

```javascript
const $injector = self.ctx.$scope.$injector;
const widgetService = $injector.get(self.ctx.servicesMap.get('widgetService'));
const widgetsBundleId = 'your-widgets-bundle-id';
const widgetTypeIds = ['your-widget-type-i-1', 'your-widget-type-i-2'];
widgetService.updateWidgetsBundleWidgetTypes(widgetsBundleId, widgetTypeIds).subscribe(savedWidgetsBundleWidgetTypes => {
  console.log('Saved Widgets Bundle Widget Types:', savedWidgetsBundleWidgetTypes);
});
```

**11. updateWidgetsBundleWidgetFqns**

```javascript
const $injector = self.ctx.$scope.$injector;
const widgetService = $injector.get(self.ctx.servicesMap.get('widgetService'));
const widgetsBundleId = 'your-widgets-bundle-id';
const widgetTypeFqns = [];  // e.g. array of widget-type-fqns values
widgetService.updateWidgetsBundleWidgetFqns(widgetsBundleId, widgetTypeFqns).subscribe(savedWidgetsBundleWidgetFqns => {
  console.log('Saved Widgets Bundle Widget Fqns:', savedWidgetsBundleWidgetFqns);
});
```

**12. getBundleWidgetTypes**

```javascript
const $injector = self.ctx.$scope.$injector;
const widgetService = $injector.get(self.ctx.servicesMap.get('widgetService'));
const widgetsBundleId = 'your-widgets-bundle-id';
widgetService.getBundleWidgetTypes(widgetsBundleId).subscribe(bundleWidgetTypes => {
  console.log('List of Bundle Widget Types:', bundleWidgetTypes);
});
```

**13. exportBundleWidgetTypesDetails**

```javascript
const $injector = self.ctx.$scope.$injector;
const widgetService = $injector.get(self.ctx.servicesMap.get('widgetService'));
const widgetsBundleId = 'your-widgets-bundle-id';
widgetService.exportBundleWidgetTypesDetails(widgetsBundleId).subscribe(exportBundleWidgetTypesDetails => {
  console.log('List of Export Bundle Widget Types Details:', exportBundleWidgetTypesDetails);
});
```

**14. getBundleWidgetTypeFqns**

```javascript
const $injector = self.ctx.$scope.$injector;
const widgetService = $injector.get(self.ctx.servicesMap.get('widgetService'));
const widgetsBundleId = 'your-widgets-bundle-id';
widgetService.getBundleWidgetTypeFqns(widgetsBundleId).subscribe(bundleWidgetTypeFqns => {
  console.log('List of Bundle Widget Type Fqns:', bundleWidgetTypeFqns);
});
```

**15. getBundleWidgetTypeInfosList**

```javascript
const $injector = self.ctx.$scope.$injector;
const widgetService = $injector.get(self.ctx.servicesMap.get('widgetService'));
const widgetsBundleId = 'your-widgets-bundle-id';
widgetService.getBundleWidgetTypeInfosList(widgetsBundleId).subscribe(bundleWidgetTypeInfosLists => {
  console.log('List of Bundle Widget Type Infos Lists:', bundleWidgetTypeInfosLists);
});
```

**16. getBundleWidgetTypeInfos**

```javascript
const $injector = self.ctx.$scope.$injector;
const widgetService = $injector.get(self.ctx.servicesMap.get('widgetService'));
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const widgetsBundleId = 'your-widgets-bundle-id';
const widgetTypes = 'value';
widgetService.getBundleWidgetTypeInfos(pageLink, widgetsBundleId, widgetTypes).subscribe(bundleWidgetTypeInfos => {
  console.log('List of Bundle Widget Type Infos:', bundleWidgetTypeInfos);
});
```

**17. getWidgetType**

```javascript
const $injector = self.ctx.$scope.$injector;
const widgetService = $injector.get(self.ctx.servicesMap.get('widgetService'));
const fullFqn = 'your-full-fqn';
widgetService.getWidgetType(fullFqn).subscribe(widgetType => {
  console.log('Get Widget Type:', widgetType);
});
```

**18. saveWidgetTypeDetails**

```javascript
const $injector = self.ctx.$scope.$injector;
const widgetService = $injector.get(self.ctx.servicesMap.get('widgetService'));
const widgetInfo = {  // WidgetInfo object
  // ... set the fields you need
};
const id = {  // WidgetTypeId object
  // ... set the fields you need
};
const createdTime = 10;
const version = 10;
widgetService.saveWidgetTypeDetails(widgetInfo, id, createdTime, version).subscribe(savedWidgetTypeDetails => {
  console.log('Saved Widget Type Details:', savedWidgetTypeDetails);
});
```

**19. saveImportedWidgetTypeDetails**

```javascript
const $injector = self.ctx.$scope.$injector;
const widgetService = $injector.get(self.ctx.servicesMap.get('widgetService'));
const widgetTypeDetails = {  // WidgetTypeDetails object
  // ... set the fields you need
};
widgetService.saveImportedWidgetTypeDetails(widgetTypeDetails).subscribe(savedImportedWidgetTypeDetails => {
  console.log('Saved Imported Widget Type Details:', savedImportedWidgetTypeDetails);
});
```

**20. getWidgetTypeById**

```javascript
const $injector = self.ctx.$scope.$injector;
const widgetService = $injector.get(self.ctx.servicesMap.get('widgetService'));
const widgetTypeId = 'your-widget-type-id';
widgetService.getWidgetTypeById(widgetTypeId).subscribe(widgetTypeBy => {
  console.log('Get Widget Type By Id:', widgetTypeBy);
});
```

**21. exportWidgetType**

```javascript
const $injector = self.ctx.$scope.$injector;
const widgetService = $injector.get(self.ctx.servicesMap.get('widgetService'));
const widgetTypeId = 'your-widget-type-id';
widgetService.exportWidgetType(widgetTypeId).subscribe(exportWidgetType => {
  console.log('Export Widget Type:', exportWidgetType);
});
```

**22. getWidgetTypeInfoById**

```javascript
const $injector = self.ctx.$scope.$injector;
const widgetService = $injector.get(self.ctx.servicesMap.get('widgetService'));
const widgetTypeId = 'your-widget-type-id';
widgetService.getWidgetTypeInfoById(widgetTypeId).subscribe(widgetTypeInfoBy => {
  console.log('Get Widget Type Info By Id:', widgetTypeInfoBy);
});
```

**23. saveWidgetType**

```javascript
const $injector = self.ctx.$scope.$injector;
const widgetService = $injector.get(self.ctx.servicesMap.get('widgetService'));
const widgetTypeDetails = {  // WidgetTypeDetails object
  // ... set the fields you need
};
widgetService.saveWidgetType(widgetTypeDetails).subscribe(savedWidgetType => {
  console.log('Saved Widget Type:', savedWidgetType);
});
```

**24. getWidgetTypes**

```javascript
const $injector = self.ctx.$scope.$injector;
const widgetService = $injector.get(self.ctx.servicesMap.get('widgetService'));
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const widgetTypes = 'value';
widgetService.getWidgetTypes(pageLink, widgetTypes).subscribe(widgetTypes => {
  console.log('List of Widget Types:', widgetTypes);
});
```

**25. getWidgetTemplate**

```javascript
const $injector = self.ctx.$scope.$injector;
const widgetService = $injector.get(self.ctx.servicesMap.get('widgetService'));
const widgetTypeParam = {  // widgetType object
  // ... set the fields you need
};
widgetService.getWidgetTemplate(widgetTypeParam).subscribe(widgetTemplate => {
  console.log('Get Widget Template:', widgetTemplate);
});
```

**26. getWidgetInfoFromCache**

```javascript
const $injector = self.ctx.$scope.$injector;
const widgetService = $injector.get(self.ctx.servicesMap.get('widgetService'));
const fullFqn = 'your-full-fqn';
const result = widgetService.getWidgetInfoFromCache(fullFqn);
console.log('Result:', result);
```

**27. getBasicWidgetSettingsComponentBySelector**

```javascript
const $injector = self.ctx.$scope.$injector;
const widgetService = $injector.get(self.ctx.servicesMap.get('widgetService'));
const selector = 'your-selector';
const result = widgetService.getBasicWidgetSettingsComponentBySelector(selector);
console.log('Result:', result);
```

**28. getWidgetSettingsComponentTypeBySelector**

```javascript
const $injector = self.ctx.$scope.$injector;
const widgetService = $injector.get(self.ctx.servicesMap.get('widgetService'));
const selector = 'your-selector';
const result = widgetService.getWidgetSettingsComponentTypeBySelector(selector);
console.log('Result:', result);
```

**29. widgetTypeUpdated**

```javascript
const $injector = self.ctx.$scope.$injector;
const widgetService = $injector.get(self.ctx.servicesMap.get('widgetService'));
const updatedWidgetType = {  // BaseWidgetType object
  // ... set the fields you need
};
const result = widgetService.widgetTypeUpdated(updatedWidgetType);
console.log('Result:', result);
```

**30. loadWidgetsBundleCache**

```javascript
const $injector = self.ctx.$scope.$injector;
const widgetService = $injector.get(self.ctx.servicesMap.get('widgetService'));
widgetService.loadWidgetsBundleCache().subscribe(widgetsBundleCache => {
  console.log('Load Widgets Bundle Cache:', widgetsBundleCache);
});
```
