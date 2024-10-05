# План автоматизации тестирования

**Цель плана автоматизации** - описание процесса автоматизации тестирования перехода к форме покупки тура по определённой цене двумя способами:

1. Обычная оплата по дебетовой карте.

2. Уникальная технология: выдача кредита по данным банковской карты.



## Предусловия

1. Открыт сайт веб-сервиса.

2. На главной странице нажать кнопку "Купить"

3. Валидный номер активированной карты 4444 4444 4444 4441

4. Валидный номер заблокированной карты 4444 4444 4444 4442



## Перечень автоматизируемых сценариев

### UI Тестирование формы оплаты тура по карте



#### Позитивные сценарии(Валидные значения)

Произвести указаные проверки для вкладки "Купить",затем во вкладке "Купить в кредит".



### 1. Ввод данных в поле "Владелец" на латинице, фамилия и имя состоят из 35 символов:

1. В поле "Номер карты" ввести валидное значение активной карты (см. предусловия);

2. В поле "Месяц" ввести валидные данные;

3. В поле "Год" ввести валидные данные;

4. В поле "Владелец" ввести данные (имя и фамилию) на латинице по 35 символов;

5. В поле "CVC/CVV" ввести валидное значение из трех цифр;

6. Нажать кнопку "Продолжить".



### 2. Отклонение оплаты тура по заблокированной карте:

1. В поле "Номер карты" ввести валидное значение заблокированной карты (см. предусловия);

2. В поле "Месяц" ввести валидные данные;

3. В поле "Год" ввести валидные данные;

4. В поле "Владелец" ввести валидное значение (латиницей имя и фамилию);

5. В поле "CVC/CVV" ввести валидное значение из трех цифр;

6. Нажать кнопку "Продолжить".

**ОР**: Всплывающее окно с сообщением "Ошибка! Банк отказал в проведении операции." В БД есть запись DECLINED



### 3. Ввод данных в поле "Владелец" на латинице, имя через дефис:

1. В поле "Номер карты" ввести валидное значение активной карты (см. предусловия);

2. В поле "Месяц" ввести валидные данные;

3. В поле "Год" ввести валидные данные;

4. В поле "Владелец" ввести данные(имя и фамилию) на латинице + дефис;

5. В поле "CVC/CVV" ввести валидное значение из трех цифр;

6. Нажать кнопку "Продолжить".

**ОР**: Всплывающее окно с сообщением "Успешно! Операция одобрена банком."

### 4. Ввод данных в поле "Владелец" на латинице, фамилия и имя состоят из 2 символов:

1. В поле "Номер карты" ввести валидное значение активной карты (см. предусловия);

2. В поле "Месяц" ввести валидные данные;

3. В поле "Год" ввести валидные данные;

4. В поле "Владелец" ввести данные (имя и фамилию) на латинице по 2 символа;

5. В поле "CVC/CVV" ввести валидное значение из трех цифр;

6. Нажать кнопку "Продолжить".

**ОР**: Всплывающее окно с сообщением "Успешно! Операция одобрена банком."

### 5. Успешная оплата тура по активной карте:

1. В поле "Номер карты" ввести валидное значение активной карты (см. предусловия);

2. В поле "Месяц" ввести валидные данные;

3. В поле "Год" ввести валидные данные;

4. В поле "Владелец" ввести валидное значение (латиницей имя и фамилию).

5. В поле "CVC/CVV" ввести валидное значение из трех цифр;

6. Нажать кнопку "Продолжить".

**ОР**: Всплывающее окно с сообщением "Успешно! Операция одобрена банком." В БД есть запись APPROVED



#### Негативные сценарии(Невалидные значения, граничные значения)

Произвести указаные проверки для вкладки "Купить",затем во вкладке "Купить в кредит".

## Ввод невалидных значений в поле "Номер карты"

### 1. Ввод номера карты состоящим из нулей:

1. В поле "Номер карты" ввести номер карты, содержащий 16 нулей;

2. В поле "Месяц" ввести валидные данные;

3. В поле "Год" ввести валидные данные;

3. В поле "Владелец" ввести валидное значение (латиницей имя и фамилию);

4. В поле "CVC/CVV" ввести валидное значение из трех циф;.

5. Нажать кнопку "Продолжить"

**ОР:** Поле "Номер карты" подсвечивает сообщение: "Неверно указан номер карты"

### 2. Поле номера карты пустое:

1. Поле "Номер карты" оставить пустым;

2. В поле "Месяц" ввести валидные данные;

