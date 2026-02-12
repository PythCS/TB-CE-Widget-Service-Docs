# User Service

Complete reference for the UserService in ThingsBoard widget development.

## Service Injection

```javascript
const $injector = self.ctx.$scope.$injector;
const userService = $injector.get(self.ctx.servicesMap.get('userService'));

// Alternative: Direct context access
const userService = self.ctx.userService;
```

## Methods

### getUsers (!!CE VERSION!!)

Get paginated list of users. Behavior differs between Community and Professional editions.

```javascript
const pageLink = self.ctx.pageLink(10, 0, '', 'email', 'ASC');
userService.getUsers(pageLink).subscribe(users => {
  console.log('Users:', users);
});
```

### getUser

Get a user by ID.

```javascript
const userId = 'your-user-id';
userService.getUser(userId).subscribe(user => {
  console.log('User:', user);
});
```

### saveUser

Create or update a user.

```javascript
const user = {
  email: 'user@example.com',
  firstName: 'John',
  lastName: 'Doe',
  authority: 'CUSTOMER_USER'
};
const sendActivationMail = true;
userService.saveUser(user, sendActivationMail).subscribe(savedUser => {
  console.log('Saved User:', savedUser);
});
```

### getCustomerUsers

Get users belonging to a specific customer.

```javascript
const customerId = 'your-customer-id';
const pageLink = self.ctx.pageLink(10, 0, '', 'email', 'ASC');
userService.getCustomerUsers(customerId, pageLink).subscribe(users => {
  console.log('Customer Users:', users);
});
```

### getActivationLink

Get the activation link for a user.

```javascript
const userId = 'your-user-id';
userService.getActivationLink(userId).subscribe(activationLink => {
  console.log('Activation Link:', activationLink);
});
```

## Common Use Cases

### Creating User Management Interface

```javascript
// Load all users for management table
const pageLink = self.ctx.pageLink(50, 0, '', 'email', 'ASC');
userService.getUsers(pageLink).subscribe(userPage => {
  const users = userPage.data;
  console.log(`Found ${users.length} users`);
  
  users.forEach(user => {
    console.log(`User: ${user.email} (${user.firstName} ${user.lastName})`);
  });
});
```

### Finding Users by Email

```javascript
// Search for users by email pattern
const searchText = '@company.com';
const pageLink = self.ctx.pageLink(20, 0, searchText, 'email', 'ASC');
userService.findUsersByQuery(pageLink).subscribe(users => {
  console.log('Company users found:', users);
});
```

### Managing User Status

```javascript
const userId = 'your-user-id';
const isEnabled = false; // Disable user

userService.setUserCredentialsEnabled(userId, isEnabled).subscribe(() => {
  console.log('User credentials status updated');
});
```