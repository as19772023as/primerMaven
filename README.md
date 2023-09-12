### Многомодульный проект на Maven

создайте одномодульный проект - как это было показано на занятии.

После необходимо установить packaging в pom

<packaging>pom</packaging>
После создаем 3 модуля в корне проекта: db, api, service.
В каждом модуле будет создан pom.xml c содержимым:
В каждом pom.xml обязательно указываем parent - в качестве родительского модуля с 
его данными и название artifactId текущего модуля (db, api, service)
Чтобы подключить новые модули к проекту, добавляем в корне проекта в файл pom.xml
 новые созданные модули:

 Подключим связанные модули между собой.

Для подключения модуля db в модуль service добавим зависимость:

    <dependencies>
        <dependency>
            <groupId>ru.netology</groupId>
            <artifactId>db</artifactId>
            <version>1.0-SNAPSHOT</version>
            <scope>compile</scope>
        </dependency>
    </dependencies>


    Теперь можно собрать проект, выполнив команду: 2 раза в IDEA ctrl+ctrl

mvn clean install