
## Генератор Id

```cpp
#include <iostream>
#include <string>
using namespace std;

class AppleClass
{
    //Класс HumanForAppleClass дружественный класс
    friend HumanForAppleClass;

public:
    //статиченая переменная, хранит в себе количество яблок
    static int Count;

    //конструктор
    AppleClass(int weight, string color)
    {
        //присваиваем полям класса, те данные которые передали
        this->weight = weight;
        this->color = color;
        Count++;
        id = Count; 
    }

    //Метод вызова id 
    int GetId()
    {
        return id;
    }

private:
    int weight;
    int id;
    string color;
};

//инициализация статического поля вне класса
int AppleClass::Count = 0;


//Основной код
int main()
{
    setlocale(LC_ALL, "ru");

    AppleClass apple(150, "Red");
    AppleClass apple2(100, "Green");
    AppleClass apple3(120, "Yellow");

    cout << apple.GetId() << endl;
    cout << apple2.GetId() << endl;
    cout << apple3.GetId() << endl;

    return 0;
}

```
## Реализация класса String

Необходимо еще перегрузить оператор вывода, равенства 

```cpp
#include <iostream>
#include <string>
using namespace std;

class MyString
{
public:
    //конструктор без параметров, присваивается ничего, что бы точно ничего там не было
    MyString()
    {
        str = nullptr;
        length = 0;
    }

    //конструктор с параметрами, при создании объекта класса необходимо переслать строку, которую он будет хранить
    //констурктор с параметрами, это обычное присвоение объекта каких то данных
    MyString(const char *str)
    {
        //получаем количество символов в строке, которую мы передаем в объект
        length = strlen(str);

        //выделяем память для динамического массива, где будет храниться наша строка
        //+1 символ так как нужно место в массиве под терминирующий 0
        //что бы он понял str, который member. +1 для того то бы считал '\0'
        this->str = new char[length + 1];

        //копируем символы строки в массив нашего класса
        for (int i = 0; i < length; i++)
        {
            this->str[i] = str[i];
        }

        //закрываем строку терминирующим 0
        this->str[length] = '\0';
    }

    //деструктор, отвечает за освобождение ресурсов занятых объектом, вызывается при уничтожении объекта класса
    //деструктор, уничтожает все объекты, когда программа заканчивает работу
    ~MyString()
    {
        //должны очищать дин память, на которую указывает наш массив
        delete[] this->str;
    }

    //конструктор копирования, необходим для создания точной копии объекта класса, но в другой области памяти
    //констурктор копирования, это присвоение одного значения объекта другому, что бы не занимало место в динамической памяти
    MyString(const MyString &other)
    {
        length = strlen(other.str);
        this->str = new char[length + 1];

        for (int i = 0; i < length; i++)
        {
            this->str[i] = other.str[i];
        }
        this->str[length] = '\0';
    }

    //перегруженный конструктор присваивания, вызывается когда необходимо присвоить значение одного объекта другому
    MyString &operator=(const MyString &other)
    {
        //здесь логика похожа на ту которая в констукторе, за исключением того, что нам нужно позаботиться
        //об освобождении ресурсов объекта, если до копирования в него новой строки он уже содержал код
        //+ стандартный синтаксис перегрузка оператора =

        if (this->str != nullptr)
        {
            delete[] str;
        }
        length = strlen(other.str);
        this->str = new char[length + 1];

        for (int i = 0; i < length; i++)
        {
            this->str[i] = other.str[i];
        }
        this->str[length] = '\0';

        return *this;
    }

    //перегруженный оператор сложения, в текущей реализации класса String необходим для конкатенации строк. Объединение строк в одну
    //оператор конкотенации
    MyString operator+(const MyString &other)
    {
        //создаем новый пустой объект, где будем хранить результат конкатенации строк и который будет результатом работы
        //перегруженного оператора +
        MyString newStr;

        //получаем количество символов в обеих строках для конкатенации
        int thisLenght = strlen(this->str);
        int otherLenght = strlen(other.str);

        newStr.length = thisLenght + otherLenght;

        //выделяем место в динамической памяти под новую строку
        newStr.str = new char[thisLenght + otherLenght + 1];

        //копируем данные из 2х конкатенируемых строк в новую строку
        int i = 0;
        for (; i < thisLenght; i++)
        {
            newStr.str[i] = this->str[i];
        }

        for (int j = 0; j < otherLenght; j++, i++)
        {
            newStr.str[i] = other.str[j];
        }

        newStr.str[thisLenght + otherLenght] = '\0';

        //возвращаем результат конкатенации
        return newStr;
    }

    //выводит строку в консоль, в идеале для этого необходима перегрузка оператора <<
    void Print()
    {
        cout << str;
    }

    int Lenght()
    {
        return length;
    }


    //константная ссылка на объект, мы заглядываем в поля, поменять в полях мы ничего не можем, так как это ссылка
    //перегруженный оператор сравнения, сравнивает две строки сначала верны ли их длины друг другу, затем посимвольно отличается ли хоть один элемент друг от друга
    //Пример 
    //bool equal = str.operator == str2;
	//bool equal = str == str2;
	//cout << (str != str2) << endl;
    bool operator==(const MyString &other)
    {
        if (this->length != other.length)
        {
            return false;
        }

        for (int i = 0; i < this->length; i++)
        {
            if (this->str[i] != other.str[i])
            {
                return false;
            }
        }

        return true;
    }

    //перегруженный оператор не равно, возвращает обратное значение оператора сравнения
    bool operator!=(const MyString &other)
    {
        return !(this->operator==(other));
    }

    //перебор элементов, замена символа
    //перегруженный оператор квадратные скобки, принимает ссылку на тип char, что бы иметь возможность изменить его
    //берет передаваемый индекс и подставляет его к индексу str выводя этот символ
    //Пример    
	//str[0] = 'Q';
    char &operator[](int index)
    {
        return this->str[index];
    }

    //ссылка на ссылку на объект. Адрес на переменную, которая хранит в себе еще один адрес
    //конструктор перемещения
    MyString(MyString &&other)
    {
        this->length = other.length;
        this->str = other.str;

        //что бы оператор delete не удалял данные при перемещении одних файлов в другие
        //нужно заперетить ему это делать, при присваиваении nullptr оператор delete ничего делать не будет
        //expression must be a modifiable lvalue, входящий параметр НЕ должен быть константой MyString(MyString &&other)
        other.str = nullptr;
    }

private:
    //указатель на массив char, хранит символы которые мы передаем в наш объект
    //или m_data. читается как m_ member
    char *str;

    //переменная длины строки
    int length;
};

int main()
{
    MyString str("Hello");
    MyString str2("Hello");

    MyString result;
    result = str + str2;

    return 0;
}
```

