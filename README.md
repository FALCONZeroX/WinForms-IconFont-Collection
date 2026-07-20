# 🎨 WinForms IconFont Collection

<p align="center">
<img src="https://img.shields.io/badge/.NET%20Framework-4.7.2%2B-512BD4?logo=dotnet&logoColor=white" alt=".NET Framework 4.7.2+" />
<img src="https://img.shields.io/badge/.NET-6%2B-512BD4?logo=dotnet&logoColor=white" alt=".NET 6+" />
<img src="https://img.shields.io/badge/.NET-8%2B-512BD4?logo=dotnet&logoColor=white" alt=".NET 8+" />

<img src="https://img.shields.io/badge/Icons-Vector%20%F0%9F%8E%AF%20DPI%20Aware-important" alt="Vector Icons DPI Aware" />
<img src="https://img.shields.io/badge/Memory-Safe%20%F0%9F%A7%A0-green" alt="Memory Safe" />
<img src="https://img.shields.io/badge/Zero-Installation%20%F0%9F%93%A6-blue" alt="Zero Installation" />
<img src="https://img.shields.io/badge/DPI-Scaling%20Ready%20%F0%9F%96%A5%EF%B8%8F-ff69b4" alt="DPI Scaling Ready" />

<img src="https://img.shields.io/github/stars/FALCONzeroX/WinForms-IconFont-Collection?style=social" alt="GitHub Stars" />
<img src="https://img.shields.io/github/forks/FALCONzeroX/WinForms-IconFont-Collection?style=social" alt="GitHub Forks" />
<img src="https://img.shields.io/github/issues/FALCONzeroX/WinForms-IconFont-Collection" alt="GitHub Issues" />
<img src="https://img.shields.io/github/last-commit/FALCONzeroX/WinForms-IconFont-Collection" alt="Last Commit" />

<img src="https://img.shields.io/badge/Icon%20Sets-Font%20Awesome%20%7C%20Material%20%7C%20Ionicons-informational" alt="Supported Icon Sets" />

<img src="https://img.shields.io/badge/build-passing-brightgreen" alt="Build Status" />
<img src="https://img.shields.io/badge/code%20quality-A+-brightgreen" alt="Code Quality" />
</p>

---

## The Problem: Why Traditional Icons Fail on Modern Screens

If you’ve ever built a Windows Forms application and tested it on a high‑DPI monitor (4K, 125%, 150%, 200% scaling), you’ve witnessed the **icon blur**. A beautifully designed 32×32 pixel icon becomes a smeared, fuzzy mess the moment the operating system tries to stretch it to match the screen’s scaling factor.  

This isn’t a bug in your code – it’s a fundamental limitation of **raster (bitmap) image formats** like `.png` and `.ico`.  

### How Bitmap Icons Work (and Why They Break)

A PNG or ICO file stores an icon as a fixed grid of colored pixels. At 100% DPI (96 DPI standard), every pixel maps perfectly to a physical screen pixel. But modern screens have much higher pixel densities. To keep UI elements physically the same size, Windows tells applications to render at a larger logical scale – for example, **150%** means every control (and every icon) must be drawn 1.5× larger.

With a bitmap, there is no extra detail beyond the original grid. The graphics engine must **interpolate** – guess what the extra pixels should look like. This interpolation creates:
- **Blur and softness**: edges become undefined.
- **Jagged “stair‑step” artifacts**: diagonal lines look pixelated.
- **Inconsistent appearance**: icons designed at 16×16 look completely different from those forced to render at 24×24 or 32×32.

Even the common “multi‑resolution ICO” trick (embedding several fixed sizes like 16×16, 32×32, 48×48) fails at fractional scaling values like 125% or 175%, because the scaling factor rarely matches an exact pre‑made size. The result is always a compromise.

---

### 🌐 المشكلة: لماذا تبدو الأيقونات التقليدية سيئة على الشاشات الحديثة

إذا قمت سابقاً ببناء تطبيق Windows Forms وجربته على شاشة عالية الدقة (4K، أو إعدادات تكبير مثل 125% أو 150% أو 200%)، فأنت بالتأكيد لاحظت **ضبابية الأيقونات**. أيقونة صممت بدقة 32×32 بكسل تتحول إلى فوضى مشوشة عندما يحاول النظام تمديدها لتتناسب مع معامل التكبير.

هذا ليس خطأً في كودك – بل هو قصور جوهري في **الصيغ النقطية (Bitmap)** مثل PNG و ICO.

