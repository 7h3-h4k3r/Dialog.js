
# 📦 Dialog.js

A lightweight, reusable **JavaScript dialog (modal) system** built on top of **jQuery + Bootstrap/CoreUI**.

It allows you to dynamically create dialogs with custom titles, messages, buttons, and events — without writing modal HTML repeatedly.

---

# 🚀 Features

* ✅ Dynamic dialog creation
* ✅ Custom buttons with click handlers
* ✅ Bootstrap & CoreUI support
* ✅ Event handling (show, hide, etc.)
* ✅ Multiple dialogs support (unique IDs)
* ✅ Auto cleanup (removes modal after close)

---

# 🛠️ Requirements

* jQuery
* Bootstrap 5 (or CoreUI)
* CryptoJS (for generating unique IDs)

---

# 📁 Setup

## 1. Include dependencies

```html
<script src="https://code.jquery.com/jquery-3.7.1.min.js"></script>
<script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/js/bootstrap.bundle.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/crypto-js/4.1.1/crypto-js.min.js"></script>
```

---

## 2. Add modal template

```html
<div id="modalsGarbage"></div>

<div id="dummy-dialog-modal" class="modal fade">
  <div class="modal-dialog">
    <div class="modal-content">

      <div class="modal-header">
        <h5 class="modal-title"></h5>
        <small class="modal-subtitle"></small>
      </div>

      <div class="modal-body"></div>

      <div class="modal-footer"></div>

    </div>
  </div>
</div>
```

---

# ⚡ Basic Usage

## Simple Dialog

```js
dialog("Hello", "This is a simple dialog");
```

---

## Custom Dialog

```js
let d = new Dialog("Delete File", "Are you sure?");

d.setButtons([
  {
    name: "Cancel",
    class: "btn-secondary",
    onClick: function () {
      console.log("Cancelled");
    }
  },
  {
    name: "Delete",
    class: "btn-danger",
    onClick: function () {
      console.log("Deleted!");
    }
  }
]);

d.show();
```

---

## Confirm Dialog Helper

```js
display_dialog("Delete", "Delete this file?", function () {
  alert("Deleted!");
});
```

---

# ⚙️ Options

```js
new Dialog(title, message, options)
```

### Available Options

| Option      | Description                                  |
| ----------- | -------------------------------------------- |
| `framework` | `"bootstrap"` or `"coreui"`                  |
| `clone_id`  | Template modal ID                            |
| `size`      | `"small"`, `"medium"`, `"large"`, `"xlarge"` |

---

# 🔘 Button Structure

```js
{
  name: "Button Text",
  class: "btn-primary",
  dismiss: true,
  onClick: function(event) {}
}
```

---

# 🎯 Events

```js
d.setEvents([
  {
    action: "shown",
    callback: function () {
      console.log("Dialog opened");
    }
  }
]);
```

### Supported Events:

* `show`
* `shown`
* `hide`
* `hidden`

---

# 🧠 How It Works

1. Clones a hidden modal template
2. Assigns a unique ID
3. Injects content (title, message, buttons)
4. Appends to DOM
5. Shows modal using Bootstrap/CoreUI
6. Removes modal after closing

---

# ⚠️ Notes

* Ensure `clone_id` exists in HTML
* Place `#modalsGarbage` inside `<body>`
* Avoid duplicate IDs
* Bootstrap 5 recommended

---

# 🔧 Future Improvements

* Remove jQuery dependency
* Convert to ES6 module
* Add animations & themes
* React/Vue integration

---

# 📄 License

MIT License

---

# 🙌 Author

Developed by **7h3-h4k3r**
