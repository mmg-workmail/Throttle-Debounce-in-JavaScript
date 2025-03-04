# 🚀 Throttle & Debounce in JavaScript  

Handling **frequent events** like `scroll`, `resize`, and `input` efficiently can greatly improve performance.  
This repository explains **Throttle & Debounce**, two essential techniques for optimizing event handling.  

---

## 🔥 What is Throttle?  
Throttle ensures that a function is called **at most once** within a specified time interval.  
### **✅ Use Cases:**  
✔️ Scroll Events  
✔️ Mouse Movement  
✔️ Window Resize  

### **📌 Example:**
```js

function throttle(func, limit) {
  let lastCall = 0;
  return function (...args) {
    const now = Date.now();
    if (now - lastCall >= limit) {
      lastCall = now;
      func.apply(this, args);
    }
  };
}

// Usage: Logs "Scrolling..." at most once every 1 second
window.addEventListener(
  "scroll",
  throttle(() => console.log("Scrolling..."), 1000)
);

```

---

## ⏳ What is Debounce? 
Debounce ensures that a function executes only after a delay and only if no further calls happen within that time.
### **✅ Use Cases:**  
✔️ Search Box Typing  
✔️ Auto-Save Forms  
✔️ Button Click Prevention  

### **📌 Example:**
```js

function debounce(func, delay) {
  let timer;
  return function (...args) {
    clearTimeout(timer);
    timer = setTimeout(() => {
      func.apply(this, args);
    }, delay);
  };
}

// Usage: Executes search function only after typing stops for 500ms
document.getElementById("search").addEventListener(
  "input",
  debounce((event) => {
    console.log("Searching for:", event.target.value);
  }, 500)
);

```

## 📢 Let's Connect!
If you found this useful, don't forget to star ⭐ the repo and follow me on GitHub! 😎



