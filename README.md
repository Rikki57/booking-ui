# Event Booking Frontend

Фронтенд для системы бронирования мероприятий, разработанный на React с TypeScript.

## Описание проекта

Система позволяет:
- Регистрироваться и входить в систему
- Просматривать список мероприятий с пагинацией
- Бронировать билеты на мероприятия
- Управлять своими бронированиями
- Настраивать уведомления
- Администраторам: управлять мероприятиями и бронированиями

## Технологический стек

- **React 18** с TypeScript
- **React Router** для навигации
- **React Hook Form** с Yup для валидации форм
- **Axios** для HTTP-запросов
- **Tailwind CSS** для стилизации
- **Lucide React** для иконок
- **React Hot Toast** для уведомлений

## Быстрый старт

### Предварительные требования

- Node.js 16+ 
- npm или yarn

### Установка зависимостей

```bash
npm install
```

## Запуск проекта

### 1. Запуск с моками (демонстрация)

По умолчанию проект запускается с моками для демонстрации функциональности:

```bash
npm start
```

Приложение будет доступно по адресу: http://localhost:3000

#### Тестовые аккаунты для демонстрации:

**Обычный пользователь:**
- Email: `user@example.com`
- Пароль: `password123`

**Администратор:**
- Email: `admin@example.com`
- Пароль: `password123`

### 2. Запуск с реальным бэкендом

Для подключения к реальному бэкенду создайте файл `.env` в корне проекта:

```env
REACT_APP_API_URL=http://localhost:8080
REACT_APP_USE_MOCKS=false
```

Затем запустите приложение:

```bash
npm start
```

## Инструкции по запуску для разных ОС

### Windows

1. **Установка Node.js:**
   - Скачайте Node.js с официального сайта: https://nodejs.org/
   - Установите, следуя инструкциям установщика
   - Проверьте установку: `node --version` и `npm --version`

2. **Клонирование и запуск:**
   ```cmd
   git clone <repository-url>
   cd event-booking-frontend
   npm install
   npm start
   ```

3. **Возможные проблемы:**
   - Если возникают ошибки с правами доступа, запустите командную строку от имени администратора
   - При проблемах с npm кэшем: `npm cache clean --force`

### macOS

1. **Установка Node.js:**
   - Рекомендуется использовать Homebrew:
     ```bash
     brew install node
     ```
   - Или скачайте с официального сайта: https://nodejs.org/

2. **Клонирование и запуск:**
   ```bash
   git clone <repository-url>
   cd event-booking-frontend
   npm install
   npm start
   ```

3. **Возможные проблемы:**
   - При проблемах с правами доступа: `sudo npm install`
   - Если порт 3000 занят, npm автоматически предложит другой порт

## Структура проекта

```
src/
├── components/          # React компоненты
│   ├── AuthForm.tsx     # Форма аутентификации
│   ├── Navigation.tsx   # Навигация
│   ├── EventList.tsx    # Список мероприятий
│   ├── EventDetail.tsx  # Детали мероприятия
│   ├── BookingList.tsx  # Список бронирований
│   ├── AdminBookingList.tsx # Админ: управление бронированиями
│   └── NotificationSettings.tsx # Настройки уведомлений
├── contexts/            # React контексты
│   └── AuthContext.tsx  # Контекст аутентификации
├── services/            # API сервисы
│   ├── api.ts          # Основной API сервис
│   └── mockApi.ts      # Моки для демонстрации
├── types/               # TypeScript типы
│   └── index.ts        # Определения типов
├── App.tsx             # Главный компонент
└── index.tsx           # Точка входа
```

## API Endpoints

### Аутентификация
- `POST /auth/login` - Вход в систему
- `POST /auth/register` - Регистрация

### Мероприятия
- `GET /events` - Список мероприятий
- `GET /events/{id}` - Детали мероприятия
- `POST /admin/events` - Создание мероприятия (Admin)
- `PUT /admin/events/{id}` - Обновление мероприятия (Admin)
- `DELETE /admin/events/{id}` - Удаление мероприятия (Admin)

### Бронирования
- `GET /bookings` - Мои бронирования
- `POST /bookings` - Создание бронирования
- `DELETE /bookings/{id}` - Отмена бронирования
- `GET /admin/bookings` - Все бронирования (Admin)
- `PUT /admin/bookings/{id}/confirm` - Подтверждение бронирования (Admin)
- `DELETE /admin/bookings/{id}` - Удаление бронирования (Admin)

### Уведомления
- `GET /user/notifications` - Настройки уведомлений
- `PUT /user/notifications` - Обновление настроек
- `DELETE /user/notifications` - Сброс настроек
- `POST /user/telegram/link` - Привязка Telegram

## Переменные окружения

| Переменная | Описание | По умолчанию |
|------------|----------|--------------|
| `REACT_APP_API_URL` | URL бэкенда | `http://localhost:8080` |
| `REACT_APP_USE_MOCKS` | Использовать моки | `true` (если API_URL не задан) |

## Сборка для продакшена

```bash
npm run build
```

Собранные файлы будут в папке `build/`.

## Тестирование

```bash
npm test
```

## Дополнительные команды

- `npm run eject` - Извлечение конфигурации (необратимо)
- `npm run build` - Сборка для продакшена
- `npm run test` - Запуск тестов
- `npm run test:coverage` - Тесты с покрытием

## Особенности демонстрационного режима

При запуске с моками:
- Все данные хранятся в памяти браузера
- При перезагрузке страницы данные сбрасываются
- Имитируются задержки API для реалистичности
- Доступны предустановленные тестовые аккаунты

## Поддержка

При возникновении проблем:
1. Проверьте версию Node.js (должна быть 16+)
2. Удалите `node_modules` и `package-lock.json`, затем выполните `npm install`
3. Очистите кэш npm: `npm cache clean --force`
4. Убедитесь, что порт 3000 свободен

## Лицензия

MIT