## Class 

```cpp
#include <iostream>
#include <string>
using namespace std;

class Human
{
public:
    int age;
    int weight;
    string name;

    void Print()
    {
        cout << "Имя " << name << "\nВес " << weight << "\nВозраст " << age << endl
             << endl;
    }
};

class Point
{
private:
    int x;
    int y;

public:
    //Конструктор по умолчанию 
    Point() 
    {
        x = 0;
        y = 0;
    }  

    //Конструктор класса. Он есть всегда. Даже если его нет, он существует по умолчанию.
    Point(int ValueX, int ValueY)
    {
        x = ValueX;
        y = ValueY;
    }

    //Все что можно получить, необходимо писать начиная с Get
    int GetX()
    {
        return x;
    }

    int GetY()
    {
        return y;
    }

    //Методы Set
    void SetX(int ValueX)
    {
        x = ValueX;
    }

    void SetY(int ValueY)
    {
        y = ValueY;
    }

    //Другие методы
    void Print()
    {
        cout << "X= " << x << "\t Y= " << y << endl
             << endl;
    }
};

class CoffeeGrinder
{
private:
    bool CheckVoltage()
    {

        return false;
    }

public:
    void Start()
    {
        if (CheckVoltage())
        {
            cout << "Vsjuh!" << endl;
        }
        else
        {
            cout << "Beep Beep" << endl;
        }
    }
};

class MyClass
{
    int* data;

public:
    //Конструктор
    MyClass(int size)
    {
        //в конструкторе класса вы выделяем место под какой то массив 
        data = new int[size];
        for (int i = 0; i < size; i++)
        {
            data[i] = i;
        }

        cout <<"Объект " << data << " Вызывался конструктор" << endl;
    }

    //Деструктор. Всегда только один. 
    ~MyClass()
    {   
        //уберегаем от утечки памяти для динамического массива 
        delete[] data;
        cout << "Объект " << data << " Вызывался деструктор" << endl;
    }
};

void Foo()
{
    cout << "Foo начало выполения" << endl;
    MyClass a(1);
    cout << "Foo конец выполнения" << endl;
}

int main()
{
    setlocale(LC_ALL, "ru");

    Foo();

    return 0;
}

```

## Угол между векторами 
---
STUBaseCharacter.h
```cpp
public:
    UFUNCTION(BlueprintCallable, Category = "Movement")
    float GetMovementDirection() const;
```

