# -enum-.-124
Перечисляемый тип enum С++. #124
enum PCState//PCState - это тип данных/ Здесь мы опишем, какие состояния б. принимать нащ комп 
{//ниже набор констант
OFF,
ON,
SLEEP

};
class PC
{
public:

	PCState GetState() { return State; }
	void SetState(PCState State)
	{
		this->State = State;
	}
private:
PCState State;//перем для состояния компа, вкл/выкл, перем с типом данных PCState

};
int main()
{
	setlocale(LC_ALL, "ru");
	PC pc;
	pc.SetState(PCState::OFF);// в парам установливаем состояние, которое вернет геттер в if
	if (pc.GetState()==PCState::ON)
	{
		cout << "РС работает!" << endl;
	}
	//PCState s;
	//s = PCState::OFF;//передали состояние компа в переменную s, удобная констр-я
	////если навести на OFF, т оно хранит ноль, ON =1, SLEEP=2
	switch (pc.GetState())//результат выполнения гет
	{
	case PCState::OFF:
			cout<< "Выключен!" << endl;
			break;
	case PCState::ON:
				cout << "Включен!" << endl;
				break;
	case PCState::SLEEP:
					cout << "Спит!" << endl;
					break;
	}
	

	return 0;
}
class PCState инкапсулировали в класс PC, синтаксис

class PC
{
public:
enum PCState//PCState - это тип данных/ Здесь мы опишем, какие состояния б. принимать нащ комп 
{//ниже набор констант
	OFF,
	ON,
	SLEEP

};
	PCState GetState() { return State; }
	void SetState(PCState State)
	{
		this->State = State;
	}
private:
	PCState State;//перем для состояния компа, вкл/выкл, перем с типом данных PCState

};
int main()
{
	setlocale(LC_ALL, "ru");
	PC pc;
	pc.SetState(PC::PCState::OFF);// в парам установливаем состояние, которое вернет геттер в if
	//Обратим внимани ена изменение синстаксиса всвязи с инкапсуляцией класса PCState
	if (pc.GetState() == PC::PCState::ON)
	{
		cout << "РС работает!" << endl;
	}
	PCState s;
	s = PCState::OFF;//передали состояние компа в переменную s, удобная констр-я
	//если навести на OFF, т оно хранит ноль, ON =1, SLEEP=2
	switch (pc.GetState())//результат выполнения гет
	{
	case PC::PCState::OFF:
		cout << "Выключен!" << endl;
		break;
	case PC::PCState::ON:
		cout << "Включен!" << endl;
		break;
	case PC::PCState::SLEEP:
		cout << "Спит!" << endl;
		break;
	}


	return 0;
}

enum Speed
{
	MTN = 150,//мы м. присвоить значения нашим эномам
	RCPOMMEND = 100,
    MAX=800
};
int main()
{
	setlocale(LC_ALL, "ru");
	Speed sp = Speed::MAX;
	cout << sp << endl;//получили реальное значение enum =800

	return 0;
}