#### كيف تعمل الأيقونات النقطية – ولماذا تفشل

ملف PNG أو ICO يخزّن الأيقونة على هيئة شبكة ثابتة من البكسلات الملوّنة. عند دقة 100% (96 DPI)، كل بكسل يقابل تماماً بكسل شاشة حقيقي. لكن الشاشات الحديثة تملك كثافة بكسلات أعلى بكثير. وللحفاظ على الحجم الفعلي للعناصر، يطلب ويندوز من التطبيقات أن ترسم بمقياس منطقي أكبر – مثلاً **150%** تعني أن كل عنصر (وكل أيقونة) يجب رسمه بحجم 1.5 ضعف.

مع الصورة النقطية، لا توجد تفاصيل إضافية خارج الشبكة الأصلية. محرك الرسم يضطر إلى **الاستكمال (Interpolation)** – أي تخمين كيف يجب أن تبدو البكسلات الإضافية. هذا الاستكمال ينتج عنه:
- **ضبابية وتلاشي**: الحواف تصبح غير محددة.
- **تشوهات (Stair‑step)**: الخطوط القطرية تبدو مكعبة.
- **مظهر غير متجانس**: أيقونات 16×16 تبدو مختلفة تماماً عند رسمها بحجم 24×24 أو 32×32.

حتى حيلة الأيقونات متعددة الأحجام (ICO تحتوي على عدة طبقات 16×16، 32×32، 48×48) تفشل عند معاملات تكبير كسرية مثل 125% أو 175%، لأن المعامل نادراً ما يطابق أحد الأحجام الجاهزة. والنتيجة دائماً حل وسط غير مرضٍ.

---

## Why Icon Fonts Are the Superior Choice

Icon fonts (`.ttf` / `.otf`) solve every scaling problem mentioned above **by design**. Instead of storing pixels, they store **mathematical outlines** – just like the system fonts you use for text (Segoe UI, Arial, etc.).  

### The Vector Advantage

- **Infinite resolution**: A vector outline is resolution‑independent. When you render it at 16pt, 64pt, or 256pt, the operating system recalculates the exact shape using the same mathematical curves. The result is **perfect sharpness at any DPI level** – no interpolation, no blur.
- **Sub‑pixel rendering**: Modern font engines apply anti‑aliasing (ClearType) that leverages the physical arrangement of LCD sub‑pixels, making icon edges even smoother and more readable than a bitmap could ever achieve.
- **Consistency across the entire application**: Because icon fonts are rendered by the same text layout engine as labels and buttons, they automatically respect the system’s DPI settings. You set a font size in points, and the system handles the rest.
- **Scalability (Flexibility when resizing)**: Raster images (such as PNG or ICO files) come in fixed sizes; if you try to scale them up or down, they do not adapt well because their dimensions are predetermined. In contrast, using an icon font offers complete flexibility during application development, as the icons are treated just like standard characters.

---

## 🔒 The Problem of Including Fonts

When you use a custom icon font in a Windows Forms application, you must deliver the font file (`.ttf` / `.otf`) to every user’s machine so that the operating system can render the icons. How you deliver it directly impacts security, reliability, and maintenance.

### The Problem
Fonts are normally stored in `C:\Windows\Fonts` and are available to all applications. To make a custom font available, you have three options:

| Approach | Problems |
| :--- | :--- |
| **1. Install font globally** | - Requires administrator rights (UAC prompt).<br>- Pollutes the system font folder permanently.<br>- May conflict with other versions of the same font.<br>- Uninstalling your app does not remove the font.<br>- Breaks on locked‑down corporate environments. |
| **2. Ship font as a loose file**| - The `.ttf` must be placed next to the `.exe` – easy to delete or lose.<br>- Network deployments and shortcuts break if the file is missing.<br>- Extra file means extra support headaches. |
| **3. Embed font as resource** | ✅ **No admin rights needed.**<br>✅ **Single‑file deployment** – font lives inside the `.exe`.<br>✅ **Impossible to lose or misplace.**<br>✅ **Isolated** – no other app can see or interfere with it.<br>✅ **Clean uninstall** – nothing left behind. |

### Why Embedding as a Resource is the Best Solution

Embedding the font as a **binary resource** inside your `.exe` works by loading the font data directly into unmanaged memory and registering it with GDI+ via `PrivateFontCollection.AddMemoryFont`. The font exists **only in the memory of your process** and is completely invisible to the rest of the system. This technique:

- **Bypasses the need for administrator elevation** – no setup, no UAC pop‑ups.
- **Guarantees the exact version of the font** you tested with – no risk of a user replacing it with an incompatible copy.
- **Enables true single‑file deployments** (xcopy, ClickOnce, MSIX) with no external dependencies.
- **Keeps the user’s system clean** – the font disappears when the application exits.

> ⚠️ **Critical implementation note:** The memory block holding the font data must not be freed until the `PrivateFontCollection` is disposed. Premature cleanup causes rendering crashes. Our architecture uses **deferred cleanup** (tracking all `IntPtr` pointers and freeing them only on application exit) to guarantee safety.

### Practical Benefits for WinForms Developers
- **Zero installation on the client machine**: By embedding the font file directly inside your `.exe` as a resource, you bypass the need to install anything in the Windows Fonts folder. The font is loaded entirely from memory and stays private to your application.
- **Single‑file deployment**: The icon set travels with your executable – no extra PNG files to lose or mismanage.
- **Flexibility**: You can change the icon color, size, or even apply text effects (bold, outline) just by modifying the `Font` object’s properties. No need to ask a designer for a new asset file.

---

### 🌐 مميزات الخطوط التي تحتوي على الأيقونات (Vector)
- **دقة غير محدودة**: المخطط المتجهي Vector مستقل عن الدقة. عندما ترسمه بحجم 16 أو 64 أو 256 نقطة، يعيد النظام حساب الشكل بدقة باستخدام نفس المنحنيات الرياضية. والنتيجة **حدة كاملة عند أي مستوى DPI** – بلا استكمال ولا ضبابية.
- **عرض تحت البكسلي (Sub‑pixel)**: محركات الخطوط الحديثة تطبق صقل الحواف (ClearType) الذي يستغل الترتيب الفيزيائي للبكسلات الثانوية في شاشات LCD، مما يجعل حواف الأيقونة أكثر نعومة وقراءةً مما يمكن لأي صورة نقطية تحقيقه.
- **تجانس تام عبر التطبيق**: لأن خطوط الأيقونات ترسم بواسطة نفس محرك تنسيق النصوص، فهي تحترم تلقائياً إعدادات DPI للنظام. أنت تحدد حجم الخط بالنقاط، والنظام يتولى الباقي.
- **مرونة عند التكبير والتصغير**: إذا كانت لديك صورة نقطية من النوع png أو ico فهي تأتي بحجم محدد مسبقاً وإذا أردت تكبيرها أو تصغيرها فهي لا تستجيب بشكل جيد لأن أبعادها مقيدة، ولكن عند استخدام خط يحتوي على الأيقونات فستحصل على مرونة كاملة في عملية تطوير التطبيقات لأنك ستعامل الأيقونات وكأنها حروف عادية.

### 🌐 مشكلة تضمين الخط: لماذا تضمين الخط داخل ملف .exe مهم بدلاً من الاعتماد على خطوط الويندوز المثبتة مسبقاً؟
عندما تستخدم خط أيقونات مخصصاً في تطبيق Windows Forms، يجب أن يصل ملف الخط (`.ttf` / `.otf`) إلى جهاز كل مستخدم ليتمكن النظام من رسم الأيقونات. الطريقة التي تختارها للتوصيل تؤثر مباشرة على الأمان والموثوقية والصيانة.

#### المشكلة
الخطوط عادةً ما تخزن في `C:\Windows\Fonts` وتكون متاحة لجميع التطبيقات. هناك ثلاث طرق لجعل خط مخصص متاحاً:

| الطريقة | المشاكل |
| :--- | :--- |
| **1. تثبيت الخط بشكل نظامي** | - يتطلب صلاحيات مدير (ظهور UAC).<br>- يلوث مجلد خطوط النظام بشكل دائم.<br>- قد يتعارض مع نسخ أخرى من نفس الخط من برامج أخرى.<br>- إزالة التطبيق لا تزيل الخط – يضطر المستخدم للتنظيف يدوياً.<br>- يفشل في بيئات الشركات المقفلة حيث يُمنع تثبيت الخطوط. |
| **2. توزيع الخط كملف منفصل** | - يجب أن يوضع بجانب `.exe` – سهل الحذف أو التغيير أو الضياع.<br>- الانتشار الشبكي والاختصارات تنكسر إذا اختفى الملف.<br>- ملف إضافي يعني صداع دعم فني إضافي. |
| **3. تضمين الخط كمورد** | ✅ **لا حاجة لصلاحيات مدير.**<br>✅ **نشر أحادي الملف** – الخط يعيش داخل `.exe`.<br>✅ **مستحيل ضياعه أو تغييره.**<br>✅ **معزول** – لا تطبيق آخر يمكنه رؤية الخط أو التداخل معه.<br>✅ **إزالة نظيفة** – لا يترك أثراً بعد الحذف. |