STUBaseCharacter.cpp
```cpp
float ASTUBaseCharacter::GetMovementDirection() const
{
    const auto VelocityNormal = GetVelocity().GetSafeNormal();
    const auto AngleBetween = FMath::Acos(FVector::DotProduct(GetActorForwardVector(), VelocityNormal));
    const auto CrossProduct = FVector::CrossProduct(GetActorForwardVector(), VelocityNormal);
    return FMath::RadiansToDegrees(AngleBetween) * FMath::Sign(CrossProduct.Z);
}
```

1) Высчитывает нормаль вектора скорости 
2) Высчитывает скалярное произведение между Forward Vector и Vector Normal, берем Арк косинус получаем угол между векторами 
3) Высчитываем ортогональный вектор CrossProduct
4) Переводим AngleBetween в градусы и домножаем на знак CrossProduct 

![[Pasted image 20241220144708.png]]

## Ускорение персонажа
---
STU_CharacterMovemenetComponent.cpp

```cpp
#include "Components/STU_CharacterMovementComponent.h"
#include "Player/STUBaseCharacter.h"

float USTU_CharacterMovementComponent::GetMaxSpeed() const 
{
    const float MaxSpeed = Super::GetMaxSpeed();
    const ASTUBaseCharacter* Player = Cast<ASTUBaseCharacter>(GetPawnOwner());
    return Player && Player->IsRunning() ? MaxSpeed * RunModifier: MaxSpeed;
}
```

1) Из CharacterMovement компонента вытягивает значение GetMaxSpeed
2) GetMaxSpeed присваеивается в переменную GetMaxSpeed
3) Создается переменная Player которому присвается значение Base Character.GetPawnOwner главного перс
4) Из персонажа вытаскивается заранее созданная функция IsRunning 
5) Если она правда. Макс скорость умножается на переменную RunModifier
6) Возвращает полученный MaxSpeed 

## Типы переменных
---

```cpp
void ABaseGeometryActor::printTypes()
{
	int WeaponsNum = 4;
	int KillsNum = 7;
	float Health = 34.1535633;
	bool IsDead = false;
	bool HasWeapon = true;

	//Вывод переменных в лог
	UE_LOG(LogTemp, Display, TEXT("Weapon num: %d, kills num: %i"), WeaponsNum, KillsNum);
	UE_LOG(LogTemp, Display, TEXT("Health: %f"), Health);
	UE_LOG(LogTemp, Display, TEXT("Health: %.2f"), Health); //вывод количества чисел после запятой
	UE_LOG(LogTemp, Display, TEXT("IsDead: %d"), IsDead);
	UE_LOG(LogTemp, Display, TEXT("HasWeapon: %d"), static_cast<int>(HasWeapon)); //переобразование из одного тип в другой
}
```

```CPP
	FString Name = "John Connor";
	UE_LOG(LogBaseGeometry, Display, TEXT("Name: %s"), *Name);

	int WeaponsNum = 4;
	float Health = 34.1535633;
	bool IsDead = false;

	FString WeaponsNumStr = "Weapons num = " + FString::FromInt(WeaponsNum); 
	FString HealthStr = "Health = " + FString::SanitizeFloat(Health); 
	FString IsDeadStr = "Is dead = " + FString(IsDead ? "true" : "false"); 

	FString Stat = FString::Printf(TEXT(" \n -- All Stat -- \n %s \n %s \n %s "), *WeaponsNumStr, *HealthStr, *IsDeadStr);
	UE_LOG(LogBaseGeometry, Warning, TEXT("%s"), *Stat);

	GEngine->AddOnScreenDebugMessage(-1, 3.0f, FColor::Red, Name);
	GEngine->AddOnScreenDebugMessage(-1, 5.0f, FColor::Green, Stat, true, FVector2D(1.5f, 1.5f));
```

## Движение по траектории
---

Эта логика заставляет два объекта двигаться по синусу.

```cpp
// Called every frame
void ABaseGeometryActor::Tick(float DeltaTime)
{
	Super::Tick(DeltaTime);

	FVector CurrentLocation = GetActorLocation();
	float time = GetWorld()->GetTimeSeconds();
	CurrentLocation.Z = InitialLocation.Z + Amplitude * FMath::Sin(Frequency * time);
	SetActorLocation(CurrentLocation);
}
```

Ниже записывается начальные значения в переменную 

```cpp
void ABaseGeometryActor::BeginPlay()
{
	Super::BeginPlay();

	InitialLocation = GetActorLocation();
```

И возможность изменений значений во вьюпорте 

```cpp
	UPROPERTY(EditAnywhere, Category = "Movement")
	float Amplitude = 50.0f;

	UPROPERTY(EditAnywhere, Category = "Movement")
	float Frequency = 2.0f;
```

## Вывести в блюпринт. UPROPERTY
---

