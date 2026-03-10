# EN
## General
This repository contains files that allow you to modify existing Unreal Engine class templates.
The problem with them is the default comments, which constantly need to be cleaned up, and, what is particularly annoying,
`bCanEverTick = true` for `AActor` and it's descendants, which can lead to a huge number of unnecessary Event Ticks.

There are three folders in the repository: `AllTemplates`, `DefaultTemplates`, `OnlyChangedTemplates`.

* Default Templates - backup. It is needed for those cases when you are not sure about the correctness of the existing
  templates and would like to return to the default settings without spending time verifying the files.
* All Templates - all files, both default and already modified. Needed for cases when you are not sure
  about the correctness of the existing templates, but would like to install the updated version of the templates.
* Only Changed Templates - only modified templates.

Path correctness tested on Unreal Engine 5.7

## Modified files
1. PawnClass .h/.cpp - `APawn` class.
    * Removed unnecessary comments (to the constructor, BeginPlay, SetupPlayerInputComponent).
    * Removed the Tick function (if necessary, it can be easily recreated).
    * `bCanEverTick` is now `false` by default.
2. ActorClass .h/.cpp - `AActor` class.
    * Changes are similar.
3. CharacterClass .h/.cpp - `ACharacter` class.
    * Changes are similar.
4. ActorComponentClass .h/.cpp - `UActorComponent` class.
    * Changes are similar (except that Tick is called TickComponent).

## Installation
From the folder you need, copy the `Engine` folder and paste it into the folder where the engine is installed
(by default, `C:/ProgramFiles/EpicGames/UE_5.X/`, where X is the engine version).

# RU
## Общее
В данном репозитории находятся файлы, позволяющие изменить существующие шаблоны Unreal Engine классов. 
Их проблема - в комментариях по умолчанию, которые постоянно приходится чистить, а также, что особенно неприятно,
bCanEverTick=true у AActor и наследников, что может привести к огромному количеству лишних Event Tick.

В репозитории три папки: `AllTemplates`, `DefaultTemplates`, `OnlyChangedTemplates`.

* Default Templates - бэкап. Он нужен для тех случаев, когда Вы не уверены в корректности существующих 
шаблонов и хотели бы вернуть настройки по умолчанию, не тратя время на верификацию файлов. 
* All Templates - все файлы, как по умолчанию, так и уже измененные. Нужен для тех случаев, когда Вы не уверены 
в корректности существующих шаблонов, но хотели бы поставить обновленную версию шаблонов.
* Only Changed Templates - только измененные шаблоны. 

Корректность путей протестирована на версии Unreal Engine 5.7

## Измененные файлы
1. PawnClass .h/.cpp - класс `APawn`.  
   * Убраны лишние комментарии (к конструктору, BeginPlay, SetupPlayerInputComponent).  
   * Убрана функция Tick (при необходимости, её можно спокойно создать заново)
   * `bCanEverTick` теперь по умолчанию `false`.
2. ActorClass .h/.cpp - класс `AActor`.
   * Изменения аналогичны
3. CharacterClass .h/.cpp - класс `ACharacter`.
   * Изменения аналогичны
4. ActorComponentClass .h/.cpp - класс `UActorComponent`.
   * Изменения аналогичны (разве что Tick называется TickComponent)

## Установка
В необходимой папке из трёх скопировать папку `Engine` и перекопировать её в папку с установленным движком 
(по умолчанию - `ProgramFiles/EpicGames/UE_5.X/`, где X - версия движка).