#### لماذا التضمين كمورد هو الحل الأفضل؟
تضمين الخط **كمورد ثنائي** داخل `.exe` يتم عبر تحميل بيانات الخط إلى ذاكرة غير مدارة وتسجيلها مع GDI+ باستخدام `PrivateFontCollection.AddMemoryFont`. الخط يوجد **فقط في ذاكرة عمليتك** وهو غير مرئي تماماً لبقية النظام. هذا الأسلوب:
- **يتجاوز الحاجة لصلاحيات المسؤول** – لا تنصيب، ولا نوافذ UAC منبثقة.
- **يضمن النسخة الدقيقة التي اختبرتها** – لا خطر من استبدال المستخدم لها بنسخة غير متوافقة.
- **يمكّن النشر الحقيقي أحادي الملف** (xcopy، ClickOnce، MSIX) بدون أي ارتباطات خارجية.
- **يحافظ على نظام المستخدم نظيفاً** – الخط يختفي عند خروج التطبيق.

> ⚠️ **ملاحظة تنفيذية حرجة:** كتلة الذاكرة التي تحوي بيانات الخط يجب ألا تُحرّر قبل التخلص من `PrivateFontCollection`. التحرير المبكر يسبب أعطالاً في الرسم. بنيتنا تستخدم **التنظيف المؤجل** (تتبع جميع مؤشرات `IntPtr` وتحريرها فقط عند خروج التطبيق) لضمان السلامة الكاملة.

#### فوائد عملية لمطوري WinForms
- **صفر تثبيت على جهاز العميل**: عبر تضمين ملف الخط كمورد داخل `.exe`، تتجاوز الحاجة لتثبيت أي شيء في مجلد الخطوط. يُحمّل الخط بالكامل من الذاكرة ويبقى خاصاً بتطبيقك.
- **نشر أحادي الملف**: مجموعة الأيقونات تسافر داخل الملف التنفيذي – لا ملفات PNG ضائعة أو منسية.
- **مرونة**: تستطيع تغيير لون الأيقونة أو حجمها أو حتى تطبيق تأثيرات (خط عريض، حدود) بمجرد تعديل خصائص كائن `Font`. لا حاجة لطلب ملف جديد من المصمم.

---

# 📖 How to Use Icon Fonts in WinForms | دليل استخدام أيقونات الخطوط

---

## 🛠️ Step 1: Embedding the Font into Resources | أولاً: تضمين الخط داخل موارد المشروع

Before writing code, the font file (`.ttf` or `.otf`) must be bundled inside the application executable.

قبل كتابة الكود، يجب دمج ملف الخط داخل ملف التطبيق التنفيذي عبر الخطوات التالية:

1. In **Solution Explorer**, right-click the project and select **Properties**.
2. Go to **Resources**; if it does not exist, click the link to create it.
3. Click the **Add Resource** drop-down menu and select **Add Existing File…** (or click the **+** icon).
4. In the file selection window, change the file type filter to **All Files** or **Font Files** and select your font.
Your font is now included in the project resources.

---

1. من **Solution Explorer**، اضغط بزر الفأرة الأيمن على المشروع واختر **Properties**.
2. اذهب إلى تبويب **Resources**، وإذا لم يكن موجوداً اضغط على الرابط لإنشائه.
3. اضغط على القائمة المنسدلة **Add Resource** واختر **Add Existing File…** أو اضغط على علامة **+**.
4. في نافذة اختيار الملف، غيّر فلتر النوع إلى اختيار كافة الملفات ومن ثم قم باختيار الخط المطلوب.
الآن خطك أصبح متاحاً وموجوداً في Resources المشروع كـ `byte[]`.

---

## 💻 Step 2: Safe Memory Loading Code | ثانياً: كود تحميل الخط إلى الذاكرة

Here is the clean, production-grade generic code. Copy this framework directly into your **Form** file (`Form1.cs`).

