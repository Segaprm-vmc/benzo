# Настройка аналитики для сайта benzo.ru

## Google Analytics 4 (GA4)

### Установка
1. Перейдите на https://analytics.google.com/
2. Создайте новое свойство для benzo.ru
3. Получите код отслеживания (G-XXXXXXXXXX)
4. Вставьте код в `index.html` перед закрывающим тегом `</head>`:

```html
<!-- Google Analytics -->
<script async src="https://www.googletagmanager.com/gtag/js?id=G-XXXXXXXXXX"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'G-XXXXXXXXXX');
</script>
```

## Яндекс.Метрика

### Установка
1. Перейдите на https://metrica.yandex.ru/
2. Создайте новый счетчик для benzo.ru
3. Получите код счетчика
4. Вставьте код в `index.html` перед закрывающим тегом `</body>`:

```html
<!-- Яндекс.Метрика -->
<script type="text/javascript" >
   (function(m,e,t,r,i,k,a){m[i]=m[i]||function(){(m[i].a=m[i].a||[]).push(arguments)};
   m[i].l=1*new Date();k=e.createElement(t),a=e.getElementsByTagName(t)[0],k.async=1,k.src=r,a.parentNode.insertBefore(k,a)})
   (window, document, "script", "https://mc.yandex.ru/metrika/tag.js", "ym");

   ym(XXXXXXXX, "init", {
        clickmap:true,
        trackLinks:true,
        accurateTrackBounce:true,
        webvisor:true
   });
</script>
<noscript><div><img src="https://mc.yandex.ru/watch/XXXXXXXX" style="position:absolute; left:-9999px;" alt="" /></div></noscript>
```

## Отслеживание событий

### Клики по кнопкам
Для отслеживания кликов добавьте атрибуты `onclick` к кнопкам:

```html
<!-- Для Google Analytics -->
onclick="gtag('event', 'click', {'event_category': 'button', 'event_label': 'vmc_main_site'});"

<!-- Для Яндекс.Метрики -->
onclick="ym(XXXXXXXX, 'reachGoal', 'vmc_main_site');"
```

### Настройка целей
1. **Google Analytics**: Настройте конверсии в разделе "Конверсии"
2. **Яндекс.Метрика**: Создайте цели в разделе "Настройки" → "Цели"

## Рекомендуемые события для отслеживания

1. **Переход на vmcmoto.ru** - основная цель
2. **Переход на каталоги** - просмотр продукции
3. **Переход в B2B** - партнерские интересы
4. **Клики по соцсетям** - социальная активность
5. **Время на сайте** - качество контента

## Проверка работы

После установки:
1. Проверьте в Google Analytics в разделе "Отчеты в реальном времени"
2. Проверьте в Яндекс.Метрике в разделе "Сводка"
3. Используйте браузерные расширения для проверки счетчиков

## Важные замечания

- Замените `G-XXXXXXXXXX` на ваш реальный ID Google Analytics
- Замените `XXXXXXXX` на ваш реальный номер счетчика Яндекс.Метрики
- Убедитесь что код аналитики не конфликтует с политикой конфиденциальности
- Рассмотрите возможность добавления уведомления о cookies 