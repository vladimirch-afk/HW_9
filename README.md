# HW_9
# ОС ДЗ-9, БПИ227, Чечуров Владимир

### Задание выполнялось на оценку 10

## Условие

Реализовать для родительского и дочернего процесса двухстороннюю связь с использованием только одного неименованного канала (pipe) и циклической организацией обмена посредством семафора. При этом канал должен быть постоянно открытым. Обмен должен завершаться после поочередной передачи в каждую сторону по десять сообщений. По завершении обмена обеспечить корректное закрытие каналов и удаление семафора.

## Решение

Данная программа позволяет родительскому и дочернему процессам обмениваться информацией  через канал (pipe) и семафоры для синхронизации. Программа создает общий буфер, в котором процессы записывают и считывают данные.

Вначале создаются семафор для синхронизации обмена данными, дочерний процесс, неименованный `pipe` . Далее родитель ждет сигнала от дочернего процесса, считывает данные и отправляет сигнал о готовности принять новые данные. Дочерний процесс ждет сигнала от родительского, затем записывает случайное число в буфер и отправляет сигнал о готовности передать данные. Все сообщения передаются в виде строк. После завершения обмена данные канала закрываются, а семафор удаляется, после чего очищаются ресурсы.
