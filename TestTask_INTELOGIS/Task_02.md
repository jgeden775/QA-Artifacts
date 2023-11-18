# Тестирование сайта: http://u920152e.beget.tech/#

## Чек-лист:
* Форма авторизации
1. Заполнение логина и пароля (корректные значения).
2. Заполнение логина и пароля (некорректные значения).
3. После нажатия на кнопку "Войти" происходит переход к следующей странице, при корректном сценарии.
4. После нажатия на кнопку "Войти" выводится сообщение об ошибке при некорректном сценарии.
5. Поля передаются в запросе.
6. Проверка валидации полей.
* Список возрастных диапазонов
1. Проверка перехода, при выборе пункта "младше 18"
2. Проверка перехода, при выборе пункта "от 18 до 24"
3. Проверка перехода, при выборе пункта "от 25 до 35"
4. Проверка перехода, при выборе пункта "более 35"
* Страница с текстовой информацией
1. Проверка орфографии
***
## Пример тест-кейсов:
(в данном случае взята проверка поля ввода e-mail)
<table border="1">
<tr>
<th>№</th>
<th>Проверка</th>
<th>Ожидаемый результат</th>
</tr>
<tr>
<td>01</td>
<td>Пустое поле "Введите Ваш имейл"</td>
<td>Сообщение о незаполненном поле email</td>
</tr>
<tr>
<td>02</td>
<td>Email без символа "@"</td>
<td>Сообщение о незаполненном поле email</td>
</tr>
<tr>
<td>03</td>
<td>Email c недопустимым символом "("</td>
<td>Сообщение о незаполненном поле email</td>
</tr>
<tr>
<td>04</td>
<td>Пустое поле "Введите Ваш пароль"</td>
<td>Сообщение о незаполненном поле для пароля</td>
</tr>
<tr>
<td>05</td>
<td>Поле "Введите Ваш пароль" заполнено кириллицей</td>
<td>Переход на следующую страницу</td>
</tr>
<tr>
<td>06</td>
<td>Email и пароль введены корректно</td>
<td>Переход на следующую страницу</td>
</tr>
<tr>
<td>07</td>
<td>Выбран пункт "младше 18"</td>
<td>Переход на следующую страницу</td>
</tr>
<tr>
<td>08</td>
<td>Выбран пункт "от 25 до 35"</td>
<td>Переход на следующую страницу</td>
</tr>
</table>

***
## Selenium+Java код для проверки тест-кейса № 06:

```
public class LoginUsingSelenium {
    public static void main(String[] args) {
        System.setProperty("webdriver.chrome.driver", " path of driver "); 
        WebDriver driver=new ChromeDriver(); driver.manage().window().maximize(); 
        driver.get("http://u920152e.beget.tech/#");

        WebElement email=driver.findElement(By.id("email"));
        WebElement password=driver.findElement(By.id("password"));
        WebElement auth=driver
            .findElement(By.xpath("//form_auth_button[text()='Войти']"));
        email.sendKeys("test@mail.me");
        password.sendKeys("123456p");

        login.click(); 
        String actualUrl="http://u920152e.beget.tech/page1.html?auth_email=test%40mail.me&auth_pass=123456p&form_auth_submit="; 
        String expectedUrl= driver.getCurrentUrl();

        if(actualUrl.equalsIgnoreCase(expectedUrl)) { 
        System.out.println("Test passed");
        } 
        else {
        System.out.println("Test failed");
        }
    }   
}
