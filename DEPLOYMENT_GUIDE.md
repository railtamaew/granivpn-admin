# 🚀 Руководство по развертыванию GraniVPN Admin Panel

## 📋 Варианты развертывания

### 1. Netlify (Рекомендуется - Бесплатно)

#### Шаг 1: Подготовка
1. Убедитесь, что у вас установлен Node.js
2. Откройте командную строку (CMD, не PowerShell)
3. Перейдите в папку проекта

#### Шаг 2: Сборка проекта
```bash
cd admin-panel
npm install
npm run build
```

#### Шаг 3: Развертывание на Netlify
1. Зайдите на [netlify.com](https://netlify.com)
2. Нажмите "New site from Git"
3. Подключите ваш GitHub/GitLab/Bitbucket репозиторий
4. Выберите папку `admin-panel`
5. Настройки сборки:
   - Build command: `npm run build`
   - Publish directory: `build`
6. Нажмите "Deploy site"

### 2. Vercel (Альтернатива)

#### Шаг 1: Подготовка
```bash
npm install -g vercel
```

#### Шаг 2: Развертывание
```bash
cd admin-panel
vercel
```

### 3. GitHub Pages

#### Шаг 1: Создание репозитория
1. Создайте репозиторий на GitHub
2. Загрузите код

#### Шаг 2: Настройка GitHub Actions
Создайте файл `.github/workflows/deploy.yml`:

```yaml
name: Deploy to GitHub Pages

on:
  push:
    branches: [ main ]

jobs:
  build-and-deploy:
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@v2
    - uses: actions/setup-node@v2
      with:
        node-version: '18'
    - run: |
        cd admin-panel
        npm install
        npm run build
    - uses: peaceiris/actions-gh-pages@v3
      with:
        github_token: ${{ secrets.GITHUB_TOKEN }}
        publish_dir: ./admin-panel/build
```

## 🔧 Настройка домена

### Netlify
1. В настройках сайта выберите "Domain settings"
2. Нажмите "Add custom domain"
3. Введите ваш домен
4. Настройте DNS записи

### Vercel
1. В настройках проекта выберите "Domains"
2. Добавьте ваш домен
3. Настройте DNS записи

## 📱 Доступ к админ панели

После развертывания вы получите URL вида:
- Netlify: `https://your-site-name.netlify.app`
- Vercel: `https://your-project.vercel.app`

### Вход в систему
- **Email:** любой (например: admin@granivpn.com)
- **Password:** любой (например: admin123)

## 🔄 Обновления

### Автоматические обновления
При каждом push в репозиторий сайт будет автоматически обновляться.

### Ручные обновления
```bash
cd admin-panel
npm run build
# Затем перезапустите деплой
```

## 🛠️ Устранение неполадок

### Ошибка сборки
1. Проверьте версию Node.js (должна быть 16+)
2. Удалите node_modules и package-lock.json
3. Выполните `npm install` заново

### Ошибка 404
1. Убедитесь, что настроены redirects в netlify.toml
2. Проверьте, что папка build создалась

### Проблемы с кодировкой
Используйте CMD вместо PowerShell для команд npm.

## 📞 Поддержка

Если возникли проблемы:
1. Проверьте логи сборки в панели управления
2. Убедитесь, что все зависимости установлены
3. Проверьте версию Node.js

---

**Удачи с развертыванием! 🚀**
