# games_tags
Это репозиторий с ноутбуками с исследованием датасета с описанием компьютерных игр и тегов к ним. Датасет был предоставлен на соревновании https://www.tinkoff.ru/solutioncup/ на секции для дата инженеров. В рамках дополнительного творческого задания было предложено поисследовать датасет на предмет интересных инсайтов. Мои исследования приведены здесь.

Структура json датасета:

[
{"app_id":,"description":"","tags":[]},
...
]

где:

app_id - идентификатор игры  

description - текстовое описание игры  

tags - список тегов которые присвоены игре  


Файлы:

games_tags_EDA - общее исследование датасета

games_tags_predict_single_tag - обучение простенькой модели угадывать один тег для игры

games_tags_predict_multiclass - обучение модели угадывать пару тегов для игры

gmas_tags_model - простая самопальная модель которая предлагает теги по описанию игры

TODO:
1. В games_tags_model параметры модели можно уточнить. Выбрать более широкую по всем измерениям сетку с более мелким разбиением. Вопрос только во времени работы.
2. В games_tags_EDA есть кластеризация по тегам, можно добавить кластеризацию по токенам извлеченным из токенизированного описания игры.
3. В games_tags_EDA есть кластеризация по тегам, в ней условие остановки реккурсивной кластеризации можно улучшить. Завязывыаться не на кол-во элементов в кластере, а на среднее значение появление тега в кластере. Чтото типа: остановка когда кол-во тегов со средним более 0.5 стало больше 5.
4. Попытки обучения моделей градиентного бустинга не внушили доверия. Можно попробовать объяснить почему обучить отдельную модель для каждого из 441 тегов это плохо/хорошо. Или предложить разбиение множества всех тегов на группы (в примере games_tags_predict_multiclass представлена группа из 2 тегов), на этих группах решать задачу мультиклассификации.
5. Предложить решение задачи выдачи тегов по описанию игры с помощью нейронной сети.
