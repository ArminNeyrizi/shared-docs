To understand how React works, we first need a basic understanding of how browsers interpret your code to create (or render) user interfaces (UI).

When a user visits a web page, the server returns an HTML file to the browser that may look like this:

![Two side-by-side diagrams, left showing the HTML code, and right showing the DOM tree.](https://nextjs.org/_next/image?url=https%3A%2F%2Fh8DxKfmAPhn8O0p3.public.blob.vercel-storage.com%2Flearn%2Fdark%2Flearn-html-and-dom.png&w=3840&q=75)

The browser then reads the HTML and constructs the Document Object Model (DOM).

### What is the DOM?[](https://nextjs.org/learn/react-foundations/rendering-ui#what-is-the-dom)

The DOM is an object representation of the HTML elements. It acts as a bridge between your code and the user interface, and has a tree-like structure with parent and child relationships.

![Two side-by-side diagrams, left showing the DOM tree, and right showing the rendered UI.](https://nextjs.org/_next/image?url=https%3A%2F%2Fh8DxKfmAPhn8O0p3.public.blob.vercel-storage.com%2Flearn%2Fdark%2Flearn-dom-and-ui.png&w=3840&q=75)

You can use DOM methods and JavaScript, to listen to user events and [manipulate the DOM](https://developer.mozilla.org/docs/Learn/JavaScript/Client-side_web_APIs/Manipulating_documents) by selecting, adding, updating, and deleting specific elements in the user interface. DOM manipulation allows you to not only target specific elements, but also change their style and content.

In the next section you'll learn how to use JavaScript and DOM methods.

> **Additional Resources:**
> 
> - [Introduction to the DOM](https://developer.mozilla.org/docs/Web/API/Document_Object_Model/Introduction)
> - [How to view the DOM in Google Chrome](https://developer.chrome.com/docs/devtools/dom/)
> - [How to view the DOM in Firefox](https://firefox-source-docs.mozilla.org/devtools-user/debugger/how_to/highlight_and_inspect_dom_nodes/index.html)

سوال ها
---

### ۱. وقتی کاربر یک صفحه وب را باز می‌کند، سرور چه چیزی به مرورگر می‌فرستد؟
**پاسخ:**  
سرور یک فایل **HTML** به مرورگر ارسال می‌کند.

---

### ۲. مرورگر بعد از دریافت فایل HTML چه کاری انجام می‌دهد؟
**پاسخ:**  
مرورگر HTML را می‌خواند و از روی آن **Document Object Model (DOM)** را می‌سازد.

---

### ۳. DOM چیست؟
**پاسخ:**  
DOM یک **نمایش شیء‌محور (Object Representation)** از عناصر HTML است که به‌صورت یک **ساختار درختی** شامل رابطه‌های والد و فرزند سازمان‌دهی شده است.

---

### ۴. چرا DOM را «پل ارتباطی» بین کد و رابط کاربری می‌دانند؟
**پاسخ:**  
چون JavaScript از طریق DOM می‌تواند به عناصر صفحه دسترسی داشته باشد و آن‌ها را تغییر دهد، و این تغییرات مستقیماً در **UI** دیده می‌شوند.

---

### ۵. ساختار DOM چگونه است؟
**پاسخ:**  
DOM به شکل یک **درخت (Tree-like structure)** است که هر عنصر می‌تواند والد یا فرزند عناصر دیگر باشد.

---

### ۶. با استفاده از JavaScript و DOM چه کارهایی می‌توان انجام داد؟
**پاسخ:**  
می‌توان:
- به رویدادهای کاربر (مثل کلیک) گوش داد  
- عناصر را **انتخاب، اضافه، ویرایش یا حذف** کرد  
- **استایل و محتوای** عناصر را تغییر داد  

---

### ۷. DOM manipulation به چه معناست؟
**پاسخ:**  
DOM manipulation یعنی **تغییر دادن عناصر صفحه وب** با استفاده از JavaScript، مثل تغییر متن، رنگ، یا ساختار عناصر.

---

### ۸. آیا DOM همان HTML است؟
**پاسخ:**  
خیر.  
HTML یک **فایل متنی** است، اما DOM یک **ساختار شیء‌ای در حافظه مرورگر** است که از HTML ساخته می‌شود.

---

### ۹. چرا درک DOM برای یادگیری React مهم است؟
**پاسخ:**  
چون React در نهایت رابط کاربری را از طریق **تغییر DOM (یا Virtual DOM)** به‌روزرسانی می‌کند و فهم DOM کمک می‌کند عملکرد React را بهتر درک کنیم.

---