3. В поле "Год" ввести валидные данные;

3. В поле "Владелец" ввести валидное значение (латиницей имя и фамилию);

4. В поле "CVC/CVV" ввести валидное значение из трех цифр;

5. Нажать кнопку "Продолжить".

**ОР:** Под полем "Номер карты" появляется валидационное сообщение "Поле обязательно для заполнения"

### 3. Ввод номера карты на латинице:

1. В поле "Номер карты" ввести данные на латинице 16 символов;

2. В поле "Месяц" ввести валидные данные;

3. В поле "Год" ввести валидные данные;

4. В поле "Владелец" ввести валидное значение (латиницей имя и фамилию);

5. В поле "CVC/CVV" ввести валидное значение из трех цифр;

6. Нажать кнопку "Продолжить".

**ОР:** Поле "Номер карты" подсвечивает сообщение: "Неверно указан номер карты"

### 4. Ввод номера карты на кирилице:

1. В поле "Номер карты" ввести данные на кирилице 16 символов;

2. В поле "Месяц" ввести валидные данные;

3. В поле "Год" ввести валидные данные;

4. В поле "Владелец" ввести валидное значение (латиницей имя и фамилию);

5. В поле "CVC/CVV" ввести валидное значение из трех цифр;

6. Нажать кнопку "Продолжить".

**ОР:** Поле "Номер карты" подсвечивает сообщение: "Неверно указан номер карты"

### 5. Ввод номера карты специальными символами:

1. В поле "Номер карты" ввести данные спецсимволами 16 символов;

2. В поле "Месяц" ввести валидные данные;

3. В поле "Год" ввести валидные данные;

3. В поле "Владелец" ввести валидное значение (латиницей имя и фамилию);

4. В поле "CVC/CVV" ввести валидное значение из трех цифр;

5. Нажать кнопку "Продолжить".

**ОР:** Поле "Номер карты" подсвечивает сообщение: "Неверно указан номер карты"



## Ввод граничных значений в поле "Номер карты"

### 6. Поле номера карты состоящее больше чем 16 символов:

1. В поле "Номер карты" ввести номер карты больше 16 символов;

2. В поле "Месяц" ввести валидные данные;

3. В поле "Год" ввести валидные данные;

4. В поле "Владелец" ввести валидное значение (латиницей имя и фамилию);

5. В поле "CVC/CVV" ввести валидное значение из трех цифр;

6. Нажать кнопку "Продолжить".

**ОР:** Поле "Номер карты" заполняется до 16 символов

### 7. Поле номера карты состоящее меньше чем 16 символов:

1. В поле "Номер карты" ввести номер карты меньше 16 символов;

2. В поле "Месяц" ввести валидные данные;

3. В поле "Год" ввести валидные данные;

4. В поле "Владелец" ввести валидное значение (латиницей имя и фамилию);

5. В поле "CVC/CVV" ввести валидное значение из трех цифр;

6. Нажать кнопку "Продолжить".

**ОР:** Поле "Номер карты" подсвечивает сообщение: "Неверно указан номер карты, номер карты должен состоять из 16 цифр"



## Ввод невалидных значений в поле "Месяц"

### 8. Поле "Месяц" пустое:

1. В поле "Номер карты" ввести валидное значение активной карты (см. предусловия);

2. Поле "Месяц" оставить пустым;

3. В поле "Год" ввести валидное значение;

4. В поле "Владелец" ввести валидное значение (латиницей имя и фамилию);

5. В поле "CVC/CVV" ввести валидное значение из трех цифр;

6. Нажать кнопку "Продолжить".

**ОР:** Под полем "Месяц" появляется валидационное сообщение "Поле обязательно для заполнения";

### 9. Ввод данных в поле "Месяц" нулевое значение:

1. В поле "Номер карты" ввести валидное значение активной карты (см. предусловия);

2. В поле "Месяц" ввести "00.";

3. В поле "Год" ввести валидное значение;

4. В поле "Владелец" ввести валидное значение (латиницей имя и фамилию);

5. В поле "CVC/CVV" ввести валидное значение из трех цифр;

6. Нажать кнопку "Продолжить".

**ОР:** Поле "Месяц" подсвечивает сообщение: "Неверно указан срок действия карты"

### 10. Поле "Месяц" с истёкшим сроком действия карты ,пример карта действительна до 05 месяца,а  покупка тура 12 месяца:

1. В поле "Номер карты" ввести валидное значение активной карты (см. предусловия);

2. В поле "Месяц" ввести невалидное значение (05);

