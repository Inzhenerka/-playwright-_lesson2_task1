##### Урок 2

### Задание 1

В браузере откройте страницу http://uitestingplayground.com/click. Изучите поведение кнопки. После клика, цвет кнопки становится зеленым.  
Ваша задача – дописать тест, который кликает по кнопке и проверяет ее цвет.
1. В папке с тестами создайте файл `lesson2_click.spec.js`
2. Скопируйте в файл код
```javascript
const { test, expect } = require('@playwright/test');

test('click test', async ({ page }) => {
    await page.goto('http://uitestingplayground.com/click');
    
    // >>>>> дополнить код здесь
    await page.locator("#badButton");
    // <<<<<
    
    await expect(await page.locator("#badButton").getAttribute("class")).toMatch(/btn-success/);
  });
```
3. Запустите тест. Изучите текст ошибки. 
> ```
> Error: expect(received).toMatch(expected)
> Expected pattern: /btn-success/
> Received string:  "btn btn-primary"
> ```
5. Допишите строку работы с элементом – вызовите у элемента метод `click()`
6. Запустите тест – тест должен быть "зеленым".
