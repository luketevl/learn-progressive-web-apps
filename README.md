# learn-progressive-web-apps ( PWA )
Learn about Progressive Web Apps


# ABOUT
-

# OFFLINE

## LOCALSTORAGE
- Tudo que passamos para a função ```localStorage.setItem``` acaba sendo convertido para texto. Nessa conversão algumas informações podem ser alteradas e quando recuperarmos com localStorage.getItem a informação foi perdida. Para evitar isso é importante converter as informações para texto antes de armazenar e convertê-las novamente para o tipo inicial depois de recuperar.
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
localStorage.removeItem(key);

# OBSERVATIONS
- **PWA** **P**rogressive **W**eb **A**pps