3. В поле "Год" ввести валидное значение;

4. В поле "Владелец" ввести валидное значение (латиницей имя и фамилию);

5. В поле "CVC/CVV" ввести валидное значение из трех цифр;

6. Нажать кнопку "Продолжить".

**ОР:** Поле "Месяц" подсвечивает сообщение: "Неверно указан срок действия карты"

### 11. Ввод данных в поле "Месяц" 13 месяца:

1. В поле "Номер карты" ввести валидное значение активной карты (см. предусловия);

2. В поле "Месяц" ввести "13.";

3. В поле "Год" ввести валидное значение;

4. В поле "Владелец" ввести валидное значение (латиницей имя и фамилию);

5. В поле "CVC/CVV" ввести валидное значение из трех цифр;

6. Нажать кнопку "Продолжить".

**ОР:** Поле "Месяц" подсвечивает сообщение: "Неверно указан срок действия карты"

### 12. Ввод данных в поле "Месяц" спец символами:

1. В поле "Номер карты" ввести валидное значение активной карты (см. предусловия);

2. В поле "Месяц" ввести данные спец символами;

3. В поле "Год" ввести валидное значение;

4. В поле "Владелец" ввести валидное значение (латиницей имя и фамилию);

5. В поле "CVC/CVV" ввести валидное значение из трех цифр;

6. Нажать кнопку "Продолжить".

**ОР:** Поле "Месяц" не заполняется



## Ввод невалидных значений в поле "Год"

### 13. Ввод данных в поле "Год" c нулевым значением:

1. В поле "Номер карты" ввести валидное значение активной карты (см. предусловия);

2. В поле "Месяц" ввести валидное значение;

3. В поле "Год" ввести данные "00";

4. В поле "Владелец" ввести валидное значение (латиницей имя и фамилию);

5. В поле "CVC/CVV" ввести валидное значение из трех цифр;

6. Нажать кнопку "Продолжить".

**ОР:** Поле "Год" подсвечивает сообщение: "Неверно указан срок действия карты"

### 14. Ввод данных в поле "Год" спец символами:

1. В поле "Номер карты" ввести валидное значение активной карты (см. предусловия);

2. В поле "Месяц" ввести валидное значение;

3. В поле "Год" ввести данные спец символами;

4. В поле "Владелец" ввести валидное значение (латиницей имя и фамилию);

5. В поле "CVC/CVV" ввести валидное значение из трех цифр;

6. Нажать кнопку "Продолжить".

**ОР:** Поле "Год" не заполняется

### 15. Поле "Год" оставить поле пустым:

1. В поле "Номер карты" ввести валидное значение активной карты (см. предусловия);

2. В поле "Месяц" ввести валидное значение;

3. Поле "Год" оставить пустым;

4. В поле "Владелец" ввести валидное значение (латиницей имя и фамилию);

5. В поле "CVC/CVV" ввести валидное значение из трех цифр;

6. Нажать кнопку "Продолжить".

**ОР:** Под полем "Год" появляется валидационное сообщение "Поле обязательно для заполнения";

### 16. Поле "Год" с истёкшим сроком действия карты,пример карта действительна до 2023 года,а покупка тура в 2024 году:

1. В поле "Номер карты" ввести валидное значение активной карты (см. предусловия);

2. В поле "Месяц" ввести валидное значение;

3. В поле "Год" ввести невалидное значение (23).

4. В поле "Владелец" ввести валидное значение (латиницей имя и фамилию);

5. В поле "CVC/CVV" ввести валидное значение из трех цифр;

6. Нажать кнопку "Продолжить".

**ОР:** Поле "Год" подсвечивает сообщение: "Неверно указан срок действия карты"



## Ввод невалидных значений в поле "Владелец"

### 17. Поле "Владелец" поле пустое:

1. В поле "Номер карты" ввести валидное значение активной карты (см. предусловия);

2. В поле "Месяц" ввести валидные данные;

3. В поле "Год" ввести валидное значение;

4. В Поле "Владелец" оставить пустым;

5. В поле "CVC/CVV" ввести валидное значение из трех цифр;

6. Нажать кнопку "Продолжить".

**ОР:** Под полем "Владелец" появляется валидационное сообщение "Поле обязательно для заполне

### 18. Ввод данных в поле "Владелец" на латинице, без фамилии:

1. В поле "Номер карты" ввести валидное значение активной карты (см. предусловия);

2. В поле "Месяц" ввести валидные данные;

3. В поле "Год" ввести валидное значение;

