# Validatron
![Uploading ChatGPT Image May 19 2025.png…]()

**Validatron** — минималистичный и очень простой валидатор для Node.js без лишнего кода и зависимостей.

## 🚀 Установка

Установите пакет через npm или yarn:

```bash
npm install validatron
# или
yarn add validatron
```

## ⚡ Быстрый старт

```js
import { IsString, IsNumber, validate, ValidationError } from 'validatron';

class User {
  @IsString()
  username;

  @IsNumber()
  age;
}

const user = new User();
user.username = 'Ivan';
user.age = 30;

try {
  validate(user);
  console.log('Данные корректны!');
} catch (err) {
  if (err instanceof ValidationError) {
    console.error('Ошибка валидации:', err.message);
  }
}
```

## 📋 API

* **@IsString()** — проверяет, что значение свойства является строкой.
* **@IsNumber()** — проверяет, что значение свойства является числом.
* **validate(obj)** — запускает валидацию всех декорированных свойств объекта и выбрасывает `ValidationError` при первой обнаруженной ошибке.
* **ValidationError** — представляет ошибку валидации с сообщением формата `"<поле>: <причина>"`.

## 🤝 Contributing

1. Форкните репозиторий.
2. Создайте ветку `feature/your-feature`.
3. Внесите изменения и добавьте тесты.
4. Откройте Pull Request.

## 📄 Лицензия

MIT © merdernoty
