# counter-value-increasing-and-decreasing-with-html-css-and-javascript
Here's a basic **text reader** feature (in JavaScript) you can add to your project, which lets users upload a `.txt` file and view its content on the web page:

### 📝 1. Add HTML for file input and display

Add this **inside the `<body>`** tag in `Untitled-1.html`:

```html
<div class="mt-4 text-center">
    <input type="file" id="textFileInput" class="mb-2" />
    <pre id="fileContent" style="white-space: pre-wrap; text-align: left;"></pre>
</div>
```

### 🧠 2. Add this to `untitled.js`

Below your existing functions, paste:

```javascript
document.getElementById("textFileInput").addEventListener("change", function (event) {
    const file = event.target.files[0];
    if (!file) return;

    const reader = new FileReader();
    reader.onload = function (e) {
        document.getElementById("fileContent").textContent = e.target.result;
    };
    reader.readAsText(file);
});
```

### ✅ Result:

This lets users upload a `.txt` file, and its content will be displayed in a formatted `<pre>` block under the counter UI.

Want to extend this with text analysis or editing features?