هذا هو الكود العام والآمن، يمكنك نسخه ولصقه مباشرة داخل ملف النافذة لديك.

```csharp
using System;
using System.Collections.Generic;
using System.Drawing;
using System.Drawing.Text;
using System.Runtime.InteropServices;
using System.Windows.Forms;

namespace WinForms_IconFont_Demo
{
    public partial class MainForm : Form
    {
        // 1. Unified collection to store and manage custom font families
        private PrivateFontCollection _privateFonts = new PrivateFontCollection();

        // 2. Generic font instances that will hold our custom icon fonts
        private Font _iconFontPrimary;
        private Font _iconFontSecondary;

        // 3. Track unmanaged memory pointers to guarantee deferred, safe cleanup upon closing
        private List<IntPtr> _fontPointers = new List<IntPtr>();

        // Win32 API to register the memory-resident font into the Windows GDI subsystem
        [DllImport("gdi32.dll")]
        private static extern IntPtr AddFontMemResourceEx(IntPtr pbFont, uint cbFont, IntPtr pdv, [In] ref uint pcFonts);

        public MainForm()
        {
            InitializeComponent();
            
            // Execute the lifecycle steps
            LoadAllFonts();
            ApplyFontsToControls();

            // Bind the cleanup event to prevent memory corruption/leaks
            this.FormClosed += MainForm_FormClosed;
        }

        /// <summary>
        /// A generic, reusable method to load a font from resources into unmanaged memory.
        /// </summary>
        private Font CreateFontFromResource(byte[] fontResourceData, float fontSize)
        {
            // Allocate unmanaged block of memory matching the font size
            IntPtr fontPtr = Marshal.AllocCoTaskMem(fontResourceData.Length);
            
            // Copy the raw byte array into the allocated unmanaged memory pointer
            Marshal.Copy(fontResourceData, 0, fontPtr, fontResourceData.Length);

            // Register the font with the native OS graphics subsystem (explicitly 1 font package)
            uint numFonts = 1;
            AddFontMemResourceEx(fontPtr, (uint)fontResourceData.Length, IntPtr.Zero, ref numFonts);

            // Append the font to our managed PrivateFontCollection
            _privateFonts.AddMemoryFont(fontPtr, fontResourceData.Length);

            // Save pointer reference for bulk cleanup when the application exits
            _fontPointers.Add(fontPtr);

            // Instantiate the Font object using the most recently added index
            int lastFontIndex = _privateFonts.Families.Length - 1;
            return new Font(_privateFonts.Families[lastFontIndex], fontSize, FontStyle.Regular, GraphicsUnit.Point);
        }

        /// <summary>
        /// PLACEHOLDER A: Load your custom fonts here.
        /// </summary>
        private void LoadAllFonts()
        {
            // Change 'Properties.Resources.YOUR_FONT' to your actual resource name, and adjust the size (e.g., 24, 32)
            _iconFontPrimary = CreateFontFromResource(Properties.Resources.Design_icons, 24);
            _iconFontSecondary = CreateFontFromResource(Properties.Resources.System_icons, 32);
        }

        /// <summary>
        /// PLACEHOLDER B: Bind your fonts and glyphs to your UI controls.
        /// </summary>
        private void ApplyFontsToControls()
        {
            // Example for Primary Font (e.g., Toolbar Buttons)
            button1.Font = _iconFontPrimary;
            button1.Text = "\ue908"; // Replace with your Unicode glyph code

            button2.Font = _iconFontPrimary;
            button2.Text = "\ue937";

            // Example for Secondary Font (e.g., Status Bar Icons)
            button6.Font = _iconFontSecondary;
            button6.Text = "\uf247"; 
        }

        /// <summary>
        /// Clean up allocated resources cleanly upon form closure.
        /// </summary>
        private void MainForm_FormClosed(object sender, FormClosedEventArgs e)
        {
            // Dispose managed font wrappers
            if (_iconFontPrimary != null) _iconFontPrimary.Dispose();
            if (_iconFontSecondary != null) _iconFontSecondary.Dispose();
            if (_privateFonts != null) _privateFonts.Dispose();

            // Release all unmanaged memory buffers at once
            foreach (IntPtr ptr in _fontPointers)
            {
                if (ptr != IntPtr.Zero)
                {
                    Marshal.FreeCoTaskMem(ptr);
                }
            }
            _fontPointers.Clear();
        }
    }
}

```

---

## 🔍 Code Customization Guide | دليل تعديل الكود للمطورين

