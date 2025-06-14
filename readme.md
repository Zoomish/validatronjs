# Validatronjs

![valodatron-rongo](https://github.com/user-attachments/assets/29bd7dbb-56b1-4981-96a9-062d38f4f4bf)

**Validatronjs** — минималистичный и очень простой валидатор для Node.js без лишнего кода и зависимостей.

## 🚀 Установка

Установите пакет через npm или yarn:

```bash
npm install validatronjs
# или
yarn add validatronjs
```

## ⚡ Быстрый старт

```js
import { IsString, IsNumber, validate, ValidationError } from 'validatronjs';

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
* **@IsBoolean()** — проверяет, что значение свойства является булевым (`true` или `false`).
* **@IsArray()** — проверяет, что значение свойства является массивом.
* **@IsObject()** — проверяет, что значение свойства является объектом.
* **@IsDate()** — проверяет, что значение свойства является датой (`Date`).
* **@IsEmail()** — проверяет, что значение свойства является корректным email.
* **@IsUrl()** — проверяет, что значение свойства является корректным URL.
* **@IsUUID()** — проверяет, что значение свойства является UUID.
* **@IsPhoneNumber()** — проверяет, что значение свойства является телефонным номером.
* **@Length(min, max)** — проверяет, что длина строки находится в диапазоне от `min` до `max`.
* **@Min(min)** — проверяет, что числовое значение не меньше `min`.
* **@Max(max)** — проверяет, что числовое значение не больше `max`.
* **@ValidateIf(condition)** — выполняет валидацию, только если функция `condition` возвращает `true`.
* **@IsIn(values)** — проверяет, что значение содержится в массиве `values`.
* **@IsNotEmpty()** — проверяет, что значение не пустое.
* **@IsNotNull()** — проверяет, что значение не `null`.
* **@IsUpperCase()** — проверяет, что строка состоит из заглавных букв.
* **@IsLowerCase()** — проверяет, что строка состоит из строчных букв.
* **@IsMongoId()** — проверяет, что значение является корректным MongoDB ObjectId.
* **validate(obj)** — запускает валидацию всех декорированных свойств объекта и выбрасывает `ValidationError` при первой обнаруженной ошибке.
* **ValidationError** — представляет ошибку валидации с сообщением формата `"<поле>: <причина>"`.

## 🤝 Contributing

1. Форкните репозиторий.
2. Создайте ветку `feature/your-feature`.
3. Внесите изменения и добавьте тесты.
4. Откройте Pull Request.

## 📄 Лицензия

MIT © [merdernoty](https://github.com/merdernoty)
