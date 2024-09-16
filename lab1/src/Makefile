cleanup:
	rm -f file.txt with_cake.txt average.sh numbers.txt script.sh

task1:
	sh background.sh &
	cat cake_rhymes.txt > file.txt && cat file.txt && clear
	wc file.txt

task2:
	cat cake_rhymes.txt | grep cake | cat > with_cake.txt
	rm with_cake.txt > /dev/null


task3_1:
	chmod +x hello.sh
	sh hello.sh



task3_2: task3_1
	echo '#!/bin/bash\n \
    # This is a comment\n \
    echo "Current directory is:"&& pwd; \
    echo "Current date is: `date +%d-%m-%Y`"; \
    echo "Current time is: `date +%H:%M:%S`"; \
    echo "Current PATH is: $$PATH"' > script.sh
	sh script.sh


avg_input:
	 echo '#!/bin/bash\n \
    # Проверяем, есть ли входные аргументы\n \
    if [ $$# -eq 0 ]; then \n \
        echo "Нет входных аргументов." \n \
        exit 1 \n \
    fi \n \
    # Инициализируем переменные для подсчета\n \
    count=0\n \
    sum=0\n \
    # Цикл по всем аргументам\n \
    for arg in "$$@"\n \
    do\n \
        sum=$$((sum + arg))\n \
        count=$$((count + 1))\n \
    done\n \
    # Вычисляем среднее арифметическое\n \
    average=$$(echo "$$sum / $$count" | bc -l)\n \
    # Выводим количество аргументов и среднее арифметическое\n \
    echo "Количество аргументов: $$count"\n \
    echo "Среднее арифметическое: $$average"' > average.sh

task4: avg_input
	head -c 600 /dev/random | od -An -tu4 | head -n 150 > numbers.txt
	sh average.sh $$(cat numbers.txt)

