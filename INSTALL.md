# تعليمات رفع المشروع على GitHub

## الخطوات

### 1. إنشاء مستودع على GitHub
1. اذهب إلى [GitHub](https://github.com)
2. اضغط على "New repository"
3. اختر اسماً للمستودع (مثلاً: `student-attendance-system`)
4. اختر Public أو Private
5. **لا تختر** "Initialize with README"
6. اضغط "Create repository"

### 2. ربط المشروع المحلي مع GitHub
افتح PowerShell في مجلد المشروع وقم بتنفيذ:

```bash
git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPO_NAME.git
git branch -M main
git push -u origin main
```

استبدل:
- `YOUR_USERNAME` باسم المستخدم في GitHub
- `YOUR_REPO_NAME` باسم المستودع الذي أنشأته

### 3. التحقق
اذهب إلى صفحة المستودع على GitHub وتأكد من ظهور جميع الملفات.

## النشر التلقائي على Render/Railway

بعد رفع المشروع على GitHub:

### Render
1. سجل على [render.com](https://render.com)
2. New > Web Service
3. اختر مستودعك من GitHub
4. Build Command: `pip install -r requirements.txt`
5. Start Command: `gunicorn run:app --bind 0.0.0.0:$PORT`
6. اضغط Deploy

### Railway
1. سجل على [railway.app](https://railway.app)
2. New Project > Deploy from GitHub repo
3. اختر مستودعك
4. Start Command: `gunicorn run:app`
5. Railway ينشر تلقائياً

## ملاحظات
- `.gitignore` يحمي الملفات الحساسة والبيانات
- `attendance.db` لن يُرفع (كما يجب)
- تأكد من وجود جميع الملفات المطلوبة قبل الرفع