4. В поле "Владелец" ввести только имя на латинице без фамилии (Ivan);

5. В поле "CVC/CVV" ввести валидное значение из трех цифр;

6. Нажать кнопку "Продолжить".

**ОР:** Под полем "Владелец" появляется валидационное сообщение "Поле обязательно для заполнения";

### 19. Ввод данных в поле "Владелец" на кирилице:

1. В поле "Номер карты" ввести валидное значение активной карты (см. предусловия);

2. В поле "Месяц" ввести валидные данные;

3. В поле "Год" ввести валидное значение;

4. В поле "Владелец" ввести имя, фамилию на кирилице;

5. В поле "CVC/CVV" ввести валидное значение из трех цифр;

6. Нажать кнопку "Продолжить".

**ОР:** Поле "Владелец" подсвечивает сообщение: "Поле заполняется латиницей"

### 20. Ввод данных в поле "Владелец", фамилию на латинице,а имя на кирилице:

1. В поле "Номер карты" ввести валидное значение активной карты (см. предусловия);

2. В поле "Месяц" ввести валидные данные;

3. В поле "Год" ввести валидное значение;

4. В поле "Владелец" ввести только фамилию на латинице а имя на кирилице;

5. В поле "CVC/CVV" ввести валидное значение из трех цифр;

6. Нажать кнопку "Продолжить".

**ОР:** Поле "Владелец" подсвечивает сообщение: "Поле заполняется латиницей

### 21. Ввод данных в поле "Владелец" спец симвалами:

1. В поле "Номер карты" ввести валидное значение активной карты (см. предусловия);

2. В поле "Месяц" ввести валидные данные;

3. В поле "Год" ввести валидное значение;

4. В поле "Владелец" ввести имя, фамилию спец символама;

5. В поле "CVC/CVV" ввести валидное значение из трех цифр;

6. Нажать кнопку "Продолжить".

**ОР:** Поле "Владелец" подсвечивает сообщение: "Поле заполняется латиницей"

### 22. Ввод данных в поле "Владелец" на латинице, имя с пробелом:

1. В поле "Номер карты" ввести валидное значение активной карты (см. предусловия);

2. В поле "Месяц" ввести валидные данные;

3. В поле "Год" ввести валидное значение;

4. В поле "Владелец" ввести данные(имя и фамилию) на латинице + пробел;

5. В поле "CVC/CVV" ввести валидное значение из трех цифр;

6. Нажать кнопку "Продолжить".

**ОР:** Поле "Владелец" подсвечивает сообщение: "Значения поля указывается без пробелов"

### 23. Ввод данных в поле "Владелец", фамилию на кирилице,а имя на латинице:

1. В поле "Номер карты" ввести валидное значение активной карты (см. предусловия);

2. В поле "Месяц" ввести валидные данные;

3. В поле "Год" ввести валидное значение;

4. В поле "Владелец" ввести только имя на латинице а фамилию на кирилице;

5. В поле "CVC/CVV" ввести валидное значение из трех цифр;

6. Нажать кнопку "Продолжить".

**ОР:** Поле "Владелец" подсвечивает сообщение: "Поле заполняется латиницей"

### 24. Ввод данных в поле "Владелец" на кирилице с цифрами:

1. В поле "Номер карты" ввести валидное значение активной карты (см. предусловия);

2. В поле "Месяц" ввести валидные данные;

3. В поле "Год" ввести валидное значение;

4. В поле "Владелец" ввести имя, фамилию на кирилице + цифры;

5. В поле "CVC/CVV" ввести валидное значение из трех цифр;

6. Нажать кнопку "Продолжить".

**ОР:** Поле "Владелец" подсвечивает сообщение: "Поле заполняется латиницей"



## Ввод невалидных значений в поле "CVC/CVV"

### 25. Поле "CVC/CVV" оставить поле пустым:

1. В поле "Номер карты" ввести валидное значение активной карты (см. предусловия);

2. В поле "Месяц" ввести валидные данные;

3. В поле "Год" ввести валидное значение;

4. В поле "Владелец" ввести валидное значение (латиницей имя и фамилию);

5. Поле "CVC/CVV" оставить пустым;

6. Нажать кнопку "Продолжить".

**ОР:** Под полем "CVC/CVV" появляется валидационное сообщение "Поле обязательно для заполнения"

### 26. Ввод данных в поле "CVC/CVV" нылевые значения:

1. В поле "Номер карты" ввести валидное значение активной карты (см. предусловия);

2. В поле "Месяц" ввести валидные данные;

