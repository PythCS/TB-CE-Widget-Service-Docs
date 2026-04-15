# Image

```javascript
// Service name: image
// File: image.service.ts
```

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const image = $injector.get(self.ctx.servicesMap.get('image'));
```

### **1. uploadImage**

```javascript
image.uploadImage(file, title, imageSubType).subscribe(image => {
  console.log('Image:', image);
});
```

### **2. updateImage**

```javascript
image.updateImage(type, key, file).subscribe(image => {
  console.log('Image:', image);
});
```

### **3. updateImageInfo**

```javascript
image.updateImageInfo(imageInfo).subscribe(image => {
  console.log('Image:', image);
});
```

### **4. updateImagePublicStatus**

```javascript
image.updateImagePublicStatus(imageInfo, isPublic).subscribe(image => {
  console.log('Image:', image);
});
```

### **5. getImages**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
image.getImages(pageLink).subscribe(images => {
  console.log('Images:', images);
});
```

### **6. getImageInfo**

```javascript
image.getImageInfo(type, key).subscribe(image => {
  console.log('Image:', image);
});
```

### **7. getImageDataUrl**

```javascript
image.getImageDataUrl(imageUrl).subscribe(image => {
  console.log('Image:', image);
});
```

### **8. loadImageDataUrl**

```javascript
image.loadImageDataUrl(imageLink).subscribe(image => {
  console.log('Image:', image);
});
```

### **9. getImageString**

```javascript
image.getImageString(imageUrl).subscribe(image => {
  console.log('Image:', image);
});
```

### **10. resolveImageUrl**

```javascript
image.resolveImageUrl(imageUrl).subscribe(image => {
  console.log('Image:', image);
});
```

### **11. downloadImage**

```javascript
image.downloadImage(type, key).subscribe(image => {
  console.log('Image:', image);
});
```

### **12. exportImage**

```javascript
image.exportImage(type, key).subscribe(image => {
  console.log('Image:', image);
});
```

### **13. importImage**

```javascript
image.importImage(imageData).subscribe(image => {
  console.log('Image:', image);
});
```
