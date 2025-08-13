# GraniVPN - VPN-сервис

Коммерческий VPN-сервис с собственной серверной частью, панелью администратора и кроссплатформенным клиентским приложением.

## Архитектура проекта

```
granivpn/
├── backend/                 # Серверная часть (FastAPI)
│   ├── api/                # API endpoints
│   ├── core/               # Основная логика
│   ├── models/             # Модели данных
│   ├── services/           # Бизнес-логика
│   └── utils/              # Утилиты
├── admin-panel/            # Панель администратора (React)
│   ├── src/
│   │   ├── components/     # React компоненты
│   │   ├── pages/          # Страницы
│   │   ├── services/       # API сервисы
│   │   └── utils/          # Утилиты
│   └── public/             # Статические файлы
├── mobile-app/             # Мобильное приложение (Flutter)
│   ├── lib/
│   │   ├── screens/        # Экраны приложения
│   │   ├── services/       # Сервисы
│   │   ├── models/         # Модели данных
│   │   └── utils/          # Утилиты
│   └── assets/             # Ресурсы
├── server-config/          # Конфигурация серверов
│   ├── wireguard/          # WireGuard конфигурации
│   ├── nginx/              # Nginx конфигурации
│   └── docker/             # Docker файлы
└── docs/                   # Документация
```

## Технологический стек

### Backend
- **FastAPI** - веб-фреймворк
- **PostgreSQL** - база данных
- **Redis** - кэширование и сессии
- **WireGuard** - VPN протокол
- **JWT** - аутентификация

### Admin Panel
- **React** - фронтенд фреймворк
- **TypeScript** - типизация
- **Material-UI** - UI компоненты
- **Redux Toolkit** - управление состоянием

### Mobile App
- **Flutter** - кроссплатформенная разработка
- **Dart** - язык программирования
- **Provider** - управление состоянием

## Основные функции

### Мобильное приложение
- Подключение/отключение VPN
- Регистрация/авторизация по email
- Ограничение на 2 устройства
- Выбор сервера
- Таймер подключения
- Push-уведомления
- Оплата российскими картами
- Split tunneling

### Панель администратора
- Управление пользователями
- Мониторинг серверов
- Управление тарифами
- Просмотр платежей
- Интеграция с AmoCRM
- Логи и статистика

### Серверная часть
- WireGuard VPN сервер
- REST API
- Ограничение скорости
- Логирование подключений
- Автоматическая деактивация

## Быстрый старт

### Требования
- Python 3.8+
- Node.js 16+
- Flutter 3.0+
- Docker
- PostgreSQL
- Redis

### Установка

1. **Backend**
```bash
cd backend
pip install -r requirements.txt
python main.py
```

2. **Admin Panel**
```bash
cd admin-panel
npm install
npm start
```

3. **Mobile App**
```bash
cd mobile-app
flutter pub get
flutter run
```

## Конфигурация

### Сервер
- IP: 94.131.107.227
- OS: Ubuntu 20.04
- WireGuard: /etc/wireguard/wg0.conf
- API: http://45.89.111.135:8000

### Платежные системы
- CloudPayments
- ЮKassa
- PayAnyWay

### CRM
- AmoCRM интеграция

## Лицензия

MIT License
