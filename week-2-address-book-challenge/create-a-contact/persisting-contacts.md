# Persisting contacts

We've come a long way with our application, what is left to do now is to actually store the contact and display it on the page. For storage, we've decided to keep things simple and make use of `localStorage`.

[LocalStorage](https://developer.mozilla.org/en-US/docs/Web/API/Window/localStorage) is a [Web Storage API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Storage_API/Using_the_Web_Storage_API) property which will allow us to store key/value pairs that are saved across browser sessions. Remember one of the requirements for the application was to have the ability to view previously saved contact. There are other alternatives that can be used to achieve this, but just to keep things simple, we will go with localStorage for this iteration of the application.

In order to save the contact we need to add the following snippet of code in the `submit` event listener we setup in the previous step.

{% code-tabs %}
{% code-tabs-item title="src/app.js" %}
```javascript
  addContactForm.addEventListener('submit', event => {
    event.preventDefault()
    const localStorage = window.localStorage
    ...
    console.log(`Saving the following contact: ${JSON.stringify(contact)}`)
    localStorage.setItem('contacts', JSON.stringify([contact]))
  })
```
{% endcode-tabs-item %}
{% endcode-tabs %}



