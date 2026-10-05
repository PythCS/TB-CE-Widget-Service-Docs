# AI CHAT SERVICE

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
