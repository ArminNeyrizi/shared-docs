می‌توانید این متن را در یک فایل `.tex` کپی کنید و با کامپایلرهای آنلاین (مثل Overleaf) یا محلی خود اجرا کنید تا خروجی را ببینید.

```latex
\documentclass[12pt, a4paper]{article}
\usepackage[utf8]{inputenc}
\usepackage[T1]{fontenc}
\usepackage{lmodern} % فونت استاندارد
\usepackage{amsmath, amssymb, amsfonts} % برای ریاضیات
\usepackage{graphicx} % برای تصاویر
\usepackage{hyperref} % برای لینک‌ها
\usepackage{geometry}
\geometry{left=2.5cm, right=2.5cm, top=2.5cm, bottom=2.5cm}

\title{LaTeX Cheat Sheet}
\author{ZharfaTech / Shaboof}
\date{\today}

\begin{document}

\maketitle

\section{ساختار کلی سند}
هر سند لاتک در یک محیط \texttt{document} قرار می‌گیرد.
\begin{verbatim}
\documentclass{article} % یا book, report, beamer
\begin{document}
    متن شما اینجا نوشته می‌شود.
\end{document}
\end{verbatim}

\section{سرفصل‌ها (Sections)}
برای ایجاد بخش‌بندی از دستورات زیر استفاده کنید:
\begin{itemize}
    \item \texttt{\textbackslash section{نام بخش}}
    \item \texttt{\textbackslash subsection{نام زیربخش}}
    \item \texttt{\textbackslash subsubsection{زیرزیربخش}}
    \item \texttt{\textbackslash paragraph{پاراگراف}}
\end{itemize}

\section{فرمت متن (Text Formatting)}
\begin{itemize}
    \item \textbf{Bold}: \texttt{\textbackslash textbf{متن}} $\rightarrow$ \textbf{متن}
    \item \textit{Italic}: \texttt{\textbackslash textit{متن}} $\rightarrow$ \textit{متن}
    \item \underline{Underline}: \texttt{\textbackslash underline{متن}} $\rightarrow$ \underline{متن}
    \item \texttt{Typewriter}: \texttt{\textbackslash texttt{متن}} $\rightarrow$ \texttt{متن}
    \item \textsc{Small Caps}: \texttt{\textbackslash textsc{متن}} $\rightarrow$ \textsc{متن}
    \item \textbf{Bold Italic}: \texttt{\textbackslash textbf{\textbackslash textit{متن}}}
\end{itemize}

\section{معرفی پاراگراف و خط جدید}
\begin{itemize}
    \item \textbf{خط جدید}: \texttt{\textbackslash \textbackslash} (دو بک‌اسلش)
    \item \textbf{پاراگراف جدید}: یک خط خالی بین متن‌ها بگذارید.
    \item \textbf{بدون تورفتگی}: \texttt{\textbackslash noindent}
\end{itemize}

\section{ریاضیات (Mathematics)}
برای نوشتن فرمول‌ها از محیط‌های ریاضی استفاده کنید.

\subsection{ریاضیات درون‌خطی (Inline Math)}
فرمول در وسط متن: \( E = mc^2 \)
کد: \texttt{\textbackslash \( E = mc^2 \textbackslash \)} یا \texttt{\textbackslash( E = mc^2 \textbackslash)}

\subsection{ریاضیات بلوکی (Display Math)}
فرمول در خط جداگانه:
\[
    \sum_{i=1}^{n} i = \frac{n(n+1)}{2}
\]
کد:
\begin{verbatim}
\[
    \sum_{i=1}^{n} i = \frac{n(n+1)}{2}
\]
\end{verbatim}

\subsection{نمادهای رایج ریاضی}
\begin{itemize}
    \item توان: \texttt{\^{}{}} $\rightarrow$ \( x^2 \)
    \item اندیس (پایین): \texttt{\_\_} $\rightarrow$ \( x_1 \)
    \item کسر: \texttt{\textbackslash frac\{صورت\}\{مخرج\}} $\rightarrow$ \( \frac{a}{b} \)
    \item رادیکال: \texttt{\textbackslash sqrt\{\}} $\rightarrow$ \( \sqrt{x} \)
    \item سیگما: \texttt{\textbackslash sum} $\rightarrow$ \( \sum \)
    \item انتگرال: \texttt{\textbackslash int} $\rightarrow$ \( \int \)
    \item حد: \texttt{\textbackslash lim} $\rightarrow$ \( \lim \)
    \item گسسته: \texttt{\textbackslash set} $\rightarrow$ \( \in \)
    \item نامساوی: \texttt{<}, \texttt{>}, \texttt{\textbackslash leq}, \texttt{\textbackslash geq}
    \item یونان: \texttt{\textbackslash alpha}, \texttt{\textbackslash beta}, \texttt{\textbackslash Gamma}
\end{itemize}

\subsection{آرایش فرمول‌ها (Align)}
برای تراز کردن چند معادله:
\begin{verbatim}
\begin{align}
    a &= b + c \\
    d &= e + f
\end{align}
\end{verbatim}

\section{فهرست‌ها و لیست‌ها}

\subsection{لیست بدون شماره (Itemize)}
\begin{itemize}
    \item آیتم اول
    \item آیتم دوم
    \begin{itemize}
        \item زیرمجموعه
    \end{itemize}
\end{itemize}

\subsection{لیست شماره‌دار (Enumerate)}
\begin{enumerate}
    \item مرحله اول
    \item مرحله دوم
    \item مرحله سوم
\end{enumerate}

\subsection{تعریف لیست سفارشی (Description)}
\begin{description}
    \item[کلید ۱] توضیح مربوط به کلید یک
    \item[کلید ۲] توضیح مربوط به کلید دو
\end{description}

\section{جداول (Tables)}
\begin{verbatim}
\begin{table}[h!]
    \centering
    \begin{tabular}{|c|c|c|}
        \hline
        \textbf{ستون ۱} & \textbf{ستون ۲} & \textbf{ستون ۳} \\
        \hline
        داده ۱ & داده ۲ & داده ۳ \\
        \hline
        داده ۴ & داده ۵ & داده ۶ \\
        \hline
    \end{tabular}
    \caption{عنوان جدول}
\end{table}
\end{verbatim}
\textit{توضیح: در \{c|c|c\} حروف c یعنی وسط‌چین (center)، l یعنی چپ‌چین (left)، r یعنی راست‌چین (right).}

\section{تصاویر (Figures)}
\begin{verbatim}
\begin{figure}[h!]
    \centering
    \includegraphics[width=0.5\textwidth]{image.png}
    \caption{عنوان تصویر}
    \label{fig:my_label}
\end{figure}
\end{verbatim}
\textit{نکته: فایل تصویر باید در پوشه پروژه باشد.}

\section{ارجاع‌دهی و فهرست مطالب}
\begin{itemize}
    \item \textbf{تعریف برچسب}: \texttt{\textbackslash label\{sec:intro\}}
    \item \textbf{ارجاع به بخش}: \texttt{\textbackslash ref\{sec:intro\}} $\rightarrow$ شماره بخش
    \item \textbf{ارجاع به شکل}: \texttt{\textbackslash ref\{fig:my\_label\}}
    \item \textbf{ایجاد فهرست مطالب}: \texttt{\textbackslash tableofcontents} (باید دو بار کامپایل شود)
\end{itemize}

\section{معرفی بسته‌های پرکاربرد (Packages)}
\begin{itemize}
    \item \texttt{amsmath}: ابزارهای پیشرفته ریاضی
    \item \texttt{graphicx}: کار با تصاویر
    \item \texttt{hyperref}: لینک‌های داخلی و خارجی
    \item \texttt{geometry}: تنظیم حاشیه‌های صفحه
    \item \texttt{color} یا \texttt{xcolor}: رنگ‌آمیزی متن
    \item \texttt{listings}: نمایش کدهای برنامه‌نویسی
    \item \texttt{tikz}: رسم نمودار و شکل‌های گرافیکی پیشرفته
\end{itemize}

\section{نکات کلیدی}
\begin{itemize}
    \item \textbf{کاراکترهای خاص}: برخی کاراکترها معنای خاص دارند و باید با بک‌اسلش escape شوند:
    \begin{itemize}
        \item \#: \texttt{\textbackslash \#}
        \item \$: \texttt{\textbackslash \$}
        \item \%: \texttt{\textbackslash \%}
        \&: \texttt{\textbackslash \&}
        \textasciicircum: \texttt{\textbackslash \^{}}
        \_ (Underscore): \texttt{\textbackslash \_}
        \textasciitilde: \texttt{\textbackslash \textasciitilde}
        \|: \texttt{\textbackslash |}
    \end{itemize}
    \item \textbf{نظرات}: هر خطی که با \texttt{\%} شروع شود، توسط کامپایلر نادیده گرفته می‌شود.
    \item \textbf{دو بار کامپایل}: برای به‌روزرسانی فهرست مطالب، ارجاعات و ایندکس، معمولاً باید سند را دو بار کامپایل کنید.
\end{itemize}

\end{document}
```

### نکات مهم برای استفاده از این چیت‌شیت:

1.  **کامپایلر**: برای بهترین نتیجه، از کامپایلر `pdfLaTeX` یا `XeLaTeX` (اگر نیاز به فونت فارسی دارید) استفاده کنید.
2.  **فونت فارسی**: اگر قصد دارید متن فارسی بنویسید، باید از بسته `xeCJK` یا `polyglossia` (برای XeLaTeX) استفاده کنید و فونت‌های فارسی (مثل B Nazanin یا Vazir) را در preamble تعریف نمایید.
3.  **Overleaf**: اگر تازه کار هستید، پیشنهاد می‌کنم کد بالا را در [Overleaf.com](https://www.overleaf.com) کپی کنید تا بدون نصب نرم‌افزار، خروجی را ببینید.


- [ ] نرم افزار Obsidian را نصب کنید
- [ ] ![[Pasted image 20260420131400.png]]
- [ ] این افزونه، که باهاش لیتک سریع می‌نویسند را نصب کنید.
- [ ] یک نمونه کد لیتک بنویسید.