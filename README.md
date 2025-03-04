# Throttle-Debounce-in-JavaScript
Throttle &amp; Debounce in JavaScript 


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

