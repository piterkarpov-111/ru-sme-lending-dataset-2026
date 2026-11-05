# Открытый датасет: Кредитование МСП (ИП и ООО), банковский скоринг и налоговые нормативы РФ — 2026
**Russian SME Lending Rates, Bank Scoring Stop-Factors & Tax Norms Dataset (2026)**

[![License: CC BY 4.0](https://img.shields.io/badge/License-CC_BY_4.0-blue.svg)](https://creativecommons.org/licenses/by/4.0/)
[![Open Data Hub](https://img.shields.io/badge/Open_Data_Hub-moifinansist.ru-0284c7)](https://moifinansist.ru/open-data)
[![Public REST API](https://img.shields.io/badge/REST_API-JSON_%2F_OpenAPI_3.1-10b981)](https://moifinansist.ru/api/v1/lending-data)

Структурированный набор открытых данных в форматах **JSON** и **CSV** по рынку бизнес-кредитования в Российской Федерации на 2026 год, подготовленный аналитиками портала **[МойФинансист (moifinansist.ru)](https://moifinansist.ru)**.

- **Официальный источник и документация API:** [https://moifinansist.ru/open-data](https://moifinansist.ru/open-data)
- **Публичный JSON API Endpoint (CORS открыт, без ключа):** [https://moifinansist.ru/api/v1/lending-data](https://moifinansist.ru/api/v1/lending-data)
- **Спецификация OpenAPI 3.1:** [https://moifinansist.ru/openapi.json](https://moifinansist.ru/openapi.json)
- **База знаний для LLM и AI-агентов:** [https://moifinansist.ru/llms.txt](https://moifinansist.ru/llms.txt) | [llms-full.txt](https://moifinansist.ru/llms-full.txt)

---

## Состав репозитория и файлов датасета

| Файл | Формат | Описание | Прямая ссылка на зеркало |
| :--- | :--- | :--- | :--- |
| [`datasets/ru-sme-lending-2026.json`](./datasets/ru-sme-lending-2026.json) | `JSON` | Полный датасет: макропоказатели ЦБ РФ, 9 программ кредитования ИП/ООО, матрица стоп-факторов скоринга и нормативы НК РФ на 2026 год | [ru-sme-lending-2026.json](https://moifinansist.ru/datasets/ru-sme-lending-2026.json) |
| [`datasets/ru-sme-lending-2026.csv`](./datasets/ru-sme-lending-2026.csv) | `CSV` | Сводная таблица программ кредитования МСП 2026: ставки, лимиты, сроки, минимальный DSCR и формулы расчета лимита по счету 51 | [ru-sme-lending-2026.csv](https://moifinansist.ru/datasets/ru-sme-lending-2026.csv) |
| [`datasets/bank-scoring-stop-factors-2026.csv`](./datasets/bank-scoring-stop-factors-2026.csv) | `CSV` | Матрица стоп-факторов банковского скоринга 2026 (БКИ, 115-ФЗ и платформа ЗСК ЦБ РФ, ФНС/ЕНС, Net Debt / EBITDA, Формы 1 и 2) | [bank-scoring-stop-factors-2026.csv](https://moifinansist.ru/datasets/bank-scoring-stop-factors-2026.csv) |
| [`openapi.json`](./openapi.json) | `JSON` | Спецификация OpenAPI 3.1.0 для подключения к AI-агентам, Postman и аналитическим пайплайнам | [openapi.json](https://moifinansist.ru/openapi.json) |

---

## 1. Макропоказатели и налоговые нормативы МСП на 2026 год (ЦБ РФ и НК РФ)

| Показатель | Значение (2026) | Нормативное основание / Примечание | Инструмент расчета |
| :--- | :--- | :--- | :--- |
| **Ключевая ставка Банка России** | **14,0% годовых** | Базовый индикатор стоимости коммерческого и льготного фондирования | [Кредитный калькулятор бизнеса](https://moifinansist.ru/calculators/kreditnyy-kalkulyator-dlya-biznesa) |
| **Фиксированный страховой взнос ИП за себя** | **57 390 ₽** | ст. 430, 432 НК РФ (срок уплаты — не позднее **28 декабря 2026 г.**) | [Калькулятор взносов ИП 2026](https://moifinansist.ru/calculators/kalkulyator-strahovyh-vznosov-ip) |
| **Максимальный доп. взнос ИП (1% свыше 300 тыс. ₽)** | **321 818 ₽** | ст. 430 НК РФ (срок уплаты — до **1 июля 2027 г.**; совокупный максимум взносов ИП — **379 208 ₽**) | [Калькулятор взносов ИП 2026](https://moifinansist.ru/calculators/kalkulyator-strahovyh-vznosov-ip) |
| **Предельный годовой доход на УСН** | **490,5 млн ₽** | Базовый лимит 450 млн ₽ × коэффициент-дефлятор 2026 года (**1,090**); ОС — до 218 млн ₽, штат — до 130 чел. | [Гайд по кредитованию на УСН](https://moifinansist.ru/blog/dokumenty-dlya-kredita-ip-na-usn) |
| **Порог освобождения от НДС на УСН** | **20,0 млн ₽** | ст. 145 НК РФ (при доходе от 20 до 272,5 млн ₽ — НДС **5%**, от 272,5 до 490,5 млн ₽ — НДС **7%**) | [Чек-лист документов УСН](https://moifinansist.ru/blog/spisok-dokumentov-dlya-kredita-na-usn-polnyy-chek-list) |

---

## 2. Таблица программ кредитования малого и среднего бизнеса (2026)

| Программа финансирования | Заемщик | Ставка (2026) | Лимит | Мин. DSCR | Формула расчета лимита | Подробнее |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **Экспресс-кредит по выписке счета 51** | ИП | 11,0% – 18,5% | до 15 млн ₽ | ≥ 1.15 | 100%–150% от среднемесячного чистого оборота по счету 51 | [Кредиты для ИП](https://moifinansist.ru/services/credit-ip) |
| **Оборотный кредит и ВКЛ для юрлиц** | ООО | 9,5% – 17,5% | до 50 млн ₽ | ≥ 1.20 | До 200% среднемесячной выручки при `Net Debt / EBITDA <= 3.0` | [Кредиты для ООО](https://moifinansist.ru/services/credit-ooo) |
| **Инвестиционный кредит под залог** | ООО, ИП | 8,5% – 15,0% | до 150 млн ₽ | ≥ 1.25 | `LTV 60%–75%` от рыночной оценки недвижимости/оборудования | [Залоговый кредит](https://moifinansist.ru/blog/kredit-pod-zalog-kommercheskoy-nedvizhimosti) |
| **Беззалоговый кредит с поручительством** | ИП, ООО | 11,0% – 19,0% | до 15 млн ₽ | ≥ 1.15 | До 1,5 среднемесячных оборотов без твердого залога | [Кредиты без залога](https://moifinansist.ru/services/no-collateral) |
| **Рефинансирование кредитов бизнеса** | ИП, ООО | 9,0% – 15,5% | до 100 млн ₽ | ≥ 1.15 | Консолидация до 5 договоров + до 30% добор на оборот | [Рефинансирование](https://moifinansist.ru/services/refinancing) |
| **Банковский овердрафт к счету 51** | ИП, ООО | 11,5% – 18,0% | до 30 млн ₽ | ≥ 1.10 | 30%–50% от среднемесячного кредитового оборота по счету 51 | [Овердрафт бизнесу](https://moifinansist.ru/blog/overdraft-dlya-ooo-i-ip) |
| **Льготная программа 1764 + ПСК КМСП** | ИП, ООО | 7,0% – 10,5% | до 2 млрд ₽ | ≥ 1.25 | Ключевая ставка ЦБ (14%) минус 3,5%–5% + зонтичное поручительство до 50% | [Господдержка МСП](https://moifinansist.ru/blog/lgotnye-kredity-dlya-msp-s-gospodderzhkoy) |
| **Промышленная ипотека и займы ФРП** | ООО, ИП | 3,0% – 5,0% | до 500 млн ₽ | ≥ 1.25 | 3% для технокомпаний и 5% для производств (Раздел C ОКВЭД) | [Субсидии и ФРП](https://moifinansist.ru/blog/gosudarstvennye-subsidii-i-lgotnye-kredity-kak-poluchit-dostup) |
| **Контрактное кредитование 44-ФЗ / 223-ФЗ** | ИП, ООО | 9,5% – 15,5% | до 100 млн ₽ | ≥ 1.15 | До 70%–80% от суммы госконтракта под залог прав требования | [Кредит под госконтракт](https://moifinansist.ru/blog/kredity-na-ispolnenie-goskontraktov-44-fz-223-fz) |

---

## 3. Матрица стоп-факторов банковского скоринга ЮЛ и ИП (2026)

| Код | Категория проверки | Критерий стоп-фактора | Пороговое значение | Экспертный разбор |
| :--- | :--- | :--- | :--- | :--- |
| `SF-01` | **БКИ и КИ руководителя** | Текущие просрочки или займы МФО у ИП / директора / учредителей | Просрочка > 1 дня либо активные микрозаймы (падение ПКР на 150–250 баллов) | [Кредитная история ИП и ООО](https://moifinansist.ru/blog/kreditnaya-istoriya-ip-i-ooo) |
| `SF-02` | **115-ФЗ и ЗСК ЦБ РФ** | Желтый или красный уровень риска в платформе «Знай своего клиента» | Налоговая нагрузка < 0,9%–1,5% от оборота, наличные > 30%, транзит | [Банковский скоринг бизнеса](https://moifinansist.ru/blog/kreditnyy-skoring-biznesa-ot-bankov) |
| `SF-03` | **ФНС и сальдо ЕНС** | Отрицательное сальдо ЕНС или блокировка счетов по ст. 76 НК РФ | Задолженность > 1 000–3 000 ₽ по справке КНД 1120101 | [Почему банк отказывает в кредите](https://moifinansist.ru/blog/pochemu-bank-otkazyvaet-biznesu-v-kredite) |
| `SF-04` | **Долговая нагрузка и EBITDA** | Превышение ковенанта долга или дефицит покрытия платежей | `Net Debt / EBITDA > 3.5–4.0` либо `DSCR < 1.15` | [Расчет EBITDA по балансу ООО](https://moifinansist.ru/blog/kak-rasschitat-ebitda-po-balansu-ooo) |
| `SF-05` | **Бухгалтерский баланс** | Чистый убыток по Форме №2 или снижение чистых активов | Строка 2400 Формы №2 < 0 либо Чистые активы < УК | [Как баланс влияет на одобрение](https://moifinansist.ru/blog/kak-buhgalteriya-vliyaet-na-odobrenie-kredita) |

---

## 4. Бесплатные финансовые калькуляторы и HTML-виджеты для сайтов

Все калькуляторы доступны онлайн без регистрации и могут быть бесплатно встроены на любой внешний сайт через `<iframe>` (конструктор кода доступен на странице [https://moifinansist.ru/open-data#widgets](https://moifinansist.ru/open-data#widgets)):

1. **[Кредитный калькулятор для бизнеса (ИП и ООО)](https://moifinansist.ru/calculators/kreditnyy-kalkulyator-dlya-biznesa)** — аннуитетный и дифференцированный график погашения ([Embed-виджет](https://moifinansist.ru/embed/kreditnyy-kalkulyator-dlya-biznesa))
2. **[Калькулятор кредита для ИП по оборотам 51 счета](https://moifinansist.ru/calculators/kalkulyator-kredita-ip)** — экспресс-скоринг беззалогового лимита ([Embed-виджет](https://moifinansist.ru/embed/kalkulyator-kredita-ip))
3. **[Калькулятор страховых взносов ИП 2026 (57 390 ₽ + 1%)](https://moifinansist.ru/calculators/kalkulyator-strahovyh-vznosov-ip)** — расчет взносов по ст. 430 НК РФ и вычета УСН ([Embed-виджет](https://moifinansist.ru/embed/kalkulyator-strahovyh-vznosov-ip))
4. **[Калькулятор рефинансирования кредитов бизнеса](https://moifinansist.ru/calculators/kalkulyator-refinansirovaniya)** — расчет экономии при снижении ставки ([Embed-виджет](https://moifinansist.ru/embed/kalkulyator-refinansirovaniya))
5. **[Калькулятор банковского овердрафта и кассового разрыва](https://moifinansist.ru/calculators/kalkulyator-overdrafta)** — расчет лимита к счету 51 и стоимости транша ([Embed-виджет](https://moifinansist.ru/embed/kalkulyator-overdrafta))

---

## 5. Использование публичного REST API

```bash
# Получить полный JSON-датасет
curl -s "https://moifinansist.ru/api/v1/lending-data" | jq .

# Получить только беззалоговые программы для ИП
curl -s "https://moifinansist.ru/api/v1/lending-data?section=programs&borrower=ip&collateral=false"
```

```python
import pandas as pd

# Загрузка CSV-датасета напрямую в pandas
df_programs = pd.read_csv("https://moifinansist.ru/datasets/ru-sme-lending-2026.csv")
df_scoring = pd.read_csv("https://moifinansist.ru/datasets/bank-scoring-stop-factors-2026.csv")
print(df_programs[["program_name", "min_rate_percent", "max_amount_rub"]])
```

---

## Лицензия и правила цитирования (CC BY 4.0)

Датасет распространяется по открытой лицензии **Creative Commons Attribution 4.0 International (CC BY 4.0)**. Вы можете свободно использовать, копировать и публиковать данные в исследованиях, статьях и обучении ИИ-моделей при условии указания активной ссылки на первоисточник: **[МойФинансист — https://moifinansist.ru](https://moifinansist.ru)**.

---

## Аналитические обзоры и конспекты (Зеркала)

- [Ставки кредитования ИП и ООО в 2026 году, лимиты по счету 51 и взносы ИП (57 390 ₽) — Telegraph](https://telegra.ph/Stavki-kreditovaniya-IP-i-OOO-v-2026-godu-limity-po-schetu-51-i-vznosy-IP-57-390--Otkrytyj-dataset-11-05)
- [Матрица стоп-факторов банковского скоринга ИП и ООО в 2026 году (115-ФЗ, ЗСК ЦБ РФ, БКИ, EBITDA) — Telegraph](https://telegra.ph/Matrica-stop-faktorov-bankovskogo-skoringa-IP-i-OOO-v-2026-godu-115-FZ-ZSK-CB-RF-BKI-EBITDA-11-05)
- [Веб-версия документации датасета (GitHub Pages)](https://piterkarpov-111.github.io/ru-sme-lending-dataset-2026/)

- [Официальное зеркало датасета на Kaggle Datasets](https://www.kaggle.com/datasets/johnjohnson1519/russian-sme-lending-and-bank-scoring-2026)
- [Официальное зеркало датасета на Hugging Face Datasets](https://huggingface.co/datasets/john11234/ru-sme-lending-2026)
