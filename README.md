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




# OBSERVATIONS
- **PWA** **P**rogressive **W**eb **A**pps
