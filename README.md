# learn-progressive-web-apps ( PWA )
Learn about Progressive Web Apps


# ABOUT
-

# OFFLINE

## LOCALSTORAGE
- Everything we pass to the ```localStorage.setItem``` function ends up being converted to text. In this conversion some information can be changed and when we retrieve with localStorage.getItem the information has been lost. To avoid this it is important to convert the information to text before storing and convert them back to the initial type after retrieving.
  - Not save types **boolean**, necessary parse. getItem return string to boolean
```javascript
JSON.parse(localStorage.getItem(booleanKey));
```
- **Create offline item**
```javascript
localStorage.setItem(key, value);
```
- **GET offline item**
```javascript
localStorage.getItem(key);
```
- **REMOVE ITEM**
```javascript
localStorage.removeItem(key);
```


## APPLICATION CACHE
- **INIT** | ADDED attribute **manifest** in **html** tag.
  - **CACHE** | list of files to cached
  - **NETWORK** | specific reload url
```html
<html manifest="fileName.manifest">
...
</html>
```
- **CREATE FILE** | fileName.manifest
```json
CHACE MANIFEST

CACHE:
files....

NETWORK:
*
```

## CACHE STORAGE
- Save **URL** and response **CONTENT**
- Are **asynchronous**
- **ACCESS**
```javascript
caches;
```
- **OPEN CACHE**
```javascript
caches.open(name);
```
- **SAVE** in cache | **put**
```javascript
fetch(url).then((response) =>{
  caches.open(name).then(cache => {
    cache.put('url', response);
  });
});
```
- **ADDALL** ADD LIST
```javascript
caches.open(name).then(cache => {
  cache.addAll(list);
});
```

- **GET** in cache | **match**
```javascript
fetch(url).then((response) =>{
  caches.match(name).then(response => {
  });
});
fetch(url).then((response) =>{
  caches.matchAll(name).then(lits => {
  });
});
```
- **DELETE CACHE**
```javascript
caches.delete('cacheName');
```

## SERVICE WORKERS
- Are a **interceptor**
- To **update** close all **application** _tabs_
- **INIT**
  - Create a **register**, and import in html
- **REGISTER SERVICE WORK**
```javascript
navigator.serviceWorker.register('fileName.js');
```
- **CREATE EVENT LISTENER**
```javascript
self.addEventListener("fetch", ()=>{});
```
### EVENTS
- **INSTALL**
```javascript
self.addEventListener("install", ()=>{});
```
- **ACTIVATE**
```javascript
self.addEventListener("activate", ()=>{});
```

# WEB APP MANIFEST
> JSON File to describle the app

- **INIT** | Import file in index
```html
<link rel="manifest" href="name.manifest">
```
- **CONTENT**
```json
{
  name,
  start_url // root folder
  display: "standalone",
  icons : [
    {
      src,
      sizes,
      type
    }
  ]
}
```

# OBSERVATIONS
- **PWA** **P**rogressive **W**eb **A**pps
- **resonse body** **ETAG**, change when the file is modify
- **APPLICATION CACHE** case error stop all.
  - **index** are automatic cached
  - **manifest** is **unique**
  - **not** used in _dynamic files_
- With **SERVICE WORK** the **APPLICATION CACHE** doesnt **work**
- **SERVICE WORKERS**
  - To cache _add_ **index** the _application_
  - To **cache** create new **cache** after **delete** old cache.
- **ADD TO HOMESCREEN** appear automatic, visit site many x
