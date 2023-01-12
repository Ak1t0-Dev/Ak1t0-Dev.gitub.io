# Web Storage API

When you start to create an e-commerce website, you might think you want to implement a function that stores the information of products a user chose, such as "add to cart" and "add to favorites" in browsers.  

In this situation, you can use Web Storage API to handle it. The Web Storage API provides mechanisms that browsers can store key/value pairs and these exist even a page is loaded.  

The Web Storage maintains the store area seperated in each origin and there are two kinds of mechanism.  

&emsp;sessionStorage: key/value pairs are available to use until a session ends, meaning it stores data until browser or tab is closed.  

&emsp;localStorage: key/value pairs are available to use when catch or stored data is cleared, meaning it stores data even browser or tab is closed.  

NOTE: You have to make sure that if the local storage is available to use because that some of browsers can disable the local storage. A simple assumption of the property exists might cause the error.  
In private browsing mode on Safari provides the local storage with no capacity so it is not available to use it.  

To access to the current domain's session and local Storage objects, needs to use Window.sessionStorage and Window.localStorage properties respectively (The Web Storage API extends the Window objects).   

Using these properties, an instance of Storage objects is generated and it allows you to manipulate the storage.  

set an item in a storage  

storage.setItem(keyName, keyValue);  

```JavaScript
function setInStorage() {
    sessionStorage.setItem('001', 'dog');
    sessionStorage.setItem('002', 'cat');
    sessionStorage.setItem('003', 'bird');
}

setInStorage();
```

If you execute the function, you can see that items are stored in the storage like below.  

Chrome DevTools > Application  
[!setItem](/img/webStorageAPI-setInStorage.png)


get an item from a storage  

storage.getItem(keyName);  

```JavaScript
sessionStorage.getItem('001'); // if the key doesn't exist, it will
```

remove an item from a storage  

storage.removeItem(keyName);  

```JavaScript
sessionStorage.removeItem('001');
```

remove all items from a storage  

storage.clear();  

```JavaScript
sessionStorage.clear();
```

### references  
https://developer.mozilla.org/en-US/docs/Web/API/Web_Storage_API
https://developer.mozilla.org/ja/docs/Web/API/Web_Storage_API/Using_the_Web_Storage_API