To adapt this code to your specific project, you only need to modify **two specific places**:

لتطويع هذا الكود ليناسب مشروعك الخاص، تحتاج فقط إلى تعديل **مكانيين محددين**:

### 1️⃣ `LoadAllFonts()` Method: (تعديل الخط والحجم)

Update the resource reference to match your actual `.ttf` file name inside your Resources.
قم بتحديث مرجع المورد ليتطابق مع الاسم الفعلي لملف `.ttf` الموجود ضمن مجلد الموارد (Resources) لديك.

```csharp
// Replace 'Design_icons' with the exact name of your resource file. 
// You can also change the font size value (e.g. 24, 40) right here.
_iconFontPrimary = CreateFontFromResource(Properties.Resources.YOUR_FONT_RESOURCE_NAME, 24);

```

### 2️⃣ `ApplyFontsToControls()` Method: (تغيير الأيقونات بالكود)

Assign the font variable to your specific WinForms controls (Buttons, Labels, Tabs) and input the correct Unicode for the icon you want to render.
قم بتعيين متغير الخط لعناصر تحكم WinForms المحددة (الأزرار، والتسميات، وعلامات التبويب)، وأدخل رمز Unicode الصحيح للأيقونة التي ترغب في عرضها.

```csharp
yourButtonName.Font = _iconFontPrimary; // Set the font target
yourButtonName.Text = "\uXXXX";        // Insert the specific Unicode value (e.g., "\ue908")

```
> [!IMPORTANT]
> ⚠️ **Important Integration Note | ملاحظة هامة جداً قبل استخدام الكود**
>
> **English:**
> Before running the code, make sure to adjust the following names to match your current project structure:
> 1. **Namespace:** Replace `WinForms_IconFont_Demo` with your project's actual namespace.
> 2. **Form Class Name:** Change `MainForm` in the class definition (`public partial class MainForm : Form`) and constructor (`public MainForm()`) to match your Form's actual class name (e.g., `Form1`).
>
> ---
>
> **العربية:**
> قبل البدء ببدء تشغيل أو نسخ الكود، يرجى التأكد من تعديل المسميات التالية لتتطابق مع هيكلية مشروعك:
> 1. **مساحة الأسماء (Namespace):** استبدل `WinForms_IconFont_Demo` بـ Namespace الخاص بمشروعك الحقيقي.
> 2. **اسم الفئة/النافذة (Form Class):** قم بتغيير الاسم `MainForm` في تعريف الفئة (`public partial class MainForm : Form`) وفي المشيد (`public MainForm()`) ليتطابق مع الاسم الفعلي للنافذة لديك (مثل `Form1`).
---

## 🔤 What is Unicode & How to Find Icons | ما هو الـ Unicode وكيف تجد الأيقونات؟

### 💡 What is Unicode? | ما هو الـ Unicode؟

Custom icon fonts do not use standard letters (like 'A', 'B', 'C'). Instead, they map vector icon designs to special placeholders called **Unicode Character Points** (usually looking like `\ue908` or `\uf1ba`). When you assign an icon font to a button and change its text to one of these codes, Windows Forms draws the high-resolution vector symbol instead of text.

أيقونات الخطوط لا تستخدم الأحرف العادية (مثل أ، ب، ج). بدلاً من ذلك، تقوم بربط الأيقونات الشعاعية برموز برمجية خاصة تُسمى **Unicode Character Points** (تظهر عادةً على شكل `\ue908` أو `\uf1ba`). عندما تقوم بتعيين الخط المخصص لزر ما وتكتب هذا الكود في خاصية الـ Text، يقوم النظام برسم الأيقونة بدقة عالية بدلاً من النص العادي.

### 🌐 Finding Icons Using the Repository's HTML Indexes | العثور على الأيقونات باستخدام فهارس HTML الخاصة بالمستودع

To make finding icons effortless, **every font pack included in this repository comes with its own Interactive HTML index file** located in the same directory.

لتسهيل العثور على الأيقونات، **يأتي كل خط في هذا المستودع مصحوباً بملف HTML تفاعلي خاص به** في نفس المجلد.

> 🛠️ **How to use it:**
> 1. Open the `.html` file corresponding to your font in any browser (Chrome, Edge, etc.).
> 2. You will see a clean, visual grid displaying every single icon contained inside that font pack.
> 3. Use the integrated **Search Bar** at the top of the webpage to quickly find specific icons (e.g., searching for "save", "settings", "user").
> 4. Next to the icon, copy the provided Unicode value.
> 5. In your C# code, prefix the code with `\u` (e.g., if the HTML index shows `e908`, paste it into Visual Studio as `"\ue908"`).
> 
> 

