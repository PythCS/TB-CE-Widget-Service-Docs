# ImageService

### **IMAGESERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const imageService = $injector.get(self.ctx.servicesMap.get('imageService'));
```

**1. uploadImage**

```javascript
imageService.uploadImage({ /* your file */ }, 'your-title', 'your-imagesubtype', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**2. updateImage**

```javascript
imageService.updateImage('your-type', 'your-key', { /* your file */ }, { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**3. updateImageInfo**

```javascript
imageService.updateImageInfo({ /* your imageInfo */ }, { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**4. updateImagePublicStatus**

```javascript
imageService.updateImagePublicStatus({ /* your imageInfo */ }, true, { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**5. getImages**

```javascript
imageService.getImages(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-imagesubtype', { /* your config */ }).subscribe(image => {
  console.log('Images:', image);
});
```

**6. getImageInfo**

```javascript
imageService.getImageInfo('your-type', 'your-key', { /* your config */ }).subscribe(imageinfo => {
  console.log('Image Info:', imageinfo);
});
```

**7. getImageDataUrl**

```javascript
imageService.getImageDataUrl('your-imageUrl').subscribe(imagedataurl => {
  console.log('Image Data Url:', imagedataurl);
});
```

**8. loadImageDataUrl**

```javascript
imageService.loadImageDataUrl('your-imageLink').subscribe(result => {
  console.log('Result:', result);
});
```

**9. getImageString**

```javascript
imageService.getImageString('your-imageUrl').subscribe(imagestring => {
  console.log('Image String:', imagestring);
});
```

**10. resolveImageUrl**

```javascript
imageService.resolveImageUrl('your-imageUrl').subscribe(result => {
  console.log('Result:', result);
});
```

**11. downloadImage**

```javascript
imageService.downloadImage('your-type', 'your-key').subscribe(result => {
  console.log('Result:', result);
});
```

**12. exportImage**

```javascript
imageService.exportImage('your-type', 'your-key', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**13. importImage**

```javascript
imageService.importImage({ /* your imageData */ }, { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```
