TARGET = exec
SRC = wassup.cpp
CXXFLAGS = -Wall -Wextra -g3 -std=c++17

$(TARGET): %.o
	@echo "Линковка (компоновка) проекта..."
	g++ wassup.o -o $(TARGET)
	@echo "Готово!"
	@echo

%.o: %.s
	@echo "Ассемблирование..."
	as wassup.s -o wassup.o
	@echo "Готово!"
	@echo

%.s: %.ii
	@echo "Компиляция..."
	g++ -S wassup.ii -o wassup.s
	@echo "Готово!"
	@echo

%.ii: wassup.cpp
	@echo "Препроцессинг..."
	g++ -E wassup.cpp -o wassup.ii
	@echo "Готово!"
	@echo

run:
	@echo "Запускаю исполняемый файл..."
	./$(TARGET)

clean:
	@echo "Провожу очистку..."
	rm -f *.o *.s *.ii $(TARGET)
	@echo "Готово!"
	@echo

.PHONY: all clean

all: $(TARGET)