3. В поле "Год" ввести валидное значение;

4. В поле "Владелец" ввести валидное значение (латиницей имя и фамилию);

5. В поле "CVC/CVV" ввести "000";

6. Нажать кнопку "Продолжить".

**ОР:** Под полем "CVC/CVV" появляется валидационное сообщение "Неверно указан cvc/cvv код"

### 27 Ввод данных в поле "CVC/CVV" на кирилице:

1. В поле "Номер карты" ввести валидное значение активной карты (см. предусловия);

2. В поле "Месяц" ввести валидные данные;

3. В поле "Год" ввести валидное значение;

4. В поле "Владелец" ввести валидное значение (латиницей имя и фамилию);

5. В поле "CVC/CVV" ввести данные на кирилице;

6. Нажать кнопку "Продолжить".

**ОР:** Под полем "CVC/CVV" появляется валидационное сообщение "Неверно указан cvc/cvv код"

### 28. Ввод данных в поле "CVC/CVV" на латинице:

1. В поле "Номер карты" ввести валидное значение активной карты (см. предусловия);

2. В поле "Месяц" ввести валидные данные;

3. В поле "Год" ввести валидное значение;

4. В поле "Владелец" ввести валидное значение (латиницей имя и фамилию);

5. В поле "CVC/CVV" ввести данные на латинице;

6. Нажать кнопку "Продолжить".

**ОР:** Под полем "CVC/CVV" появляется валидационное сообщение "Неверно указан cvc/cvv код";

### 29. Ввод данных в поле "CVC/CVV" спец символами:

1. В поле "Номер карты" ввести валидное значение активной карты (см. предусловия);

2. В поле "Месяц" ввести валидные данные;

3. В поле "Год" ввести валидное значение;

4. В поле "Владелец" ввести валидное значение (латиницей имя и фамилию);

5. В поле "CVC/CVV" ввести данные спец символами;

6. Нажать кнопку "Продолжить".

**ОР:** Под полем "CVC/CVV" появляется валидационное сообщение "Неверно указан cvc/cvv код"



## Ввод граничных значений в поле "CVC/CVV"

### 30. Ввод данных в поле "CVC/CVV" больше 3-х цифр:

1. В поле "Номер карты" ввести валидное значение активной карты (см. предусловия);

2. В поле "Месяц" ввести валидные данные;

3. В поле "Год" ввести валидное значение;

4. В поле "Владелец" ввести валидное значение (латиницей имя и фамилию);

5. В поле "CVC/CVV" ввести больше 3 цифр;

6. Нажать кнопку "Продолжить".

**ОР:** Под полем "CVC/CVV" появляется валидационное сообщение "Неверно указан cvc/cvv код".

### 31. Ввод данных в поле "CVC/CVV" меньше 3-х цифр:

1. В поле "Номер карты" ввести валидное значение активной карты (см. предусловия);

2. В поле "Месяц" ввести валидные данные;

3. В поле "Год" ввести валидное значение;

4. В поле "Владелец" ввести валидное значение (латиницей имя и фамилию);

5. В поле "CVC/CVV" ввести меньше 3 цифр;

6. Нажать кнопку "Продолжить".

**ОР:** Под полем "CVC/CVV" появляется валидационное сообщение "Неверно указан cvc/cvv код";



## 2.Перечень используемых инструментов с обоснованием выбора:

* IDEA-интегрированная среда разработки программного обеспечения;

* Java 11-язык программирования общего назначения;

* JUnit 5-платформа модульного тестирования в экосистеме Java;

* Gradle - система автоматической сборки и управления зависимостями;

* Selenide-фреймворк для автоматизированного тестирования веб-приложений;

* JavaFaker -библиотека, которая позволяет генерировать случайные данные;

* GitHub - крупнейший веб-сервис для хостинга IT-проектов и их совместной разработки, основанный на системе контроля Git;

* MySql/PostgresSql - Заявлена поддержка данных СУБД;

* Allure - фреймворк для сбора данных и построения отчетов о тестировании кода;

* Lombok - плагин компилятора;

* Docker - это платформа для разработки и запуска контейнеров.



## 3. Перечень рисков:

*  Ошибки в коде автоматизации- плохо написанный код или неправильная последовательность

*  Ошибки в настройке фреймворков

*  Ошибки в настройках БД





## 4. Интервальная оценка с учетом рисков в часах:

* Написание автотестов - 48 часов;

* Настройка, запуск БД и фреймворка - 12 часов

* Формирование отчета о проделанной работе - 15 часов

 