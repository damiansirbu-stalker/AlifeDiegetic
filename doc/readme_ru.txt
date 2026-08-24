AlifeDiegetic: Управление внутриигровым звуком для STALKER Anomaly, автор Damian
Версия: next (xlibs 1.8.4, demonized 20250908)
GitHub: https://github.com/damiansirbu-stalker/AlifeDiegetic
Список изменений: https://github.com/damiansirbu-stalker/AlifeDiegetic/blob/main/doc/changelog
English: https://github.com/damiansirbu-stalker/AlifeDiegetic/blob/main/doc/readme.txt
Баги, предложения: https://github.com/damiansirbu-stalker/AlifeDiegetic/issues

Alife Collection:
AlifeAmbience: https://github.com/damiansirbu-stalker/AlifeAmbience
AlifeBalance: https://www.moddb.com/mods/stalker-anomaly/addons/alifebalance
AlifeCompanions: https://github.com/damiansirbu-stalker/AlifeCompanions
AlifeDiegetic: https://www.moddb.com/mods/stalker-anomaly/addons/diegetic-audio-control-100
AlifeGuard: https://www.moddb.com/mods/stalker-anomaly/addons/alifeguard-1001
AlifePlus: https://www.moddb.com/mods/stalker-anomaly/addons/alifeplus-v1-0-01
AlifeSpooks: https://github.com/damiansirbu-stalker/AlifeSpooks
AlifeTactics: https://www.moddb.com/mods/stalker-anomaly/addons/alifetactics
FurnitureFuel: https://github.com/damiansirbu-stalker/FurnitureFuel
JitProfiler: https://github.com/damiansirbu-stalker/JitProfiler
TestZone: https://github.com/damiansirbu-stalker/TestZone
xlibs: https://www.moddb.com/mods/stalker-anomaly/addons/xlibs-1001

В Anomaly нет способа регулировать громкость радио, мегафонов, гитар и губных гармошек независимо от общих ползунков звука. Нельзя приглушить пропаганду Долга, не убив при этом эмбиент. AlifeDiegetic решает эту проблему.

Мод подключается напрямую к аудиоподсистемам, воспроизводящим внутриигровой звук: ph_sound для радио и мегафонов, guitar_anim для гитары у костра, harmonica_anim для губной гармошки. Каждый источник получает свой ползунок громкости, переключатель включения/выключения и, где применимо, множитель паузы, управляющий тишиной между треками или объявлениями.

Мастер-множитель громкости стоит поверх всего. Все изменения применяются немедленно через MCM.

Отсутствующие зависимости обрабатываются корректно. Если у вас не установлены моды на гитару или гармошку, соответствующие элементы управления просто не действуют.

Возможности:

Радио:
  Управление громкостью фракционных радиостанций и музыки
  Множитель паузы между треками (больше тишины или меньше)
  Переключатель включения/выключения

Мегафоны:
  Управление громкостью пропаганды Долга, объявлений Арены, тревог
  Множитель паузы между объявлениями
  Переключатель включения/выключения

Гитара:
  Управление громкостью гитары у костра (требуется мод Guitar Animation)
  Переключатель включения/выключения

Губная гармошка:
  Управление громкостью губной гармошки (требуется мод Harmonica)
  Переключатель включения/выключения

Мастер-множитель громкости, применяемый ко всем источникам

Требования:
Anomaly 1.5.3
xlibs (https://www.moddb.com/mods/stalker-anomaly/addons/xlibs-1001)
MCM
Radio_Remastered или аналог (для управления радио/мегафонами)
Guitar Animation от Daiviey (опционально, для управления гитарой)
Harmonica от Daiviey (опционально, для управления гармошкой)

Установка (MO2):
1. Установите xlibs
2. Установите AlifeDiegetic
3. Порядок загрузки не имеет значения
4. Настройте через MCM

Удаление (MO2):
Отключите или удалите в MO2.

Конфигурация:
Все настройки в MCM в разделе AlifeDiegetic. Все значения по умолчанию 1.0 (без изменений от игрового поведения).

Совместимость:
Требует xlibs.
Работает на моддированных exe themrdemonized 2025.9.10 или новее, либо AOEngine v0.55 или новее.
Полный набор функций требует последней сборки demonized. Функция, которой нужна более новая сборка, остаётся неактивной на старых exe.
Протестирован с GAMMA. Подключается к ph_sound, guitar_anim и harmonica_anim. Если эти моды отсутствуют, соответствующие элементы управления неактивны. Без модификации базовых скриптов.

Разработка:
Написано на основе исходного кода X-Ray Monolith, исходного кода моддед-экзешников Demonized и распакованных gamedata Anomaly 1.5.3.
Паттерны кода и использование движка валидированы по работам авторитетных GAMMA-моддеров (Demonized, Vintar0, RavenAscendant, xcvb).
Код валидируется в реальном времени многоступенчатым конвейером: luacheck, selene, tree-sitter AST анализ, контрактные правила, разрешение кросс-файловых зависимостей, анализ цикломатической сложности, обнаружение паттернов крашей и уязвимостей, интеграционное тестирование lua54 со стабами движка X-Ray, сканирование секретов gitleaks.
Полный отчёт в doc/test-report.log.

Часто задаваемые вопросы:

Нужны ли моддированные exe?
  Да. AlifeDiegetic требует моддированные exe от themrdemonized (2025.9.10 или новее) или AOEngine (v0.55 или новее). Ванильный Anomaly не предоставляет API, на которые он опирается.

Авторы:
Altogolik -- поддержка, идеи, исходные материалы

Использование и лицензия:
  Модпаки: разрешены и приветствуются. Сохраняйте файлы readme и лицензии.
  Аддоны, патчи, интеграции: разрешены. Укажите "AlifeDiegetic by Damian Sirbu" заметно на странице вашего мода.
  Воспроизведение реализации в другом программном обеспечении: запрещено, даже с указанием авторства.
  Полная лицензия в файле LICENSE и на GitHub.

Сообщения о проблемах и предложения
Создайте отчёт на https://github.com/damiansirbu-stalker/AlifeDiegetic/issues/new/choose или спросите на Discord-серверах GAMMA, EFP, Anomaly и Zona. Сначала прочитайте этот readme и настройки MCM.

Приложите: точные шаги воспроизведения (новая игра или именованное сохранение, ожидаемое и фактическое), сборку движка, список модов, порядок загрузки, xray.log и лог отладки мода. С сотнями загруженных модов только лог показывает, был ли задействован именно этот.

Лог отладки обязателен, поэтому выставьте уровень лога MCM на DEBUG, воспроизведите, затем верните обратно на WARN. DEBUG не бесплатен: он пишет строку для каждого события и может вызывать рывки на однопоточных сборках.
