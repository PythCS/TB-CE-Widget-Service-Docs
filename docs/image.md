### **IMAGE SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const imageservice = $injector.get(self.ctx.servicesMap.get('imageservice'));

```

**1. uploadImage**

```javascript
imageservice.uploadImage(file, 'your-title', imageSubType).subscribe(upimage => {
  console.log('Upimage:', upimage);
});
```

**2. updateImage**

```javascript
imageservice.updateImage(type, 'your-key', file).subscribe(updateimage => {
  console.log('Updateimage:', updateimage);
});
```

**3. updateImageInfo**

```javascript
imageservice.updateImageInfo(imageInfo).subscribe(updateimageinfo => {
  console.log('Updateimageinfo:', updateimageinfo);
});
```

**4. updateImagePublicStatus**

```javascript
imageservice.updateImagePublicStatus(imageInfo, true).subscribe(updateimagepublicstatus => {
  console.log('Updateimagepublicstatus:', updateimagepublicstatus);
});
```

**5. getImages**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
imageservice.getImages(pageLink, imageSubType).subscribe(images => {
  console.log('Images:', images);
});
```

**6. getImageInfo**

```javascript
imageservice.getImageInfo(type, 'your-key').subscribe(imageinfo => {
  console.log('Imageinfo:', imageinfo);
});
```

**7. getImageDataUrl**

```javascript
imageservice.getImageDataUrl('your-imageurl').subscribe(imagedataurl => {
  console.log('Imagedataurl:', imagedataurl);
});
```

**8. loadImageDataUrl**

```javascript
imageservice.loadImageDataUrl('your-imagelink').subscribe(imagedataurl => {
  console.log('Imagedataurl:', imagedataurl);
});
```

**9. getImageString**

```javascript
imageservice.getImageString('your-imageurl').subscribe(imagestring => {
  console.log('Imagestring:', imagestring);
});
```

**10. resolveImageUrl**

```javascript
imageservice.resolveImageUrl('your-imageurl').subscribe(resolveimageurl => {
  console.log('Resolveimageurl:', resolveimageurl);
});
```

**11. downloadImage**

```javascript
imageservice.downloadImage(type, 'your-key').subscribe(downimage => {
  console.log('Downimage:', downimage);
});
```

**12. exportImage**

```javascript
imageservice.exportImage(type, 'your-key').subscribe(exportimage => {
  console.log('Exportimage:', exportimage);
});
```

**13. importImage**

```javascript
imageservice.importImage(imageData).subscribe(importimage => {
  console.log('Importimage:', importimage);
});
```