> 🛠️ **طريقة الاستخدام:**
> 1. افتح ملف الـ `.html` الخاص بالخط الذي تريده في أي متصفح إنترنت.
> 2. ستظهر لك لوحة تفاعلية تعرض جميع الأيقونات الموجودة داخل هذا الخط بشكل مرئي.
> 3. يمكنك استخدام **شريط البحث** المدمج في أعلى الصفحة للبحث عن أيقونة معينة بالاسم (مثال: ابحث عن "save" أو "home").
> 4. ستجد بجانب كل أيقونة رمز الـ **Unicode** الخاص بها.
> 5. لتبنيها داخل كود C#، قم بإضافة الرمز `\u` قبل الكود (مثال: إذا كان الرمز في صفحة الـ HTML هو `e908`، اكتبه في فيجوال ستوديو بهذا الشكل `"\ue908"`).
> 
> 

---

# 📦 Available Icon Font Packs | حزم خطوط الأيقونات المتوفرة

This repository contains a massive, well-categorized library of custom vector icon fonts. Each pack is meticulously structured to include the font files along with an interactive HTML index for easy search and preview.

يحتوي هذا المستودع على مكتبة ضخمة ومنظمة من خطوط الأيقونات الشعاعية. تم ترتيب كل حزمة لتشمل ملفات الخطوط بالإضافة إلى ملف HTML تفاعلي لتسهيل البحث واستعراض الأيقونات.

---

## 📊 Collection Overview & Statistics | نظرة عامة وإحصائيات الحزم

The collection contains over **9,000+ scalable vector icons** divided into **26 specialized categories** to fit any user interface design required in your desktop software.

تضم المجموعة أكثر من **9,000 أيقونة شعاعية** قابلة للتكبير والتصغير، مقسمة إلى **26 تصنيفاً متخصصاً** لتناسب كافة احتياجات واجهات المستخدم في برامجك.

### 🗂️ Detailed Directory & Icon Counts | تفاصيل المجلدات وأعداد الأيقونات

| # | Package Name (اسم الحزمة) | Total Icons (عدد الأيقونات) | Directory Name (اسم المجلد) |
| --- | --- | --- | --- |
| 1 | **FALCON Icon Collection Pack 1** | 2001 | `FALCON_Icons_Collection_Pack1` |
| 2 | **General Icons Filled Pack 3** | 1053 | `Gereral_Icons_Filled_Pack3` |
| 3 | **FALCON Icon Collection Pack 2** | 699 | `FALCON_Icon_Collection_Pack2` |
| 4 | **Brands Icon Pack 1** | 606 | `Brands_Icons_Pack1` |
| 5 | **General Icons PACK 2** | 562 | `General_Icons_Pack2` |
| 6 | **Brands Icon Pack 2** | 501 | `Brands_Icons_Pack2` |
| 7 | **General Icon Pack 1** | 491 | `General_Icons_Pack1` |
| 8 | **System Icons** | 348 | `System_Icons` |
| 9 | **Logos Icons** | 300 | `Logos_Icons` |
| 10 | **Media Icons** | 296 | `Media_Icons` |
| 11 | **Documents Icons** | 244 | `Documents_Icons` |
| 12 | **Design Icons** | 236 | `Design_Icons` |
| 13 | **Business Icons** | 220 | `Business_Icons` |
| 14 | **Devices Icons** | 192 | `Devices_Icons` |
| 15 | **Arrows Icons** | 178 | `Arrows_Icons` |
| 16 | **Finance Icons** | 172 | `Finance_Icons` |
| 17 | **Map Icons** | 172 | `Map_Icons` |
| 18 | **Editor Icons** | 151 | `Editor_Icons` |
| 19 | **Others Icons** | 116 | `Others_Icons` |
| 20 | **Communications Icons** | 92 | `Communication_Icons` |
| 21 | **Medical Icons** | 84 | `Medical_Icons` |
| 22 | **Weather Icons** | 82 | `Weather_Icons` |
| 23 | **Development Icons** | 66 | `Development_Icons` |
| 24 | **Buildings Icons** | 62 | `Buildings_Icons` |
| 25 | **Users Icons** | 53 | `Users_Icons` |
| 26 | **Game Sport Icons** | 50 | `Game_Sports_Icons` |
| 📐 | **Total Icons Library** | **9,061 Icons** |  |