```cpp
protected:
	// Called when the game starts or when spawned
	virtual void BeginPlay() override;

	UPROPERTY(EditAnywhere, Category = "Weapon") // EditAnywhere - изменения где угодно
	int32 WeaponsNum = 4;

	UPROPERTY(EditDefaultsOnly, Category = "Stat") //EditDefaultsOnly - виден и изменение только внутри блюпринта
	int32 KillsNum = 7;

	UPROPERTY(EditInstanceOnly, Category = "Health") //EditInstanceOnly - виден и изменение только когда блюпринт в сцене 
	float Health = 34.1535633;

	UPROPERTY(EditAnywhere, Category = "Health") 
	bool IsDead = false;

	UPROPERTY(VisibleAnywhere, Category = "Weapon") // VisibleAnywhere - виден всегда, не возможен к редактированию. Category = "Weapon" - Категория позволяет объединить в группы 
	bool HasWeapon = true;
```

## Работа с циклом For
---


```cpp
		for (int32 i = 0; i < 10; ++i)
		{
			const FTransform GeometryTransform = FTransform(FRotator::ZeroRotator, FVector(0.0f, 300.0f * i, 300.0f));
			ABaseGeometryActor* Geometry = World->SpawnActor<ABaseGeometryActor>(GeometryClass, GeometryTransform);

			if (Geometry)
			{
				FGeometryData Data;
				Data.MoveType = FMath::RandBool() ? EMovementType::Static : EMovementType::Sin;
				Geometry->SetGeometryData(Data);
			}
		}
```

1)Вызывается 10 раз
2)Определение переменной с типом FTransform
3)Спавн актора


## Определение переменной с типом FTransform
---


``` cpp
const FTransform GeometryTransform = FTransform(FRotator::ZeroRotator, FVector(0.0f, 300.0f * i, 300.0f));
```

2)  Перменная для нее указывается тип FTransform
3) Затем вызывается конструктор класса FTransform 
4) Для него указываются параметры 
5) `FRotator::ZeroRotator` — задаёт поворот.
6) `FVector(...)` — задаёт позицию.

## Определение переменной Geometry с указателем на объект 
---


```cpp
ABaseGeometryActor* Geometry = World->SpawnActor<ABaseGeometryActor>(GeometryClass, GeometryTransform);
```

1) Определение переменной Geometry, которая является указателем тип ABaseGeometryActor 
2) **`World`** — указатель на текущий игровой мир (`UWorld*`). Это объект, который управляет всеми актами, объектами и состоянием в игровом мире.
3) **`SpawnActor<ABaseGeometryActor>`** — метод, который используется для создания (спауна) нового актора типа `ABaseGeometryActor` в игровом мире. Этот метод возвращает указатель на созданный актор, который сохраняется в переменной `Geometry`.
4) **`GeometryClass`**: Это объект типа `UClass*`, который определяет класс создаваемого актора. В данном случае это класс `ABaseGeometryActor`, который должен быть унаследован от `AActor`.
5) **`GeometryTransform`**:Это объект типа `FTransform`, который задаёт начальную позицию, поворот и масштаб создаваемого актора. Важно, что именно этот параметр определяет, где будет находиться новый актор в игровом мире, как он будет ориентирован, а также его масштаб.

## Указатель 
---

```cpp
class Person
{
public:
    void Greet()
    {
        std::cout << "Hello, I am a person!" << std::endl;
    }
};

int main()
{
    // Создаем объект класса Person
    Person person;

    // Создаем указатель на объект Person
    Person* pointer = &person;

    // Используем указатель для вызова метода объекта
    pointer->Greet();  // Вызовет method Greet() объекта person
}
```

1)Создается класс Person
2)В нем есть функция Greet, она что то делает
3)


## Функция с несколькими возвращаемыми значениями (STRUCT)
---

```cpp
struct Result {
    int sum;
    int product;
};

Result calculate(int a, int b) {
    Result res;
    res.sum = a + b;
    res.product = a * b;
    return res;
}
```

```cpp
USTRUCT(BlueprintType)
struct FGeometryData
{
	GENERATED_USTRUCT_BODY()

	UPROPERTY(EditAnywhere, Category = "Movement")
	float Amplitude = 50.0f;

	UPROPERTY(EditAnywhere, Category = "Movement")
	float Frequency = 2.0f;

	UPROPERTY(EditAnywhere, Category = "Movement")
	EMovementType MoveType = EMovementType::Static;
};
```

struct - пользовательский тип данных, который объединяет несколько переменных разных или одинаковых типов в одном объекте 
1) С помощью struct объединяем две переменные int sum и int product
2) запускаем функцию calculate, с двуми входными значениями int a, int b. Которые передаются функции для вычисления 
3) result calculate 