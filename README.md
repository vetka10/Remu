# Инструкция по работе с Git

![logo](Логотоп.png)

Git —  это специальная программа, которая позволяет отслеживать любые изменения в файлах, хранить их версии и оперативно возвращаться в любое сохранённое состояние.
 Git  хранит  полное отображение того, как выглядит файл в момент сохранения. Это позволяет всегда иметь полную информацию обо всех файлах и быстро восстанавливать любую из предыдущих версий.

## 1. Проверка наличия установленного Git

* В терминале выпонить комвнду `git --version` Если Git установлен , появиться сообщение с информацией о версии программы, иначе будет сообщение о ошибке. Если появилась ошибка , следуйте следующему пункту.

## 2. Установка Git

Установить систему контроля версий Git можно так:

1. Загружаем последнюю версияю Git c [сайта](https://git-scm.com/downloads).
2. Устанавливаем с настройками по умолчанию.
3. Скачать дистрибутив для нужной операционной системы.
4. Запустить установочный файл и следовать инструкциям на экране.
5. После  завершения  установки  открыть терминал или командную строку и ввести команду `git --version`. Если Git правильно установлен, отобразится версия Git.

## 3.Настройка Git

При первом использовнии Git необходимо представиться. Для этого нужно ввести в терминале 2 команды:

```md
 git config --global user.neim "Ваше имя английскими буквами"
 git config --global user.email "Ваш элетронный адрес"
```

## 4.Инициализация репозитория

 Репозиторий — это место, в котором хранится весь код и вся история его изменений.  Это просто папка связанная  с Git напрямую и содержит файлы в понятном для Git формате. Кроме того, для папки, заявленной как репозиторий, Git формирует историю изменений.
Репозиторий может быть локальным ― храниться на компьютере пользователя.
 А может быть удалённым — лежать на сервере или в облачном хранилище. В таком случае пользователи со своих устройств подключаются к этому репозиторию через интернет. Создадим репозиторий:

1. Создать пустую паку на диске.
2. Перейти в созданную папку и запустить терминал.
3. Для создания репозиторя нужно выполнить команду **git init** .
4. Создайте новый файл например Gitinstruction.md  
5. С помощью команды **git add <имя файла>** добавьте файл Gitinstruction.md  в репозиторий . После указанной команды выбранные  конкретные файлы перейдут в статус «отслеживаемых» и можно будет увидеть производимые с ними изменения ― удаление, перемещение, переименование и изменения содержимого файлов.
6. Так же команда ***git add .*** — добававляет все файлы из этой папки.
7. Затем создаем первый коммит командой ***git commit -m "Initial commit"*** или ***git commit -am "Initial commit"***.

## 5. Оновные команды для работы с Git

* git add - добавляет содержимое рабочей директории  для последующего коммита.
* git status - показывает состояния файлов в рабочей директории и индексе: какие файлы изменены, но не добавлены в индекс; какие ожидают коммита в индексе. Вдобавок к этому выводятся подсказки о том, как изменить состояние файлов.
* git diff- используется для вычисления разницы между любыми двумя Git деревьями. Это может быть разница между вашей рабочей директорией и индексом.
* git commit - берёт все данные, добавленные в индекс с помощью git add, и сохраняет их слепок во внутренней базе данных, а затем сдвигает указатель текущей ветки на этот слепок.
* git reset -  используется  для отмены изменений.
* git clean - используется для удаления мусора из рабочей директории.
* git checkout - используется для переключения веток и выгрузки их содержимого в рабочую директорию.
* git log - используется для просмотра истории коммитов, начиная с самого свежего и уходя к истокам проекта. По умолчанию, она показывает лишь историю текущей ветки, но может быть настроена на вывод истории других, даже нескольких сразу, веток. Также её можно использовать для просмотра различий между ветками на уровне коммитов.

## 6.Просмотр истории комитов и их корректировка

Коммит — это основной объект в управлении контроля версий. Он содержит все изменения за время этого коммита. Коммиты связаны между с собой как односвязный список. А именно: Есть первый коммит. Когда создается второй коммит, то он (второй) знает, что идет после первого. И таким образом можно отследить информацию.  У каждого коммита есть  своя информация, данные, они содержат:

* уникальный идентификатор коммита, по которому можно его найти;
* имя автора коммита, который создал его;
* дата создания коммита;
* комментарий, который описывает, что было сделано во время этого коммита.
* Выглядет это  примерно так:

![logo](Комит.png)

* Для просмотра всех выполненных фиксаций (комитов) можно воспользоваться историей коммитов. Она содержит сведения о каждом проведенном коммите проекта. Запросить ее можно при помощи команды:
  **git log** . В ней содержится вся информация о каждом отдельном коммите.
  * Отследить интересующие вас операции в списке изменений,  при помощи команды :
  **git show hash_commit**.
  * Если нужно переделать commit message и внести туда новый комментарий, можно написать следующую команду:
  **git commit --amend -m 'Новый комментарий'**

## 7.Как добавить изображение

* Что бы добавить и зафиксировать изображение в репозиторий, нужно сначала добавить его в нужную папку, затем выполним команду в терминале:
* **![logo](имя изображения)**

## 8. Игнорирование файлов

Git рассматривает каждый файл в рабочей копии как файл одного из трех нижеуказанных типов.

* Отслеживаемый файл — файл, который был предварительно проиндексирован или зафиксирован в коммите.
* Неотслеживаемый файл — файл, который не был проиндексирован или зафиксирован в коммите.
* Игнорируемый файл — файл, явным образом помеченный для Git как файл, который необходимо игнорировать.

Игнорируемые файлы — это артефакты сборки и файлы, генерируемые машиной из исходных файлов в вашем репозитории, либо файлы, которые по какой-либо иной причине не должны попадать в коммиты.Игнорируемые файлы отслеживаются в специальном файле .gitignore, который регистрируется в корневом каталоге репозитория.

В Git нет специальной команды для указания игнорируемых файлов: вместо этого необходимо вручную отредактировать файл .gitignore, чтобы указать в нем новые файлы, которые должны быть проигнорированы. Файлы .gitignore содержат шаблоны, которые сопоставляются с именами файлов в репозитории для определения необходимости игнорировать эти файлы. Вот некоторые распространенные примеры таких файлов:

* Для того что бы исключить из отслеживания в репозитории определенные файлы или папки , необходимо создать там файл ***.gitignore*** и записать в него их названия или шаблоны, соответствующие таким файлам и папкам.

Игнорируемые файлы отслеживаются в специальном файле .gitignore, который регистрируется в корневом каталоге репозитория. В Git нет специальной команды для указания игнорируемых файлов: вместо этого необходимо вручную отредактировать файл .gitignore, чтобы указать в нем новые файлы, которые должны быть проигнорированы. Файлы .gitignore содержат шаблоны, которые сопоставляются с именами файлов в репозитории для определения необходимости игнорировать эти файлы.

## 9. Ветки в Git

Работа с ветками в Git

Ветка в Git — это набор коммитов, расположенных в хронологическом порядке. У каждой ветки есть свое название. Основная ветка чаще всего называется ***master***, она появляется при инициализации репозитория и считается главной веткой проекта. Другим веткам вы даете имена самостоятельно. Дополнительные ветки используются для создания нового функционала и исправления ошибок. То есть все изменения в проекте создаются в отдельной ветке, а затем эта ветка сливается с основной.

## 10. Создание веток Git

По умолчанию имя основной ветки в Git - **master**. Текущая  ветка будет отмечена звездочкой *.  Команда ***git branch*** нужна для работы с ветвлением в Git. При помощи нее можно создавать новые ветки, а также просматривать, переименовывать и удалять существующие.

Создать ветку можно командой:

```md
***git branch имя новой ветки***
```

Спосок веток в репозитории можно посмотреть с помощью команды:

```md
***git branch** 
```

Чтобы переключиться на новую ветку, используйте команду:

``````md
***git checkout имя ветки***
``````

## 10. Слияние веток

* в какой-то момент нам потребуется включить обновления, представленные в других ветвях. Это может произойти, пока вы по-прежнему работаете в ветви функций. Это также может произойти, когда вы закончите работу с ветвью функций и должны сохранить изменения, добавив их в другую ветвь. В Git эти обновления можно включить, объединяя или переключяя ветви.

* Чтобы объединить основную ветвь в ветвь компонентов в командной строке, используйте следующие команды:

```md
создать/переключиться на ветку, из которой вы хотите взять изменения , вот так
`*git checkout* имя ветки (которую хотите слить с основной)`
 затем команда `*git merge master* `  
если нужно отменить слияние веток , набираем команду `**git merge --abort`
```

## 11. Удаление веток

* Что бы удалить ненужную ветку , нужно перейти в основную ветку master и ввести команду:

**git branch -d имя файла (который хотим удалить)**  или **git branch --delete имя файла (который хотим удалить)**

## 12. Знакомство с программой GitHub и создание репозитория

Git — это просто программа, которую нужно установить и подключить к своему проекту. Можно установить её на сервер и настроить удалённую работу самостоятельно. А можно воспользоваться уже готовыми сервисами. Самый популярный из них — GitHub.
 GitHub — это сайт-хранилище. Нужно сначала установить Git, потом зарегистрироваться на GitHub, создать там онлайн-репозиторий — и перенести туда файлы из своего репозитория. Можно настроить автоматический перенос и многие другие функции, которые позволят работать с кодом совместно. Наши действия:

* Регистрируемся  на GitHub: задайте логин, почту и придумайте пароль. Подтверждаем почту.

![logo](Githab1.png)

* В GitHub есть разграничение прав на работу с репозиториями. Можно задавать различные политики: сделать репозиторий публичным и приватным, ограничить права кругу пользователей или кому-то одному, например, разрешить просматривать репозиторий, но не изменять в нём данные.

* Для того чтобы сервис определил, кто вы и имеете ли право работать с тем или иным репозиторием, нужно представиться — пройти процесс аутентификации.

* Теперь создадим репозиторий

![logo](Githab2.png)

* Зададим параметры:

(1) Repository name: имя репозитория.
(2) Description: описание репозитория.
(3) Тип репозитория: Public (публичный) или Private (приватный).
(4) Ставим галку на «Создать README файл». В этом файле в формате MarkDown описывают проект или прочую документацию. Именно содержимое этого файла можно увидеть, когда заходим на главную страницу репозитория. Примеры 1, 2, 3.
(5) Если известно, на каком языке будет проект, можем добавить шаблон .gitignore для этого языка.
(6) Выбираем тип лицензии для нашего кода. В лицензии оговариваются права на проект. Стоит обратить внимание на BSD 3 или MIT, так как они предоставляют хороший баланс прав и ответственности.
(7) По умолчанию имя основной ветки в GitHub носит имя main.

![logo](Githab3.png)

* Далее GitHub показывает наборы команд, необходимые для загрузки исходного кода в репозиторий. Нас интересует второй блок.

![logo](Githab4.png)

```dm
git remote add origin https:// ссылка на удаленный репозиторий//
git branch -M main
git push -u origin main
```

Первая строка загружает origin —  прообраз нашего проекта в глобальном репозитории.  Вторая  создает  новую ветку. Третья команда загружает (пушит) изменения в GitHub-репозиторий.

И нажимаем кнопку «Create repository». У нас есть первый репозиторий

## 13. Работа с удаленными репозиториями

1. Добавление удаленного репозитория к существующему локальному. Команда ***git remote add <название удаленного репозитория> <ссылка на удаленный репозиторий>*** Ссылку на удаленный репозиторий  мы берем с Githab, нажав на большую зеленую кнопку Code на странице репозитория на GitHub.
2. Отключение удаленного репозитория от локального. Команда ***git remote remove <название удаленного репозитория>***.
3. Необходимость клонировать существующий удаленный репозиторий возникает в ситуациях, когда вы решаете поработать над уже существующим кодом. Для выполнения этой операции в Git предусмотрена команда ***git clone <ссылка на удаленный репозиторий>***Когда вы клонируете репозиторий, команда clone автоматически добавляет этот удалённый репозиторий под именем ***origin***.
4. Чтобы  получать изменения и сразу обновлять рабочую копию так, чтобы она соответствовала удаленному репозиторию.  Для этого в Git вводим команду ***git pull [origin] [имя удаленного репозитория]***.
5. Отправка изменений в удаленный репозиторий. Команда ***git push [origin] [имя удаленного репозитория] [имя ветки]***
6. Посмотреть информацию об одном из удалённых репозиториев, вы можете использовать команду git remote show [удал. сервер].

7. 14. Создание Pull Request

* Команда **pull-request** нужна, чтобы любой пользователь мог внести свой вклад в любой открытый проект, репозиторий которого есть на GitHub.
* На странице репозитория проекта, который нужно копировать. Нажимаем на кнопку `*Fork*  и git создаст точную копию этого репозитория в нашем аккаунте.
* Клонируем репозиторий к себе на компьютер `*git clone*`
* Создадим файл README.md с описанием проекта, чтобы другим пользователям было понятно, в чем отличие этой реализации от остальных.
* Сделаем коммит и выполним `*git push*`, чтобы загрузить наши изменения в удаленный репозиторий.
* Теперь GitHub подсказывает нам, что наша ветка опережает ветку исходного репозитория на один коммит и предлагает сделать пулл-реквест.
* Нажимаем на кнопку Compare на подсказке GitHub, либо переходим на вкладку `*Pull*` Requests и нажимаем `*New pull request*`.
* Перед нами откроется страница создания пулл-реквеста
Здесь мы можем просмотреть внесенные изменения и выбрать две ветки: одну в исходном репозитории, на нее будут залиты наши изменения, вторую – в нашем репозитории, с нее будут скачаны изменения. Как только мы выбрали ветки и убедились, что не внесли никаких лишних изменений, нажимаем кнопку `*Create pull request*`.
* На странице описания наших изменений
 необходимо описать, что за изменения внесли и почему они были необходимы.   Как только мы закончили с описанием, можно нажимать кнопку `*Create pull request*`.
* И попадаем на страницу уже созданного пулл-реквеста в изначальном репозитории.