---

# 📂 Folder Structure & Contents | محتويات وهيكلية المجلدات

Each icon package directory in this repository follows a clean, standardized layout generated by IcoMoon. It provides everything you need from raw font files to interactive preview web pages.

يتبع كل مجلد من مجلدات حزم الأيقونات في هذا المستودع هيكلية موحدة ونظيفة (تم إنشاؤها عبر IcoMoon). توفر هذه الهيكلية كل ما تحتاجه بدءاً من ملفات الخطوط الخام وحتى صفحات الاستعراض التفاعلية.

## 🔍 Directory Breakdown | تفصيل محتويات المجلد

Inside every individual folder, you will find the following assets:

داخل كل مجلد فرعي، ستجد الملفات والعناصر التالية:

### 1. 📂 `fonts/` (Directory / مجلد ملفات)

* **English:** Contains the core scalable font files. The `.ttf` file inside this folder is the one you will import into Visual Studio's `Resources.resx`.
* **العربية:** يحتوي على ملفات الخطوط الأساسية. ملف الـ `.ttf` الموجود داخل هذا المجلد هو الملف الذي ستقوم بتضمينه داخل موارد مشروعك `Resources.resx`.

### 2. 🌐 `[Package_Name].html` (Interactive Document / صفحة ويب تفاعلية)

* **English:** The visual index/cheat-sheet for the specific pack (e.g., `Arrows_Icons.html`). Open this in any browser to search, filter, and copy the precise Unicode points for your C# code.
* **العربية:** الفهرس المرئي المخصص للحزمة (مثل `Arrows_Icons.html`). يمكنك فتحه في أي متصفح للبحث عن الأيقونات، وتصفيتها، ونسخ أكواد الـ Unicode الخاصة بها لاستخدامها في كود C#.

### 3. 📄 `selection.json` (JSON Source File / ملف بيانات المشروع)

* **English:** The metadata configuration file containing the project definition, glyph mappings, and character codes. You can re-import this file back into tools like IcoMoon to edit or expand the font pack later.
* **العربية:** ملف البيانات الوصفية (Metadata) الذي يحتوي على إعدادات المشروع وخريطة الرموز وأكوادها. يمكنك إعادة استيراد هذا الملف في أدوات مثل IcoMoon لتعديل حزمة الخطوط أو توسيعها لاحقاً.

### 4. 🎨 `style.css` (CSS Source File / ملف التنسيق)

* **English:** Contains the CSS rules and class mappings for web projects. While not strictly used in Windows Forms, it serves as a valuable reference for internal font naming conventions.
* **العربية:** يحتوي على قواعد التنسيق وربط الكلاسات المخصصة لمشاريع الويب. بالرغم من عدم استخدامه مباشرة في تطبيقات Windows Forms، إلا أنه يمثل مرجعاً ممتازاً لمعرفة الأسماء البرمجية الداخلية للأيقونات.

### 5. 📂 `demo-files/` (Directory / مجلد ملفات العرض)

* **English:** Internal components and assets required to properly render and style the interactive HTML preview page.
* **العربية:** المكونات والملفات المساعدة المطلوبة لتشغيل وعرض صفحة الـ HTML التفاعلية وتنسيقها بشكل صحيح.

---

## 🤝 Contributing

We welcome contributions of any kind – icon pack suggestions, performance improvements, documentation translation, or bug fixes. Please open an issue to discuss your ideas or submit a pull request directly. All contributions are valued, and kind, constructive communication is our standard.

## 📄 License

This project is licensed under the **MIT License**. See the [LICENSE](https://www.google.com/search?q=LICENSE) file for details. You are free to use, modify, and distribute the code in personal or commercial projects, provided the original copyright notice remains intact.

---

### 🌐 النسخة العربية – المساهمة والترخيص

نرحب بجميع المساهمات – اقتراح حزم أيقونات، تحسين الأداء، ترجمة الوثائق، أو إصلاح الأخطاء. افتح issue لمناقشة أفكارك أو أرسل pull request. المشروع مرخص تحت رخصة **MIT** المشاعة – أنت حر في الاستخدام والتعديل والتوزيع في المشاريع الخاصة والتجارية مع الاحتفاظ بإشعار الحقوق الأصلي.

---
