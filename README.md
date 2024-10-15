#include <iostream>
#include <cstdlib>


// exercise 1
void DateСalculation(int date1, int date2, int month1, int month2, int year1, int year2, int dateRange, int monthRange, int yearRange);
void leapYear(int year1, int year2);



// exercise 2
void arithmeticMean(int size, int arr2[], float sum, float mean);



// exercise 3
void countAnyNumbers(int size2, int arr3[], int countMinus, int countPlus, int Count0);




void main()
{
	setlocale(LC_ALL, "ru");
	srand(time(NULL));

	//exercise 1
	int date1, date2, month1, month2, year1, year2;
	int dateRange{}, monthRange{}, yearRange{};

	std::cout << "Введите дату 1 (число, месяц, год):\n";

	std::cout << "Введите число 1: ";
	std::cin >> date1;
	if (date1 < 1 || date1 > 31)
	{
		do
		{
			std::cout << "Неверно введено число 1, введите еще раз: ";
			std::cin >> date1;
		} while (date1 < 1 || date1 > 31);
	}

	std::cout << "Введите месяц 1: ";
	std::cin >> month1;
	if (month1 < 1 || month1 > 12)
	{
		do
		{
			std::cout << "Неверно введен месяц 1, введите еще раз: ";
			std::cin >> month1;
		} while (month1 < 1 || month1 > 12);
	}

	std::cout << "Введите год 1: ";
	std::cin >> year1;
	if (year1 < 1)
	{
		do
		{
			std::cout << "Неверно введен год 1, введите еще раз: ";
			std::cin >> year1;
		} while (year1 < 1);
	}


	std::cout << "\nВведите дату 2 (число, месяц, год):\n";

	std::cout << "Введите число 2: ";
	std::cin >> date2;
	if (date2 < 1 || date2 > 31)
	{
		do
		{
			std::cout << "Неверно введено число 2, введите еще раз: ";
			std::cin >> date2;
		} while (date2 < 1 || date2 > 31);
	}

	std::cout << "Введите месяц 2: ";
	std::cin >> month2;
	if (month2 < 1 || month2 > 12)
	{
		do
		{
			std::cout << "Неверно введен месяц 2, введите еще раз: ";
			std::cin >> month2;
		} while (month2 < 1 || month2 > 12);
	}

	std::cout << "Введите год 2: ";
	std::cin >> year2;
	if (year2 < 1)
	{
		do
		{
			std::cout << "Неверно введен год 2, введите еще раз: ";
			std::cin >> year2;
		} while (year2 < 1);
	}

	std::cout << "\n";
	DateСalculation(date1, date2, month1, month2, year1, year2, dateRange, monthRange, yearRange);

	std::cout << "\n";
	leapYear(year1, year2);
	std::cout << "\n\n\n";



	// exercise 2
	float sum{};
	float mean{};
	const int size = 20;
	int arr2[size];

	std::cout << "Массив для расчета среднего арифметического: \n";

	arithmeticMean(size, arr2, sum, mean);


	// exercise 3
	const int size2 = 15;
	int arr3[size2];
	int cuuntMinus{}, countPlus{}, Count0{};

	std::cout << "\n\n\n";
	std::cout << "Массив для поиска отрицательных, положительных чисел и нулей: \n";

	countAnyNumbers(size2, arr3, cuuntMinus, countPlus, Count0);
}


// exercise 1
void DateСalculation(int date1, int date2, int month1, int month2, int year1, int year2, int dateRange, int monthRange, int yearRange)
{
	dateRange = date2 - date1;
	if (dateRange < 0)
	{
		dateRange *= -1;
	}

	monthRange = month2 - month1;
	if (monthRange < 0)
	{
		monthRange *= -1;
	}

	yearRange = year2 - year1;
	if (yearRange < 0 )
	{
		yearRange *= -1;
	}

	std::cout <<"Разница между введенными датами = " << dateRange << " дней " << monthRange << " месяцев " 
		<< yearRange << " год/лет\n";
}

void leapYear(int year1, int year2)
{
	if (year1 % 400 == 0 || (year1 % 4 == 0) && (year1 % 100 != 0))
	{
		std::cout << "Год " << year1 << " високосный" << "\n";
	}
	else
	{
		std::cout << "Год " << year1 << " не високосный" << "\n";
	}


	if (year2 % 400 == 0 || (year2 % 4 == 0) && (year2 % 100 != 0))
	{
		std::cout << "Год " << year2 << " високосный" << "\n";
	}
	else
	{
		std::cout << "Год " << year2 << " не високосный" << "\n";
	}
}



 //exercise 2
void arithmeticMean(int size, int arr2[], float sum, float mean)
{
	for (int i = 0; i < size; i++)
	{
		arr2[i] = rand() % 10 + 10;
		std::cout << arr2[i] << " ";
		sum += arr2[i];
	}

	mean = sum / size;
	std::cout << "\n\n Среднее арифметическое число = " << mean << "\n";
}



// exercise 3
void countAnyNumbers(int size2, int arr3[], int countMinus, int countPlus, int Count0)
{
	for (int i = 0; i < size2; i++)
	{
		arr3[i] = rand() % 16 - 10;
		std::cout << arr3[i] << " ";
		if (arr3[i] < 0)
		{
			countMinus++;
		}

		else if (arr3[i] == 0)
		{
			Count0++;
		}

		else if (arr3[i] > 0)
		{
			countPlus++;
		}
	}

	std::cout << "\n\n В массиве " << countMinus << " отрицательных чисел, " << Count0 << " нулей и " <<
		countPlus << " положительных чисел.\n";
}
