Abstract - конспект. Этот файл коспект использования C++ в unreal engine

alt + t hot key 

>    - [[CppUnAbstract#Создание с++ актора в UE|Создание с++ актора в UE]]
>    - [[CppUnAbstract#Структура класса |Структура класса ]]
>        - [[CppUnAbstract#Super|Super]]
>    - [[CppUnAbstract#Горячие клавиши|Горячие клавиши]]
>        - [[CppUnAbstract#f12 провалится в класс и посмотреть его исходный код|f12 провалится в класс и посмотреть его исходный код]]
>        - [[CppUnAbstract#Вылететь в управление, во время игры. Shift + F1|Вылететь в управление, во время игры. Shift + F1]]
>    - [[CppUnAbstract#Логирование. Макрос в UE|Логирование. Макрос в UE]]
>    - [[CppUnAbstract#Создание функции|Создание функции]]
>    - [[CppUnAbstract#Собственная категория логирования|Собственная категория логирования]]
>    - [[CppUnAbstract#Тип FString. Вывод на экран сообщения. FColor|Тип FString. Вывод на экран сообщения. FColor]]
>    - [[CppUnAbstract#Макрос UPROPERTY|Макрос UPROPERTY]]
>    - [[CppUnAbstract#Создание блюпринта из класса С++|Создание блюпринта из класса С++]]
>    - [[CppUnAbstract#Компоненты|Компоненты]]
>        - [[CppUnAbstract#Static Mesh Component и Root|Static Mesh Component и Root]]
>    - [[CppUnAbstract#Тип FTransform|Тип FTransform]]
>    - [[CppUnAbstract#Работа с Tick|Работа с Tick]]
>    - [[CppUnAbstract#ENUM|ENUM]]
>    - [[CppUnAbstract#USTRUCT|USTRUCT]]
>    - [[CppUnAbstract#Material|Material]]
>    - [[CppUnAbstract#Construction Script |Construction Script ]]
>    - [[CppUnAbstract#Editor Event|Editor Event]]
>    - [[CppUnAbstract#Timer|Timer]]
>    - [[CppUnAbstract#Spawn|Spawn]]
>    - [[CppUnAbstract#UFUNCTION, вызов функции в блюпринт графе |UFUNCTION, вызов функции в блюпринт графе ]]
>    - [[CppUnAbstract#Делегаты. Разрушение объекта. Destroy|Делегаты. Разрушение объекта. Destroy]]
>    - [[CppUnAbstract#GameModeBase|GameModeBase]]
>        - [[CppUnAbstract#Gameplay Framework|Gameplay Framework]]
>        - [[CppUnAbstract#Gamemode|Gamemode]]
>    - [[CppUnAbstract#Mapping, Action Mapping, Axis Mapping|Mapping, Action Mapping, Axis Mapping]]
>    - [[CppUnAbstract#Pawn|Pawn]]
>    - [[CppUnAbstract#Player Controller|Player Controller]]
>    - [[CppUnAbstract#GetAllActorsOfClass|GetAllActorsOfClass]]
>    - [[CppUnAbstract#Обзор основных классов Unreal |Обзор основных классов Unreal ]]
>    - [[CppUnAbstract#Modules, Targets, UnrealBuildTool|Modules, Targets, UnrealBuildTool]]
>        - [[CppUnAbstract#GameName.Target.cs. UnrealBuildTool|GameName.Target.cs. UnrealBuildTool]]
>        - [[CppUnAbstract#Module|Module]]
>    - [[CppUnAbstract#GameName.h  | GameName.cpp|GameName.h  | GameName.cpp]]
>        - [[CppUnAbstract#.uproject |.uproject ]]
>        - [[CppUnAbstract#Forward Declaration. Libraries. Precomiped headers. IWYU подход|Forward Declaration. Libraries. Precomiped headers. IWYU подход]]
>        - [[CppUnAbstract#Поиск по документации |Поиск по документации ]]
>        - [[CppUnAbstract#GameNameEditor.Target.cs.|GameNameEditor.Target.cs.]]
>    - [[CppUnAbstract#Макросы. Генерация кода |Макросы. Генерация кода ]]
>        - [[CppUnAbstract#Генерация кода|Генерация кода]]
>        - [[CppUnAbstract#Шаблоны, templates|Шаблоны, templates]]
>        - [[CppUnAbstract#Как происходит билд проекта |Как происходит билд проекта ]]
>        - [[CppUnAbstract#Макрос |Макрос ]]
>        - [[CppUnAbstract#Макрос. NAMEGAME_API|Макрос. NAMEGAME_API]]
>    - [[CppUnAbstract#Garbage Collector|Garbage Collector]]
>    - [[CppUnAbstract#Clang Format |Clang Format ]]
>    - [[CppUnAbstract#Gitignore|Gitignore]]
>    - [[CppUnAbstract#ACharacter|ACharacter]]
>    - [[CppUnAbstract#Build|Build]]
>    - [[CppUnAbstract#Movement Base|Movement Base]]
>    - [[CppUnAbstract#Camera|Camera]]
>    - [[CppUnAbstract#Jump|Jump]]
>    - [[CppUnAbstract#Nitro. Character Movement Component|Nitro. Character Movement Component]]
>    - [[CppUnAbstract#Health bar component|Health bar component]]
>    - [[CppUnAbstract#Check|Check]]
>    - [[CppUnAbstract#Указать границы |Указать границы ]]
>    - [[CppUnAbstract#TakeDamage|TakeDamage]]
>    - [[CppUnAbstract#Разное|Разное]]
>    - [[CppUnAbstract#- склейка двух элементов |- склейка двух элементов ]]


## Создание с++ актора в UE

![[Pasted image 20250510153256.png]]

## Структура класса 

### Super

это алиас на имя базового класса, класса родителя, в классичесом c++ это пишется. Позволяет обращаться ко всем функциям базового класса, через ключевое слово super 

```
Super::BeginPlay();
AActor::BeginPlay();
```

## Горячие клавиши

![[Pasted image 20250513201302.png]]

https://www.unrealengine.com/en-US/tech-blog/designer-s-guide-to-unreal-engine-keyboard-shortcuts

### f12 провалится в класс и посмотреть его исходный код

При нажатии на текстовый документ мы может найти его еще раз 
![[Pasted image 20250510185320.png]]

зайдя дойдем до еще одного исходного файла

![[Pasted image 20250510184706.png]]

![[Pasted image 20250510185354.png]]

### Вылететь в управление, во время игры. Shift + F1

![[Pasted image 20250513175029.png]]


## Логирование. Макрос в UE
---

Первый параметр это категория логирования, доп строчка, по которой мы можем фильтровать логи 
Уровень логирования, можем выдавать обычные сообщения, предупреждения или ошибка. 

Если где то при логике использовать как error затем при сборке unit тестов это не пройдет, так как один из логов вывел ошибку, так что надо быть с этим аккуратнее 

```cpp
// Called when the game starts or when spawned
void ATestingNewActor::BeginPlay()
{
    Super::BeginPlay();

    //LogTemp это готовая категория логирования 
    UE_LOG(LogTemp, Display, TEXT("Hello Unreal!"));
    UE_LOG(LogTemp, Warning, TEXT("Hello Unreal!"));
    UE_LOG(LogTemp, Error, TEXT("Hello Unreal!"));

    int WeaponsNum = 4;
    int KillsNum = 7;
    float Health = 35.531;
    bool IsDead = false;
    bool HasWeapon = true;

    UE_LOG(LogTemp, Display, TEXT("WeaponsNum "), WeaponsNum);
    UE_LOG(LogTemp, Display, TEXT("KillsNum "), KillsNum);
    UE_LOG(LogTemp, Display, TEXT("Health "), Health);
    UE_LOG(LogTemp, Display, TEXT("Health "), Health);
    UE_LOG(LogTemp, Display, TEXT("IsDead "), IsDead);
    UE_LOG(LogTemp, Display, TEXT("HasWeapon "), static_cast<int>(HasWeapon));

    UE_LOG(LogTemp, Display, TEXT("------------------------------"));

    //Спецификатор доступа, без них числа не выведутся
    UE_LOG(LogTemp, Display, TEXT("WeaponsNum %d "), WeaponsNum);                //int
    UE_LOG(LogTemp, Display, TEXT("KillsNum %i"), KillsNum);                     //int
    UE_LOG(LogTemp, Display, TEXT("Health %f"), Health);                         //float
    UE_LOG(LogTemp, Display, TEXT("Health %.2f"), Health);                       //float с ограничением после .
    UE_LOG(LogTemp, Display, TEXT("IsDead %d"), IsDead);                         //bool
    UE_LOG(LogTemp, Display, TEXT("HasWeapon %d"), static_cast<int>(HasWeapon)); //bool конвертация в int
}
```

LogTemp: Repeating last play command: Selected Viewport
LogTemp: Display: Hello Unreal!
LogTemp: Warning: Hello Unreal!
LogTemp: Error: Hello Unreal!
LogTemp: Display: WeaponsNum 
LogTemp: Display: KillsNum 
LogTemp: Display: Health 
LogTemp: Display: Health 
LogTemp: Display: IsDead 
LogTemp: Display: HasWeapon 
LogTemp: Display: ------------------------------
LogTemp: Display: WeaponsNum 4 
LogTemp: Display: KillsNum 7
LogTemp: Display: Health 35.530998
LogTemp: Display: Health 35.53
LogTemp: Display: IsDead 0
LogTemp: Display: HasWeapon 1

![[Pasted image 20241112194755.png]]

Вывод логов в различных цветах и типах
Можно выделить или нажать на макрос и его скопировать 

Идентификтатор 
%d , %i - целые числа
%f - float

![[Pasted image 20250510161726.png]]

По этому пути можно найти файл с логом 
Game\Saved\Logs

Лог весь грузится друг на друга и более старый лог лежит в начале и самый новый будет в конце 

Вывод названия актора в лог

```
    //GetName - встроенная функция у Actor, которого мы являемся наследниками, берем ее по указателю
    UE_LOG(LogForTestingNewActor, Warning, TEXT("Actor name %s"), *GetName());
```

## Создание функции
---

Объявляется в .h заголовочном файле актора. Две разные функции 

```cpp
UCLASS()

private:
	void printTypes();
	void printStringTypes();
```

Функция

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
	UE_LOG(LogTemp, Display, TEXT("HasWeapon: %d"), static_cast<int>(HasWeapon)); //`static_cast<int>(HasWeapon)` **преобразует `bool` в `int` 
	//Это нужно, потому что `%d` в `UE_LOG` ожидает `int`, а не `bool`.

}
```

Пкм, quick action and refactiring, create declataion and definition

Вывод функции 

```cpp
void ABaseGeometryActor::BeginPlay()
{
	Super::BeginPlay();
	
	printStringTypes();
	//printTypes();
	DoActorSpawn1();
	Bbdbda();
}
```


![[Pasted image 20241112194955.png]]

## Собственная категория логирования
---

![[Pasted image 20241112194555.png]]
файл
ElogVerbosity - уровни логирования которые существуют 

`DEFINE_LOG_CATEGORY_STATIC(LogBaseGeometry, All, All)` 

namespace ELogVerbosity

В файле лежат все уровни логировния, которым присвоен счет от 0 до 7+ . Присвоение all = 7 . Выведутся все уровни до 7. Такие 

```cpp
//Если указываешь в категории логирования не все, может не показываться 
//DEFINE_LOG_CATEGORY_STATIC(LogForTestingNewActor, Error, Error);

DEFINE_LOG_CATEGORY_STATIC(LogForTestingNewActor, All, All);

// Called when the game starts or when spawned
void ATestingNewActor::BeginPlay()
{
    Super::BeginPlay();

    UE_LOG(LogForTestingNewActor, Display, TEXT("info"));
}
```

## Тип FString. Вывод на экран сообщения. FColor
---

Спецификаторы формата 
printf, Print formatted data to stdout

https://cplusplus.com/reference/cstdio/printf/

документация по FString
https://dev.epicgames.com/documentation/en-us/unreal-engine/fstring-in-unreal-engine?application_version=5.4

```CPP
#include "Engine/Engine.h"

void ATestingNewActor::printStringTypes()
{
    FString Name = "JohnConnor";
    UE_LOG(LogForTestingNewActor, Warning, TEXT("Name: %s"), *Name);
    UE_LOG(LogTemp, Warning, TEXT("Hello Unreal!"));

    int WeaponsNum = 4;
    float Health = 34.1535633;
    bool IsDead = false;

    //преобразование к типу FString булевых значений
    FString WeaponsNumStr = "Weapons num = " + FString::FromInt(WeaponsNum);
    FString HealthStr = "Health = " + FString::SanitizeFloat(Health);
    FString IsDeadStr = "Is dead = " + FString(IsDead ? "true" : "false");

    //%s - модификаторы вывода чисел
    //вывод по указателю на переменные, которые хранят преобразованных в FString числа
    FString Stat = FString::Printf(TEXT(" \n == All Stat == \n %s \n %s \n %s"), *WeaponsNumStr, *HealthStr, *IsDeadStr);
    UE_LOG(LogForTestingNewActor, Warning, TEXT("%s"), *Stat);

    //вывод сообщения на экран
    //-1 у сообщения нет ключа гарантировано выведется на экран,
    //ключ позволяет сообщения с одинаковыми ключами повторно не выводится на экран
    //3.0f время
    //цвет и имя, следующии остаются без изменения. Так же в последнем имеется возможнсть поменять размер
    GEngine->AddOnScreenDebugMessage(-1, 3.0f, FColor::Red, Name);
    GEngine->AddOnScreenDebugMessage(-1, 5.0f, FColor::Green, Stat, true, FVector2D(1.5f, 1.5f));
}
```

//FromInt - получает на входе инт, а выходе возвращает string
//SanitizeFloat - получает на вход числа double, float будет авто переведен в double, на выходе получит тоже string
//? - работает как if else, если if = "true", тринарный оператор

Вывод на экран вьюпорта значений. Нужно подключить библотеку, затем в функции указать. 

```cpp
#include "Engine/Engine.h"
```

GEngine->AddOnScreenDebugMessage

![[Pasted image 20241112225525.png]]

Viewport:

![[Pasted image 20241112225518.png]]

Log:

LogForTestingNewActor: Warning: Name: JohnConnor
LogTemp: Warning: Hello Unreal!
LogForTestingNewActor: Warning:  
 == All Stat == 
 Weapons num = 4 
 Health = 34.153564 
 Is dead = false


## Макрос UPROPERTY
---
https://dev.epicgames.com/documentation/en-us/unreal-engine/unreal-engine-uproperties?application_version=5.4

Вставляется в .h заголовок. Позволяет выводить значения для изменения во вьюпорте 

```cpp

UCLASS()
class GAMEC_API ATestingNewActor : public AActor
{
    GENERATED_BODY()

public:
    // Sets default values for this actor's properties
    ATestingNewActor();

protected:
    // Called when the game starts or when spawned
    virtual void BeginPlay() override;

    //чтобы указать что мы хотим видеть эти переменные в эдиторе класса
    //мы могли изменять их значение, как глазик для перменной мы указываем
    //так же тип int32 гарантирует безопасность комплияции под различные виды платформ

    //можем указать категорию

    //спецификаторы доступа
    //можно изменять везде как внутри так и снаружи
    UPROPERTY(EditAnywhere, Category = "Weapon")
    int32 WeaponsNum = 4;

    //можно изменять только внутри
    UPROPERTY(EditDefaultsOnly, Category = "Stat")
    int32 KillsNum = 7;

    //можно изменять только снаружи
    UPROPERTY(EditInstanceOnly, Category = "Health")
    float Health = 35.531;

    //можно изменять везде как внутри так и снаружи
    UPROPERTY(EditAnywhere, Category = "Health")
    bool IsDead = false;

    //виден везде, но не доступен для редактирования
    UPROPERTY(VisibleAnywhere, Category = "Health")
    bool HasWeapon = true;

public:
    // Called every frame
    virtual void Tick(float DeltaTime) override;

private:
    void printTypes();
    void printStringTypes();
};

```


Есть различия при редактировании

EditAnywhere - изменения где угодно
EditDefaultsOnly - виден и изменение только внутри блюпринта
EditInstanceOnly - виден и изменение только когда блюпринт в сцене 
VisibleAnywhere - виден всегда, не возможен к редактированию 

Category = "Weapon" - Категория позволяет объединить в группы 

![[Pasted image 20241113075556.png]]

![[Pasted image 20241113080632.png]]

С группами 

![[Pasted image 20241113082031.png]]

Вывод двух разных акторов с двумя разными значениями, введеными в блюпринт в сцене. Затем плей и вывод. 

В функцию так же введен вывод лога, какой конкретный актор выводит значения

```cpp
void ABaseGeometryActor::printTypes()
{
	UE_LOG(LogBaseGeometry, Warning, TEXT("Actor name %s"), *GetName());
```

![[Pasted image 20241113082005.png]]
## Создание блюпринта из класса С++
---

![[Pasted image 20241113075929.png]]


## Компоненты
---
https://dev.epicgames.com/documentation/en-us/unreal-engine/components-in-unreal-engine?application_version=5.4

Компоненты - это объекты с определенной функциональностью, можено добавить к актору для расширения его возможностей 

С точки зрения ООП данный прием называется композицией 

В ооп есть 
композиция, деления на части закрытые и открыте 
полиморфизм на различных объекта методы могут вести себя по разному 
наследование наследующие классы сохраняют функционал родителей 

### Static Mesh Component и Root

Необходимо добавить библиотеку в заголовочный файл

Затем добавить что он был виден во вьюпорте. Он будет отсылаться к коду в cpp файле

```cpp
#include "Components/StaticMeshComponent.h"

public:	
	// Sets default values for this actor's properties
	ABaseGeometryActor();

    //Добавление статик компонета статик меша к актору
    //Принимает по указателю на BaseMesh
    UPROPERTY(EditAnywhere)
    UStaticMeshComponent* BaseMesh;
```


Так же в cpp файле нужно добавить код, который позволяет добавить меш. Так же здесь добавляется гизмо. Рут актора 

```cpp
// Sets default values
ATestingNewActor::ATestingNewActor()
{
    // Set this actor to call Tick() every frame.  You can turn this off to improve performance if you don't need it.
    PrimaryActorTick.bCanEverTick = true;

    //Присваивание переменной BaseMesh типа UStaticMeshComponent из шаблонной функции, которое принимает имя (легкое)
    BaseMesh = CreateDefaultSubobject<UStaticMeshComponent>("BaseMesh");

    //Создает root для актора
    //Это функция, которая принимает в себя переменную, объект который возьмет за центр 
    SetRootComponent(BaseMesh);
       
}
```

![[Pasted image 20241114064326.png]]

![[Pasted image 20241114064639.png]]

## Тип FTransform
---

```cpp
// Called when the game starts or when spawned
void ATestingNewActor::BeginPlay()
{
    Super::BeginPlay();

    //создаем переменную типа FTransform и присваиваем туда возвращаемое значение функции GetActorTransform()
    FTransform Transform = GetActorTransform();

    //Присваиваение основных XYZ переменных
    FVector Location = Transform.GetLocation();
    FRotator Rotator = Transform.Rotator();
    FVector Scale = Transform.GetScale3D();

    //название актора 
    UE_LOG(LogForTestingNewActor, Warning, TEXT("Actor name is %s"), *GetName());

    //Transform
    UE_LOG(LogForTestingNewActor, Warning, TEXT("Transform %s"), *Transform.ToString());

    //XYZ
    UE_LOG(LogForTestingNewActor, Warning, TEXT("Location %s"), *Location.ToString());
    UE_LOG(LogForTestingNewActor, Warning, TEXT("Rotator %s"), *Rotator.ToString());
    UE_LOG(LogForTestingNewActor, Warning, TEXT("Scale %s"), *Scale.ToString());

    //Более информативный и подробный показ Transform 
    UE_LOG(LogForTestingNewActor, Error, TEXT("Human transform %s"), *Transform.ToHumanReadableString());
}
```

![[Pasted image 20241114070425.png]]

LogForTestingNewActor: Warning: Actor name is TestingNewActor_1
LogForTestingNewActor: Warning: Transform 119.741516,-222.324280,77.975342|0.000000,0.000000,0.000000|1.000000,1.000000,1.000000
LogForTestingNewActor: Warning: Location X=119.742 Y=-222.324 Z=77.975
LogForTestingNewActor: Warning: Rotator P=0.000000 Y=0.000000 R=0.000000
LogForTestingNewActor: Warning: Scale X=1.000 Y=1.000 Z=1.000
LogForTestingNewActor: Error: Human transform Rotation: Pitch 0.000000 Yaw 0.000000 Roll 0.000000
Translation: 119.741516 -222.324280 77.975342
Scale3D: 1.000000 1.000000 1.000000

LogForTestingNewActor: Warning: Actor name is TestingNewActor_2
LogForTestingNewActor: Warning: Transform 91.476807,102.816849,171.065277|0.000000,0.000000,0.000000|1.000000,1.000000,1.000000
LogForTestingNewActor: Warning: Location X=91.477 Y=102.817 Z=171.065
LogForTestingNewActor: Warning: Rotator P=0.000000 Y=0.000000 R=0.000000
LogForTestingNewActor: Warning: Scale X=1.000 Y=1.000 Z=1.000
LogForTestingNewActor: Error: Human transform Rotation: Pitch 0.000000 Yaw 0.000000 Roll 0.000000
Translation: 91.476807 102.816849 171.065277
Scale3D: 1.000000 1.000000 1.000000

## Работа с Tick
---
Отключение работы всего тика 

```cpp
// Sets default values
//конструктор
AGeometryHubActor::AGeometryHubActor()
{
 	// Set this actor to call Tick() every frame.  You can turn this off to improve performance if you don't need it.
	PrimaryActorTick.bCanEverTick = true;

}
```

Эта логика заставляет два объекта двигаться по синусу.

New git ignore file
rules of naming variables 
Work on libraries STL

Timer, Event Editor, Constructor Script, Matrerial, USTRUCT, ENUM, Tick, FTransform



.h

```cpp 
// Fill out your copyright notice in the Description page of Project Settings.

#pragma once

#include "CoreMinimal.h"
#include "GameFramework/Actor.h"
#include "Components/StaticMeshComponent.h"
#include "TestingNewActor.generated.h"

UCLASS()
class GAMEC_API ATestingNewActor : public AActor
{
    GENERATED_BODY()

public:
    // Sets default values for this actor's properties
    ATestingNewActor();

    //Добавление статик компонета статик меша к актору
    //Принимает по указателю на BaseMesh
    UPROPERTY(EditAnywhere)
    UStaticMeshComponent* BaseMesh;

protected:
    // Called when the game starts or when spawned
    virtual void BeginPlay() override;

    //Две переменные, отвечающие за амплитуду и частоту колебаний для логики движения объектов 
    UPROPERTY(EditAnywhere, Category = "Movement")
    float Amplitude = 50.0f;

    UPROPERTY(EditAnywhere, Category = "Movement")
    float Frequency = 2.0f;

public:
    // Called every frame
    virtual void
    Tick(float DeltaTime) override;

private:
    //Кешшированная переменная, которая содержит начальное положение актора
    FVector InitialLocation;
};
```

.cpp

```cpp
// Fill out your copyright notice in the Description page of Project Settings.

#include "TestingNewActor.h"
#include "Engine/Engine.h"

// Called when the game starts or when spawned
void ATestingNewActor::BeginPlay()
{
    Super::BeginPlay();

    //доп функция получения локации актора
    //так же можно сделать через Transform.GetLocation()
    //Присваиваем при создании запуске игры 
    InitialLocation = GetActorLocation();

}

// Called every frame
void ATestingNewActor::Tick(float DeltaTime)
{
    Super::Tick(DeltaTime);

    //Работа в Tick
	//В переменную CurrentLocation, текующей позиции. типа FVector присваиваем
	FVector CurrentLocation = GetActorLocation();
	if (GetWorld())
	{
		float Time = GetWorld()->GetTimeSeconds();
		CurrentLocation.Z = InitialLocation.Z + GeometryData.Amplitude * FMath::Sin(GeometryData.Frequency * Time);
		SetActorLocation(CurrentLocation);
	}
}
```


![[Pasted image 20241114073000.png]]


## ENUM
---

В заголовочном файле указываем состояния которые используются. Для них всегда используется uint8 и так же в начале названия указывается буква E... 

```cpp
//Класс ENUM отвечающий за тип движения
//UENUM это макрос который расширяет возможности enum и позволяет выводить его в едитор
//Все enum должны начинать с заглавной буквы E , EMovementType
UENUM(BlueprintType)
enum class EMovementTypeTestingActor : uint8
{
    SIN,
    STATIC
};
```

Определяем переменную и выводим ее для изменения во вьюпорте 

```cpp
	UPROPERTY(EditAnywhere, Category = "Movement")
	EMovementType MoveType = EMovementType::Static;
```

В спп файле создаем switch. И указываем значения действия для каждого состояния 

```cpp
void ABaseGeometryActor::Tick(float DeltaTime)
{
	Super::Tick(DeltaTime);

	switch (MoveType)
	{
		case EMovementType::Sin:
		{
			FVector CurrentLocation = GetActorLocation();
			float time = GetWorld()->GetTimeSeconds();
			CurrentLocation.Z = InitialLocation.Z + Amplitude * FMath::Sin(Frequency * time);

			SetActorLocation(CurrentLocation);
		}
		break;

		case EMovementType::Static:break;
		default:break;
	}
}
```

![[Pasted image 20241116100210.png]]

## USTRUCT
---
USTRUCT служит для объединия в группы. У структур всегда впереди идет буква F.. и макрос GENERATED_USTRUCT_BODY()

Позволяет передавать переменные не по отдельности, а целым объектом

```cpp
// Fill out your copyright notice in the Description page of Project Settings.

#pragma once

#include "CoreMinimal.h"
#include "GameFramework/Actor.h"
#include "Components/StaticMeshComponent.h"
#include "TestingNewActor.generated.h"

//Все типы структур начинаются с F
//структура тот же класс, но все поля public
//структура при наследовании имеет все поля как public
//можно объединять переменные для их удобной группировки
USTRUCT(BlueprintType)
struct FGeometrydataTestingActor
{
    GENERATED_USTRUCT_BODY()

    //Две переменные, отвечающие за амплитуду и частоту колебаний для логики движения объектов
    UPROPERTY(EditAnywhere, Category = "Movement")
    float Amplitude = 50.0f;

    UPROPERTY(EditAnywhere, Category = "Movement")
    float Frequency = 2.0f;

    //Создание переменной MoveType типа enum MovementType
    //который содержит переходные значия STATIC, SIN
    UPROPERTY(EditAnywhere, Category = "Movement")
    EMovementTypeTestingActor MoveType = EMovementTypeTestingActor::STATIC;
};

UCLASS()
class GAMEC_API ATestingNewActor : public AActor
{
    GENERATED_BODY()

public:
    // Sets default values for this actor's properties
    ATestingNewActor();

    //Добавление статик компонета статик меша к актору
    //Принимает по указателю на BaseMesh
    UPROPERTY(EditAnywhere)
    UStaticMeshComponent* BaseMesh;

protected:
    // Called when the game starts or when spawned
    virtual void BeginPlay() override;

    //переменная хранящая в себе структуру
    //В ней хранятся для вывода другие переменные 
    UPROPERTY(EditAnywhere, Category = "GeometryData")
    FGeometrydataTestingActor GeometryData;

public:
    // Called every frame
    virtual void
    Tick(float DeltaTime) override;

private:

};

```

Так же стоит отметить, что при переносе из в структуры могут теряться связи. Так что необходимо обновить пути для каждой переменной 

GeometryData.Amplitude
GeometryData.Frequency
GeometryData.MoveType

```cpp
switch (GeometryData.MoveType)
	{
		case EMovementType::Sin:
		{
			FVector CurrentLocation = GetActorLocation();
			float time = GetWorld()->GetTimeSeconds();
			CurrentLocation.Z = InitialLocation.Z + GeometryData.Amplitude * FMath::Sin(GeometryData.Frequency * time);
```

![[Pasted image 20241116095629.png]]

## Material
---

https://dev.epicgames.com/documentation/en-us/unreal-engine/unreal-engine-materials?application_version=5.4

Создаются обычным способом материалы. Затем в них создаются параметры. В коде можно взять материал и управлять параметров в этом материале. Важен не название материала, а параметр в нем. 

Если будут два разных материала, но одинаковые параметры внутри, код будет работать

![[Pasted image 20241117012658.png]]

![[Pasted image 20241117013133.png]]

```cpp
#include "Materials/MaterialInstanceDynamic.h"
```

Создание функции с ссылкой на параметр в материале, для изменения.

```cpp
USTRUCT(BlueprintType)
struct FGeometrydataTestingActor
{
    GENERATED_USTRUCT_BODY()

	//Еще переменные 

    //Цвет меша, задание ему цвета через эдитор и установка цвета по умолчанию 
    UPROPERTY(EditAnywhere, Category = "Design")
    FLinearColor Color = FLinearColor::Black;
};

UCLASS()
class GAMEC_API ATestingNewActor : public AActor
{
    GENERATED_BODY()
    //код
    
private:
    void SetColor(const FLinearColor& Color);
};
```

```cpp
// Called when the game starts or when spawned
void ATestingNewActor::BeginPlay()
{
    Super::BeginPlay();

    SetColor(GeometryData.Color = FLinearColor::Blue);
}

void ATestingNewActor::SetColor(const FLinearColor& Color)
{
    if (!BaseMesh)
    {
        //Создание материала
        //В указатель
        UMaterialInstanceDynamic* DynMaterial = BaseMesh->CreateAndSetMaterialInstanceDynamic(0);
        if (DynMaterial)
        {
            //У материала выставляем цвет в его параметре Color
            //при старте цвет изменить на желтый, если параметр совпадает он сам изменит ему цвет
            //выбирать конкретный материал не нужно, он реагирует только на параметры
            //FLinearColor - 32 битный цвет, FColor - 8бит
            DynMaterial->SetVectorParameterValue("Color", Color);
        }
    }
}
```

```cpp
DynMaterial->SetVectorParameterValue("Color",FLinearColor::Yellow);
```

Указание изменение файла во вьюпорте 

```cpp
	UPROPERTY(EditAnywhere, Category = "Design")
	FLinearColor Color = FLinearColor::Black;
```

## Construction Script 

```cpp
UCLASS()
class GAMEC_API ATestingNewActor : public AActor
{
    GENERATED_BODY()

public:
    // Sets default values for this actor's properties
    ATestingNewActor();

protected:
    // Called when the game starts or when spawned
    virtual void BeginPlay() override;

    //функция которая срабатывает при создании 
    //Аналог Construction Script 
    virtual void OnConstruction(const FTransform& Transform) override;
```

```cpp
void ATestingNewActor::OnConstruction(const FTransform& Transform)
{
    Super::OnConstruction(Transform);

	//вызов функций
    SetColor(GeometryData.Color = FLinearColor::Black);
}
```
## Editor Event

```cpp
UCLASS()
class GAMEC_API ATestingNewActor : public AActor
{
    GENERATED_BODY()

public:
    // Sets default values for this actor's properties
    ATestingNewActor();

    //Добавление статик компонета статик меша к актору
    //Принимает по указателю на BaseMesh
    UPROPERTY(EditAnywhere)
    UStaticMeshComponent* BaseMesh;

protected:
    // Called when the game starts or when spawned
    virtual void BeginPlay() override;


    //Евент, если изменяется что то в едиторе то запускается этот евент
    //В данном случае к моему цвету применяется другой цвет
    virtual void PostEditChangeProperty(FPropertyChangedEvent& PropertyChangedEvent) override;
```

```cpp

void ATestingNewActor::PostEditChangeProperty(FPropertyChangedEvent& PropertyChangedEvent)
{
    Super::PostEditChangeProperty(PropertyChangedEvent);

    //// 2. Устанавливаем цвет меша в редакторе.
    //UMaterialInstanceDynamic* DynamicMaterial = UMaterialInstanceDynamic::Create(BaseMesh->GetMaterial(0), this);
    //if (DynamicMaterial)
    //{
    //    DynamicMaterial->SetVectorParameterValue(TEXT("Color"), FLinearColor::Yellow); // "Color" - имя параметра в material
    //    BaseMesh->SetMaterial(0, DynamicMaterial);
    //}

    UMaterialInstanceDynamic* DynMaterial = BaseMesh->CreateAndSetMaterialInstanceDynamic(0);
    if (DynMaterial)
    {
        //У материала выставляем цвет в его параметре Color
        //при старте цвет изменить на желтый, если параметр совпадает он сам изменит ему цвет
        //выбирать конкретный материал не нужно, он реагирует только на параметры
        //FLinearColor - 32 битный цвет, FColor - 8бит
        DynMaterial->SetVectorParameterValue("Color", FLinearColor::Yellow);
    }
}
```
## Timer
---

https://dev.epicgames.com/documentation/en-us/unreal-engine/gameplay-timers-in-unreal-engine?application_version=5.4

Таймер позволяет установить время и на каждый тик будет происходить действие 

Обозначаем переменные отвечающую за частоту срабатывания 

Создаем дискриптор Timer Handle, будет иметь доступ к нему. Сможем поставить его на паузу или остановить. Так же создаем счетчик и максимальное значение. Эти значения потом будут сравниваться 

.h

```cpp
USTRUCT(BlueprintType)
struct FGeometrydataTestingActor
{
    GENERATED_USTRUCT_BODY()
    
    //Таймер 
    UPROPERTY(EditAnywhere, Category = "Design")
    float TimerRate = 3.0f;
};

public:
    // Called every frame
    virtual void
    Tick(float DeltaTime) override;

private:
    //Создание перменной класса таймера
    FTimerHandle TimerHandle;

    //количетсво раз сколько сработать до конца 
    const int32 MaxTimerCount = 5;

    //счетчик срабатывания 
    int32 TimerCount = 0;

	//Функция во время работы таймера на каждый тик 
	void OnTimerFired();
};

```

.cpp

```cpp
#include "TimerManager.h"

// Called when the game starts or when spawned
void ATestingNewActor::BeginPlay()
{
    Super::BeginPlay();

    //вызов функции установки таймера с передачей значений
    //переданная функция OnTimerFired это функция которая работает во время таймера 
    //true - таймер срабатает один раз и остановится 
    GetWorldTimerManager().SetTimer(TimerHandle, this, &ATestingNewActor::OnTimerFired, GeometryData.TimerRate, true);

}

void ATestingNewActor::OnTimerFired()
{
    if (++TimerCount <= MaxTimerCount)
    {
        const FLinearColor NewColor = FLinearColor::MakeRandomColor();

        //TimerCount передается по значению, потому что спецификатор %i требует значение типа int.
        //*NewColor.ToString() передается как указатель, потому что спецификатор % s требует указатель на строку типа const TCHAR *.
        UE_LOG(LogForTestingNewActor, Display, TEXT("TimerCount: %i, Color to set  up: %s"), TimerCount, *NewColor.ToString());
        SetColor(NewColor);
    }
    else
    {
        UE_LOG(LogForTestingNewActor, Display, TEXT("Timer has been stopped!"));

        //остановка таймера, какой таймер остановить
        GetWorldTimerManager().ClearTimer(TimerHandle);
    }
}
```

```

Вызываем таймер

TimerHandle - указываем существующий таймер

this - указываем на объект на которую будет срабатывать функция 

&ABaseGeometryActor::OnTimerFired - ссылка на функцию, которая будет вызываться каждый тик 

GeometryData.TimerRate - частота срабатывания тиков 

true - зацикленный таймер или нет. Если false, срабатывает 1 раз и останавливается 

---

Создаем что бы функция ставила рандомные значения цвета. Используя уже имещуюся функцию SetColor и передадим туда новую переменную NewColor. Так же каждый раз выводим лог с цветом 

Затем к счетчику TimerCount добавляем +1, пока он не будет меньше чем MaxTimerCount

После закрываем таймер и выводим лог 

func
```cpp
void ABaseGeometryActor::OnTimerFired()
{
	if (++TimerCount <= MaxTimerCount)
	{
		const FLinearColor NewColor = FLinearColor::MakeRandomColor();
		
		UE_LOG(LogBaseGeometry, Display, TEXT("TimerCount: %i, Color to set up: %s"), TimerCount, *NewColor.ToString());
		
		SetColor(NewColor);
	}
	else
	{
		UE_LOG(LogBaseGeometry, Warning, TEXT("Timer has been stopped!"));
		GetWorldTimerManager().ClearTimer(TimerHandle);
	}
}
```

![[Pasted image 20241117044234.png]]

## Spawn
---

Spawn documention
https://dev.epicgames.com/documentation/en-us/unreal-engine/spawning-actors-in-unreal-engine?application_version=5.4

TArray documentation
file:///O:/UnrealProject/UE_C++_And_Base/UE_C++_And_Base/2.%20Основы%20C++%20в%20Unreal%20Engine/10.2%20Документация%20по%20TArray.html

TSubclassOf documentation
https://dev.epicgames.com/documentation/en-us/unreal-engine/typed-object-pointer-properties-in-unreal-engine?application_version=5.4

![[Pasted image 20241130015955.png]]

.h

```c++
// Fill out your copyright notice in the Description page of Project Settings.

#pragma once

#include "CoreMinimal.h"
#include "GameFramework/Actor.h"
#include "TestingNewActor.h"
#include "GeometryHubTestingActor.generated.h"

//настройки для изменения данных для каждого спавн элемента
USTRUCT(BlueprintType)
struct FGeometryPayloadTestingActor
{
    GENERATED_USTRUCT_BODY()

    UPROPERTY(EditAnywhere)
    TSubclassOf<ATestingNewActor> GeometryClass;

    UPROPERTY(EditAnywhere)
    FGeometrydataTestingActor Data;

    UPROPERTY(EditAnywhere)
    FTransform InitialTransform;
};

UCLASS() class GAMEC_API AGeometryHubTestingActor : public AActor
{
    GENERATED_BODY()

public:
    // Sets default values for this actor's properties
    AGeometryHubTestingActor();

protected:
    // Called when the game starts or when spawned
    virtual void BeginPlay() override;

    //TSubclassOf отфильтрует все классы движка и property можно будет
    //установить только сам класс или который от него наследуется
    //именно GeometryClass выбранный тут будет спавниться
    UPROPERTY(EditAnywhere)
    TSubclassOf<ATestingNewActor> GeometryClass;

    UPROPERTY(EditAnywhere)
    UClass* Class;

    UPROPERTY(EditAnywhere)
    ATestingNewActor* GeometryObject;

    //Тип массив объектов 
    //Принимает тип объектов в массиве 
    UPROPERTY(EditAnywhere)
    TArray<FGeometryPayloadTestingActor> GeometryPayloads;

public:
    // Called every frame
    virtual void Tick(float DeltaTime) override;
};

```

.cpp

```cpp
// Fill out your copyright notice in the Description page of Project Settings.

#include "GeometryHubTestingActor.h"
#include "Engine/World.h"

// Sets default values
AGeometryHubTestingActor::AGeometryHubTestingActor()
{
    // Set this actor to call Tick() every frame.  You can turn this off to improve performance if you don't need it.
    PrimaryActorTick.bCanEverTick = true;
}

// Called when the game starts or when spawned
void AGeometryHubTestingActor::BeginPlay()
{
    Super::BeginPlay();

    //указатель на мир игры, в нем находится функция спавна
    //GetWorld() - возвращает указатель на глобальный объект мира игры
    UWorld* World = GetWorld();
    if (World)
    {
        for (int32 i = 0; i < 10; i++)
        {
            //трансформация актора
            //поворот, положение, размер
            const FTransform GeometryTransform = FTransform(FRotator::ZeroRotator, FVector(0.0f, 300.0f * i, 300.0f));

            //спавн объекта
            //в параметрах спавна он может получать объект спавна
            //локацию, ротацию и доп данные
            //World->SpawnActor(GeometryClass);

            //создаем приведении типов, что могли сразу иметь указатель на объект нашего типа
            //то есть не надо приводить каст от AActor к ATestingNewActor
            //так же передаем трансформацию актора
            ATestingNewActor* Geometry = World->SpawnActor<ATestingNewActor>(GeometryClass, GeometryTransform);

            //проверка на валидность, можем ли мы вообще взять объект Geometry. иначе будет ошибка
            if (Geometry)
            {
                FGeometrydataTestingActor Data;
                Data.MoveType = FMath::RandBool() ? EMovementTypeTestingActor::STATIC : EMovementTypeTestingActor::SIN;
                Geometry->SetGeometryData(Data);
            }
        }

        //для 10 элементов
        for (int32 i = 0; i < 10; i++)
        {
            //настройки положения по умолчанию
            const FTransform GeometryTransform = FTransform(FRotator::ZeroRotator, FVector(0.0f, 300.0f * i, 700.0f));

            //SpawnActorDeferred
            //этот спавн отличается тем что при создании актора, будет вызван только констурктор,
            //а бегин плей не будет вызван
            ATestingNewActor* Geometry = World->SpawnActorDeferred<ATestingNewActor>(GeometryClass, GeometryTransform);

            if (Geometry)
            {
                FGeometrydataTestingActor Data;
                Data.Color = FLinearColor::MakeRandomColor();
                Geometry->SetGeometryData(Data);

                //ручной запуск бегин плей
                Geometry->FinishSpawning(GeometryTransform);
            }
        }

        //для всех объектов находящихся в массиве GeometryPayloads
        //разделяет объявление переменной (const FGeometryPayloadTestingActor Payload) цикла
        //от коллекции GeometryPayloads (диапазона), по которой будет происходить итерация

        for (const FGeometryPayloadTestingActor Payload : GeometryPayloads)
        {
            //World->SpawnActorDeferred<ATestingNewActor>(...)
            //
            //World : Это указатель на текущий игровой мир(UWorld*).
            //Обычно получается через GetWorld().
            //Мир отвечает за управление всеми акторами на уровне.
            //
            //SpawnActorDeferred : Это специальная функция для спавна(создания) актора,
            //которая откладывает некоторые этапы его инициализации.
            //В отличие от SpawnActor, SpawnActorDeferred не вызывает сразу BeginPlay()
            //и другие функции инициализации, связанные с полным появлением актора в мире.
            //
            //<ATestingNewActor> : Это шаблонный параметр, указывающий ожидаемый тип возвращаемого значения.
            //То есть, мы говорим, что хотим заспавнить актора, который будет(или будет совместим с)
            //типом ATestingNewActor, и мы хотим получить указатель именно этого типа.
            //
            //Payload.GeometryClass : Это аргумент, передающий класс актора, который нужно создать.
            //Он должен быть типа TSubclassOf<AActor>(или более конкретного, например TSubclassOf<ATestingNewActor>).
            //Это UClass * который был выбран в Payload.Это позволяет спавнить акторы разных классов,
            //если Payload.GeometryClass может содержать разные классы.
            //
            //Payload.InitialTransform : Это аргумент, передающий начальную трансформацию(положение, поворот, масштаб)
            //для создаваемого актора.Тип FTransform.ATestingNewActor* Geometry = ... :
            //Результат SpawnActorDeferred присваивается указателю Geometry типа ATestingNewActor*.

            //Зачем нужен SpawnActorDeferred ?
            //Он используется,когда тебе нужно настроить актора(установить его свойства,
            //вызвать какие - то специфические функции инициализации) до того,
            //как он полностью появится в мире и начнет свою “жизнь” (до вызова BeginPlay()).
            //Если бы ты использовал обычный SpawnActor,
            //то BeginPlay() был бы вызван сразу после конструктора,
            //и у тебя не было бы возможности что - то настроить перед этим.

            ATestingNewActor* Geometry = World->SpawnActorDeferred<ATestingNewActor>(Payload.GeometryClass, Payload.InitialTransform);

            if (Geometry)
            {
                //Мы передаем в этот метод какие-то данные из нашей структуры Payload.
                Geometry->SetGeometryData(Payload.Data);

                //Именно здесь, между SpawnActorDeferred и FinishSpawning,
                //ты можешь безопасно вызывать сеттеры и другие функции для настройки своего актора.
                //На этом этапе BeginPlay() еще не был вызван.

                //Что она делает:
                //Завершает процесс инициализации актора.
                //Регистрирует актора в мире.Вызывает PostActorCreated()(если переопределен).
                //Вызывает ExecuteConstruction()(что вызовет OnConstruction() в C++ и Construction Script в Blueprint).
                //Вызывает PostInitializeComponents().
                //Вызывает BeginPlay().
                //После вызова этой функции актор считается полностью “живым” и активным в мире.
                //
                //Payload.InitialTransform: В FinishSpawning также передается трансформация.
                Geometry->FinishSpawning(Payload.InitialTransform);
            }
        }
    }
}

// Called every frame
void AGeometryHubTestingActor::Tick(float DeltaTime)
{
    Super::Tick(DeltaTime);
}
```

```cpp
#include "Engine/World.h"
```

```cpp
	UWorld* World = GetWorld();
```

Создается пустой чистый актор. Который может вызывать другие акторы макросом SpawnActor

![[Pasted image 20241130020940.png]]
Здесь создается 10 акторов ABaseGeometryActor, им присваивается положение. А так же создается каст до них 

Так же дальше указыается их движение и состояние различное при котором они либо двигаются, либо стоят

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

Так же для получения движения, был сделан до заголовочного файла ABaseGeometryActor

```cpp
	void SetGeometryData(const FGeometryData& Data) { GeometryData = Data; }
```

![[Pasted image 20241130023230.png]]

Можно во вьюпорте создать несколько различных способов присвоить актор для вызова. GeometryHubActor.h

```cpp
#include "BaseGeometryActor.h"

	UPROPERTY(EditAnywhere)
	TSubclassOf<ABaseGeometryActor> GeometryClass;
		
	UPROPERTY(EditAnywhere)
	UClass* Class;

	UPROPERTY(EditAnywhere)
	ABaseGeometryActor* GeometryObject;
```

![[Pasted image 20241130024534.png]]

![[Pasted image 20241130024635.png]]
![[Pasted image 20241130024643.png]]
![[Pasted image 20241130024651.png]]



Так же существует второй способ создания актора, запустив сначала выполнение присвоение настроек, а потом бегин плей самого актора. 

SpawnActorDeferred

```cpp
		for (int32 i = 0; i < 10; ++i)
		{
			const FTransform GeometryTransform = FTransform(FRotator::ZeroRotator, FVector(0.0f, 300.0f * i, 700.0f));
			ABaseGeometryActor* Geometry = World->SpawnActorDeferred<ABaseGeometryActor>(GeometryClass, GeometryTransform);

			if (Geometry)
			{
				FGeometryData Data;
				Data.Color = FLinearColor::MakeRandomColor();
				Geometry->SetGeometryData(Data);
				Geometry->FinishSpawning(GeometryTransform)
			}
		}
```

В geometryHubActor.h

Позволяет создать аррей из объектов 

```cpp
USTRUCT(BlueprintType)
struct FGeometryPayload
{
	GENERATED_USTRUCT_BODY()

	UPROPERTY(EditAnywhere)
	TSubclassOf<ABaseGeometryActor> GeometryClass;

	UPROPERTY(EditAnywhere)
	FGeometryData Data;

	UPROPERTY(EditAnywhere)
	FTransform InitialTransform;
};
```

```cpp
	UPROPERTY(EditAnywhere)
	TArray<FGeometryPayload> GeometryPayloads;
```

.cpp

```Cpp

void AGeometryHubActor::DoActorSpawn1()
{
	UWorld* World = GetWorld();
	if (World)
	{
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
	}
}

void AGeometryHubActor::DoActorSpawn2()
{
	UWorld* World = GetWorld();
	if (World)
	{
		for (int32 i = 0; i < 10; ++i)
		{
			const FTransform GeometryTransform = FTransform(FRotator::ZeroRotator, FVector(0.0f, 300.0f * i, 700.0f));
			ABaseGeometryActor* Geometry = World->SpawnActorDeferred<ABaseGeometryActor>(GeometryClass, GeometryTransform);

			if (Geometry)
			{
				FGeometryData Data;
				Data.Color = FLinearColor::MakeRandomColor();
				Geometry->SetGeometryData(Data);
				Geometry->FinishSpawning(GeometryTransform);
			}
		}
	}
}

void AGeometryHubActor::DoActorSpawn3()
{
	UWorld* World = GetWorld();
	if (World)
	{
		for (const FGeometryPayload Payload : GeometryPayloads)
		{
			ABaseGeometryActor* Geometry = World->SpawnActorDeferred<ABaseGeometryActor>(Payload.GeometryClass, Payload.InitialTransform);

			if (Geometry)
			{
				Geometry->SetGeometryData(Payload.Data);
				Geometry->FinishSpawning(Payload.InitialTransform);
			}
		}
	}
}
```

![[Pasted image 20241130031543.png]]

## UFUNCTION, вызов функции в блюпринт графе 
---
https://dev.epicgames.com/documentation/en-us/unreal-engine/ufunctions-in-unreal-engine?application_version=5.4

путем вызова break мы можем получать доступ ко всем полям структуры, кроме поля timer rate, так как для него не указали BlueprintReadWrite

![[Pasted image 20241211123548.png]]

![[Pasted image 20250513055214.png]]

```cpp
USTRUCT(BlueprintType)
struct FGeometrydataTestingActor
{
    GENERATED_USTRUCT_BODY()

	//BlueprintReadWrite позволяет вытащить переменную в блюпринт граф

    //Две переменные, отвечающие за амплитуду и частоту колебаний для логики движения объектов
    UPROPERTY(EditAnywhere, BlueprintReadWrite,Category = "Movement")
    float Amplitude = 50.0f;

    UPROPERTY(EditAnywhere, BlueprintReadWrite, Category = "Movement")
    float Frequency = 2.0f;

    //Создание переменной MoveType типа enum MovementType
    //который содержит переходные значия STATIC, SIN
    UPROPERTY(EditAnywhere, BlueprintReadWrite, Category = "Movement")
    EMovementTypeTestingActor MoveType = EMovementTypeTestingActor::STATIC;

    //Цвет меша
    UPROPERTY(EditAnywhere, BlueprintReadWrite, Category = "Design")
    FLinearColor Color = FLinearColor::Black;

    //Таймер 
    UPROPERTY(EditAnywhere, Category = "Design")
    float TimerRate = 3.0f;
};

UCLASS()
class GAMEC_API ATestingNewActor : public AActor
{
    GENERATED_BODY()

public:
    // Sets default values for this actor's properties
    ATestingNewActor();

    //Добавление статик компонета статик меша к актору
    //Принимает по указателю на BaseMesh
    UPROPERTY(EditAnywhere)
    UStaticMeshComponent* BaseMesh;

    //позволяет вызвать функцию из блюпринт графа 
    UFUNCTION(BlueprintCallable)
    FGeometrydataTestingActor GetGeometryData() const {return GeometryData;}

protected:
    // Called when the game starts or when spawned
    virtual void BeginPlay() override;

    //переменная хранящая в себе структуру
    //В ней хранятся для вывода другие переменные
    UPROPERTY(EditAnywhere,BlueprintReadWrite,  Category = "GeometryData")
    FGeometrydataTestingActor GeometryData;
    
public:
    // Called every frame
    virtual void
    Tick(float DeltaTime) override;

private:
};

```

Позволяет все переменные GeometryData вытащить в блюпринт 

```cpp

	UFUNCTION(BlueprintCallable)
	
	BlueprintReadWrite
	
```

```cpp
USTRUCT(BlueprintType)
struct FGeometryData
{
	GENERATED_USTRUCT_BODY()

	UPROPERTY(EditAnywhere, BlueprintReadWrite, Category = "Movement")
	float Amplitude = 50.0f;

	UPROPERTY(EditAnywhere, BlueprintReadWrite, Category = "Movement")
	float Frequency = 2.0f;

	UPROPERTY(EditAnywhere, BlueprintReadWrite, Category = "Movement")
	EMovementType MoveType = EMovementType::Static;

	UPROPERTY(EditAnywhere, BlueprintReadWrite, Category = "Design")
	FLinearColor Color = FLinearColor::Black;

	UPROPERTY(EditAnywhere, Category = "Design")
	float TimerRate = 1.0f;
};

public:	
	// Sets default values for this actor's properties
	ABaseGeometryActor();

	UPROPERTY(VisibleAnywhere)
		UStaticMeshComponent* BaseMesh;

	void SetGeometryData(const FGeometryData& Data) { GeometryData = Data; }

	UFUNCTION(BlueprintCallable)
	FGeometryData GetGeometryData() const {return GeometryData; }
```

## Делегаты. Разрушение объекта. Destroy
---

Delegate documentation
https://dev.epicgames.com/documentation/en-us/unreal-engine/delegates-and-lamba-functions-in-unreal-engine?application_version=5.4

Позволяют хранить в себе метод с определенной сигнатурой, произвольного класса и вызывать когда необходимо 

Делегат это тот же евент диспатчер 

Делегаты в Unreal Engine (и в C++ в целом, хотя UE имеет свою мощную реализацию) — это очень важный механизм, который позволяет **безопасно вызывать функции объекта, не зная тип этого объекта или конкретную функцию во время компиляции.**

Проще говоря, это **способ для одного объекта сказать другому: “Когда у тебя произойдет это событие, пожалуйста, вызови вот эту мою функцию”.**

Представь себе это как подписку на уведомления или назначение ответственного.

**Основные концепции:**

1. **Указатель на функцию, но безопаснее и гибче:** Делегат, по сути, хранит указатель на функцию-член какого-либо объекта (или на глобальную/статическую функцию). В отличие от сырых указателей на функции C++, делегаты в UE:
    
    - **Типобезопасны:** Компилятор проверяет, что сигнатура функции (тип возвращаемого значения и типы параметров) соответствует сигнатуре делегата.
    - **Знают об объекте:** Делегат, связанный с функцией-членом, знает, на каком объекте эту функцию вызывать.
    - **Проверка на валидность:** Можно проверить, связан ли делегат с какой-либо функцией, перед тем как его вызвать (`IsBound()`, `ExecuteIfBound()`).
    - **Динамическое связывание/отвязывание:** Функции можно привязывать и отвязывать от делегата во время выполнения.
2. **Механизм обратного вызова (Callback):** Делегаты часто используются для реализации колбэков. Один объект может передать делегат другому, и второй объект вызовет этот делегат, когда определенное событие произойдет.
    
3. **Система событий:** Делегаты лежат в основе системы событий Unreal Engine.
    

**Зачем нужны делегаты?**

- **Декаплинг (Decoupling) / Слабая связанность:** Объект, который “вещает” (broadcasts) событие через делегат, не должен ничего знать о том, кто на это событие подписан и какие функции будут вызваны. Это делает код более модульным и гибким. Например, кнопка не знает, что должно произойти при ее нажатии; она просто сообщает “Меня нажали!”, а другие системы, подписанные на этот делегат, реагируют.
- **Уведомления об изменениях:** Когда состояние одного объекта меняется (например, здоровье персонажа), он может уведомить об этом другие заинтересованные объекты (например, UI для обновления полоски здоровья, звуковую систему для проигрывания звука) через делегат.
- **Гибкая настройка поведения:** Можно изменять поведение объекта, привязывая разные функции к его делегатам.

**Типы делегатов в Unreal Engine:**

В UE существует несколько типов делегатов, каждый для своих нужд:

1. **Одноадресные (Single-cast) делегаты:**
    
    - Может быть привязана только **одна** функция.
    - Если привязать новую функцию, старая отвяжется.
    - Могут возвращать значение.
    - Макросы для объявления: `DECLARE_DELEGATE...` (например, `DECLARE_DELEGATE(FMyDelegateName)` или `DECLARE_DELEGATE_RetVal_OneParam(float, FMyDelegateName, int32)`)
    - Для вызова: `Execute()`, `ExecuteIfBound()`.
    - 
2. **Многоадресные (Multicast) делегаты:**
    
    - Может быть привязано **несколько** функций.
    - При вызове делегата будут вызваны все привязанные функции (в порядке их добавления).
    - **Не могут возвращать значение** (потому что непонятно, значение какой из функций возвращать).
    - Макросы для объявления: `DECLARE_MULTICAST_DELEGATE...` (например, `DECLARE_MULTICAST_DELEGATE(FMyMulticastDelegateName)` или `DECLARE_MULTICAST_DELEGATE_OneParam(FMyMulticastDelegateName, float)`)
    - Для вызова: `Broadcast()`.
    - Для привязки/отвязки: `Add...()`, `Remove...()`.
3. **Динамические (Dynamic) делегаты:**
    
    - Могут быть **сериализованы** (сохранены и загружены) и **безопасно использоваться с Blueprints**.
    - Привязка функций происходит по их имени (FName), что делает их медленнее обычных делегатов.
    - Могут быть как одноадресными, так и многоадресными.
    - Макросы для объявления: `DECLARE_DYNAMIC_DELEGATE...`, `DECLARE_DYNAMIC_MULTICAST_DELEGATE...`
    - Функции, привязываемые к динамическим делегатам, должны быть помечены как `UFUNCTION()`.

![[Pasted image 20250513064502.png]]

![[Pasted image 20250513070804.png]]


![[Pasted image 20241211181650.png]]

LogForTestingNewActor: Display: TimerCount: 5, Color to set  up: (R=1.000000,G=0.164062,B=0.000000,A=1.000000)
LogHubActor: Warning: Actor name: BP_Cube_MyTestingNewActor_C_0 Color: (R=1.000000,G=0.164062,B=0.000000,A=1.000000)
LogBlueprintUserMessages: [BP_Cube_MyTestingNewActor_C_0] BP_Cube_MyTestingNewActor_C_0 = (R=1.000000,G=0.164062,B=0.000000,A=1.000000)
LogForTestingNewActor: Display: Timer has been stopped!
LogHubActor: Error: Timer finished: BP_Cube_MyTestingNewActor_C_0
LogHubActor: Error: Cast success, amplitude 50.000000
LogForTestingNewActor: Error: Actor has been destroyed

.h

```cpp

//объявление делегата
//Все делегаты назавния объявляются с большой буквы F
DECLARE_DYNAMIC_MULTICAST_DELEGATE_TwoParams(FOnColorChangedTestingNewActor, const FLinearColor&, Color, const FString&, Name);

//так как этот делегат только в с++, мы можем не указывать имя актора в блюпринтах
DECLARE_MULTICAST_DELEGATE_OneParam(FOnTimerFinishedTestingNewActor, AActor*);

UCLASS()
class GAMEC_API ATestingNewActor : public AActor
{
    GENERATED_BODY()

public:
    // Sets default values for this actor's properties
    ATestingNewActor();

    //создание делегатов
    //так же что можно было подписаться на него в блюпринтах
    UPROPERTY(BlueprintAssignable)
    FOnColorChangedTestingNewActor OnColorChanged;

    FOnTimerFinishedTestingNewActor OnTimerFinished;

protected:
    // Called when the game starts or when spawned
    virtual void BeginPlay() override;


    //виртуальная функция конца 
    virtual void EndPlay(const EEndPlayReason::Type EndPlayReason) override;

```

```CPP
UCLASS() class GAMEC_API AGeometryHubTestingActor : public AActor
{
    GENERATED_BODY()

public:
    // Sets default values for this actor's properties
    AGeometryHubTestingActor();

private:
	//Функция на срабатывание делегатов
    //Функции которые мы добавляем к динамическим дилегатам, должны быть помечены UFUNCTION
    UFUNCTION()
    void OnColorChanged(const FLinearColor& Color, const FString& Name);

    void OnTimerFinished(AActor* Actor);
};
```

```cpp

DEFINE_LOG_CATEGORY_STATIC(LogHubActor, All, All);


//функция при срабатывании делегатов
void AGeometryHubTestingActor::OnColorChanged(const FLinearColor& Color, const FString& Name)
{
    UE_LOG(LogHubActor, Warning, TEXT("Actor name: %s Color: %s"), *Name, *Color.ToString());
}

void AGeometryHubTestingActor::OnTimerFinished(AActor* Actor)
{
    if (!Actor) return;
    UE_LOG(LogHubActor, Error, TEXT("Timer finished: %s"), *Actor->GetName());

    //Даункастинг, преобразует указатель на базовый класс на указатель на класс наследника
    ATestingNewActor* Geometry = Cast<ATestingNewActor>(Actor);
    if (!Geometry) return;

    UE_LOG(LogHubActor, Error, TEXT("Cast success, amplitude %f"), Geometry->GetGeometryData().Amplitude);

    //удаление актора со сцены
    Geometry->Destroy();

    //через 2 сек вызовется destroy
    //Geometry->SetLifeSpan(2.0f);
}

```

```cpp
void ATestingNewActor::OnTimerFired()
{
    if (++TimerCount <= MaxTimerCount)
    {
        const FLinearColor NewColor = FLinearColor::MakeRandomColor();

        //TimerCount передается по значению, потому что спецификатор %i требует значение типа int.
        //*NewColor.ToString() передается как указатель, потому что спецификатор % s требует указатель на строку типа const TCHAR *.
        UE_LOG(LogForTestingNewActor, Display, TEXT("TimerCount: %i, Color to set  up: %s"), TimerCount, *NewColor.ToString());
        SetColor(NewColor);
        
        //Вызов делегата, говорит "Я Сработал!"
        //Когда где либо кто то получает сообщение что тут сработал делегат 
        //начинает логика из него 
        OnColorChanged.Broadcast(NewColor, GetName());
    }
    else
    {
        UE_LOG(LogForTestingNewActor, Display, TEXT("Timer has been stopped!"));

        //остановка таймера, какой таймер остановить
        GetWorldTimerManager().ClearTimer(TimerHandle);

        //Вызов второго делегата, когда таймер закончил работу
        OnTimerFinished.Broadcast(this);
    }
}

void ATestingNewActor::EndPlay(const EEndPlayReason::Type EndPlayReason)
{
    UE_LOG(LogForTestingNewActor, Error, TEXT("Actor has been destroyed"));
    Super::EndPlay(EndPlayReason);
}

```

baseGeometryActor.h

```cpp
DECLARE_DYNAMIC_MULTICAST_DELEGATE_TwoParams(FOnColorChanged, const FLinearColor&, Color, const FString&, Name);
DECLARE_MULTICAST_DELEGATE_OneParam(FOnTimerFinished, AActor*);

public:	
	// Sets default values for this actor's properties
	ABaseGeometryActor();
	
	UPROPERTY(BlueprintAssignable)
	FOnColorChanged OnColorChanged;

	FOnTimerFinished OnTimerFinished;

```

GeometryHubActor.h

```cpp
private:

	UFUNCTION()
	void OnColorChanged(const FLinearColor& Color, const FString& Name);

	void OnTimerFinished(AActor* Actor);
```

BaseGeometryActor.cpp

```cpp

void ABaseGeometryActor::OnTimerFired()
{
	if (++TimerCount <= MaxTimerCount)
	{
		const FLinearColor NewColor = FLinearColor::MakeRandomColor();
		UE_LOG(LogBaseGeometry, Display, TEXT("TimerCount: %i, Color to set up: %s"), TimerCount, *NewColor.ToString());
		SetColor(NewColor);
		OnColorChanged.Broadcast(NewColor, GetName());
	}
	else
	{
		UE_LOG(LogBaseGeometry, Warning, TEXT("Timer has been stopped!"));
		GetWorldTimerManager().ClearTimer(TimerHandle);
		OnTimerFinished.Broadcast(this);
	}
}


```

GeometryHubActor.cpp

```cpp
void AGeometryHubActor::BeginPlay()
{
	Super::BeginPlay();

	//DoActorSpawn1();
	//DoActorSpawn2();
	DoActorSpawn3();

}


void AGeometryHubActor::DoActorSpawn3()
{
	UWorld* World = GetWorld();
	if (World)
	{
		for (const FGeometryPayload Payload : GeometryPayloads)
		{
			ABaseGeometryActor* Geometry = World->SpawnActorDeferred<ABaseGeometryActor>(Payload.GeometryClass, Payload.InitialTransform);

			if (Geometry)
			{
				Geometry->SetGeometryData(Payload.Data);
				Geometry->OnColorChanged.AddDynamic(this, &AGeometryHubActor::OnColorChanged);
				Geometry->OnTimerFinished.AddUObject(this, &AGeometryHubActor::OnTimerFinished);
				Geometry->FinishSpawning(Payload.InitialTransform);
			}
		}
	}
}

void AGeometryHubActor::OnColorChanged(const FLinearColor& Color, const FString& Name)
{
	UE_LOG(LogGeometryHub, Warning, TEXT("Actor name: %s Color %s"), *Name, *Color.ToString());
}

void AGeometryHubActor::OnTimerFinished(AActor* Actor)
{
	if (!Actor) return;
	UE_LOG(LogGeometryHub, Error, TEXT("Timer finished: %s"), *Actor->GetName());

	ABaseGeometryActor* Geometry = Cast<ABaseGeometryActor>(Actor);
	if (!Geometry) return;

	UE_LOG(LogGeometryHub, Display, TEXT("Cast is success: amplitude %f"), Geometry->GetGeometryData().Amplitude);

	Geometry->Destroy();
	//Geometry->SetLifeSpan(2.0f)
}
```

## GameModeBase
---
### Gameplay Framework

https://dev.epicgames.com/documentation/en-us/unreal-engine/gameplay-framework-in-unreal-engine?application_version=5.4

![[Pasted image 20250513202121.png]]
### Gamemode

Настройка основного GameModeBase и замена там Pawn. Для управления в стороны

gameCGameModeBase.cpp

```cpp
// Copyright Epic Games, Inc. All Rights Reserved.


#include "gameCGameModeBase.h"
//подключение класса pawn 
#include "SandboxPawn.h"
#include "SandboxPlayerController.h"

AgameCGameModeBase::AgameCGameModeBase()
{
	//переопределяем дефолт классы 
	DefaultPawnClass = ASandboxPawn::StaticClass();
	PlayerControllerClass = ASandboxPlayerController::StaticClass();
}
```

gameCGameModeBase.h

```cpp
// Copyright Epic Games, Inc. All Rights Reserved.

#pragma once

#include "CoreMinimal.h"
#include "GameFramework/GameModeBase.h"
#include "gameCGameModeBase.generated.h"

/**
 * 
 */
UCLASS()
class GAMEC_API AgameCGameModeBase : public AGameModeBase
{
	GENERATED_BODY()
	
	public:
		//конструктор для гейммода 
		AgameCGameModeBase();
};

```

Если провалиться через .h файл в gamemode, в затем в любую функцию то можно найти как засетаплены все установки на переопределение 


```cpp
AGameModeBase::AGameModeBase(const FObjectInitializer& ObjectInitializer)
	: Super(ObjectInitializer.DoNotCreateDefaultSubobject(TEXT("Sprite")))
{
	bNetLoadOnClient = false;
	bPauseable = true;
	bStartPlayersAsSpectators = false;

	DefaultPawnClass = ADefaultPawn::StaticClass();
	PlayerControllerClass = APlayerController::StaticClass();
	PlayerStateClass = APlayerState::StaticClass();
	GameStateClass = AGameStateBase::StaticClass();
	HUDClass = AHUD::StaticClass();
	GameSessionClass = AGameSession::StaticClass();
	SpectatorClass = ASpectatorPawn::StaticClass();
	ReplaySpectatorPlayerControllerClass = APlayerController::StaticClass();
	ServerStatReplicatorClass = AServerStatReplicator::StaticClass();
}
```

![[Pasted image 20241212162503.png]]

## Mapping, Action Mapping, Axis Mapping

![[Pasted image 20241212163003.png]]

При action mapping - единичный тик 
при axis mapping - тик пока кнопка нажата 

scale позволяет инвертировать зажатие клавиши 

## Pawn

pawn documentation
https://dev.epicgames.com/documentation/en-us/unreal-engine/pawn-in-unreal-engine?application_version=5.4

Bind documentation 
https://www.geeksforgeeks.org/bind-function-placeholders-c/

"This" documentation
https://en.cppreference.com/w/cpp/language/this

Input documentation
https://dev.epicgames.com/documentation/en-us/unreal-engine/input-in-unreal-engine?application_version=5.4

SandboxPawn.h
```cpp
// Fill out your copyright notice in the Description page of Project Settings.

#pragma once

#include "CoreMinimal.h"
#include "GameFramework/Pawn.h"
#include "SandboxPawn.generated.h"

class UCameraComponent;

UCLASS()
class GAMEC_API ASandboxPawn : public APawn
{
	GENERATED_BODY()

public:
	// Sets default values for this pawn's properties
	ASandboxPawn();

	//создание переменной, корневой компонент
	//Содержит в себе только трансформацию в мире, к нему можно при атачить другие компоненты 
	UPROPERTY(VisibleAnywhere)
	USceneComponent* SceneComponent;

	//добавление статик меша
	UPROPERTY(VisibleAnywhere)
	UStaticMeshComponent* StaticMeshComponent;

	UPROPERTY(VisibleAnywhere)
	UCameraComponent* CameraComponent;

	//Скорость
	UPROPERTY(EditAnywhere)
	float Velocity = 300.0f;

	//виртуальные функции, получения контроля над pawn
	virtual void PossessedBy(AController* NewController) override;
	virtual void UnPossessed() override;

protected:
	// Called when the game starts or when spawned
	virtual void BeginPlay() override;

public:	
	// Called every frame
	virtual void Tick(float DeltaTime) override;

	// Called to bind functionality to input
	virtual void SetupPlayerInputComponent(class UInputComponent* PlayerInputComponent) override;

private:
	//Вектор скорости pawn 
	//по умолчанию он нулевой
	FVector VelocityVector = FVector::ZeroVector;

	//Функции движения вперед назад, принимают параметр
	void MoveForward(float Amount);
	void MoveRight(float Amount);
};

```

SandboxPawn.cpp

```cpp
// Fill out your copyright notice in the Description page of Project Settings.


#include "SandboxPawn.h"
//объявление заголовочный файлов для использования 
#include "Components/InputComponent.h"
#include "Components/StaticMeshComponent.h"
#include "Camera/CameraComponent.h"

//собственная категория логирования для pawn 
DEFINE_LOG_CATEGORY_STATIC(LogSandboxPawn, All, All)

// Sets default values
ASandboxPawn::ASandboxPawn()
{
	// Set this pawn to call Tick() every frame.  You can turn this off to improve performance if you don't need it.
	PrimaryActorTick.bCanEverTick = true;

	//Определение корневого элемента, применение к нему логики
	SceneComponent = CreateDefaultSubobject<USceneComponent>("SceneComponent");
	SetRootComponent(SceneComponent);

	//добавление статик меш компонента  класс 
	//атачим к сцене, базовой трансформации сцены
	StaticMeshComponent = CreateDefaultSubobject<UStaticMeshComponent>("StaticMeshComponent");
	StaticMeshComponent->SetupAttachment(GetRootComponent());
	
	//поменять трансформацию относительно родительского компонента 
	//StaticMeshComponent->SetRelativeLocation();

	//добавление камеры
	//атачим к сцене, базовой трансформации сцены
	CameraComponent = CreateDefaultSubobject<UCameraComponent>("CameraComponent");
	CameraComponent->SetupAttachment(GetRootComponent());
}

// Called when the game starts or when spawned
void ASandboxPawn::BeginPlay()
{
	Super::BeginPlay();
	
}

// Called every frame
void ASandboxPawn::Tick(float DeltaTime)
{
	Super::Tick(DeltaTime);

	//на функцию tick мы изменяем положение нашего pawn в зависимости от вектора скорости
	//если вектор 0, то вычисления можно не делать
	//if (!VelocityVector.IsZero() &&IsControlled) проверки на то управляется ли кем то или нет 
	if (!VelocityVector.IsZero())
	{
		//локальная константа, в которой хранится новое положения для pawn
		//вычисляется она по формулен равномерного прямолинейного движения 
		//r = r0 + vt
		const FVector NewLocation = GetActorLocation() + Velocity * DeltaTime * VelocityVector;
		SetActorLocation(NewLocation);

		//второй способ вместо &&IsControlled, останавливать объект. 
		//обнулять вектор скорости
		VelocityVector = FVector::ZeroVector;
	}
}

// Called to bind functionality to input
//бинд функций для управления
void ASandboxPawn::SetupPlayerInputComponent(UInputComponent* PlayerInputComponent)
{
	Super::SetupPlayerInputComponent(PlayerInputComponent);

	//проверка на нулевой указатель
	if (PlayerInputComponent)
	{
		//"бинд маппинга" "указатель на объект" "ссылка на функцию, которые мы вызываем во время работы"
		PlayerInputComponent->BindAxis("MoveForward", this, &ASandboxPawn::MoveForward);
		PlayerInputComponent->BindAxis("MoveRight", this, &ASandboxPawn::MoveRight);
	}
}

void ASandboxPawn::MoveForward(float Amount)
{
	//UE_LOG(LogSandboxPawn, Display, TEXT("Move forward: %f"), Amount)
	//изменение вектора скорости в зависимости от значения
	//значения будут -1, 0, 1
	VelocityVector.X = Amount;
}

void ASandboxPawn::MoveRight(float Amount)
{
	//UE_LOG(LogSandboxPawn, Display, TEXT("Move right: %f"), Amount)
	VelocityVector.Y = Amount;
}

//Получение контроля над pawn
void ASandboxPawn::PossessedBy(AController* NewController)
{
	Super::PossessedBy(NewController);

	//проверка на нулевой указатель
	if (!NewController) return;
	UE_LOG(LogSandboxPawn, Error, TEXT("%s possessed %s"), *GetName(), *NewController->GetName());
}

void ASandboxPawn::UnPossessed()
{
	Super::UnPossessed();

	UE_LOG(LogSandboxPawn, Warning, TEXT("%s unpossessed"), *GetName());
}

```

## Player Controller
---

https://dev.epicgames.com/documentation/en-us/unreal-engine/player-controllers-in-unreal-engine?application_version=5.4

![[Pasted image 20241212233801.png]]

SandboxPlayerController.h

```cpp
// Fill out your copyright notice in the Description page of Project Settings.

#pragma once

#include "CoreMinimal.h"
#include "GameFramework/PlayerController.h"
#include "SandboxPlayerController.generated.h"

/**
 * 
 */
UCLASS()
class GAMEC_API ASandboxPlayerController : public APlayerController
{
	GENERATED_BODY()
	

protected:
	//переопределение класса управления
	virtual void SetupInputComponent() override;
	virtual void BeginPlay() override;

private:
	//Массив со всеми pawn по которым мы можем переключаться
	UPROPERTY()
	TArray<AActor*> Pawns;

	//инднекс текущего индекса pawn 
	int32 CurrentPawnIndex = 0;

	void ChangePawn();
};

```

SandboxPlayerController.cpp
```cpp
// Fill out your copyright notice in the Description page of Project Settings.


#include "SandboxPlayerController.h"
#include "Components/InputComponent.h"
//доп класс для UGameplaySatics
#include "Kismet/GameplayStatics.h"
#include "SandboxPawn.h"

DEFINE_LOG_CATEGORY_STATIC(LogSandboxPlayerController, All, All)

//переопределенная функция при нажатии клавиши
void ASandboxPlayerController::SetupInputComponent()
{
	Super::SetupInputComponent();

	//проверка на нулевой указатель
	if (InputComponent)
	{
		//запуск действий при нажатии клавиши 
		InputComponent->BindAction("ChangePawn", IE_Pressed, this, &ASandboxPlayerController::ChangePawn);
	}
}

void ASandboxPlayerController::BeginPlay()
{
	Super::BeginPlay();

	//получение всех акторов со сцены ASandboxPawn
	//может получить всех акторов в мире ASandboxPawn 
	//или получить доступ к акторам у SandboxPlayerController передав туда ключевое слово this
	UGameplayStatics::GetAllActorsOfClass(GetWorld(), ASandboxPawn::StaticClass(), Pawns);
}

//функция изменения pawn
void ASandboxPlayerController::ChangePawn()
{
	//количество элементов в массиве больше 1 
	if (Pawns.Num() <= 1) return;

	//изменение pawn на одного из тех, кто находится на сцене
	//указатель на pawn из массива
	//каждый раз будет получать новый pawn, меняя индекс массива
	ASandboxPawn* CurrentPawn = Cast<ASandboxPawn>(Pawns[CurrentPawnIndex]);
	
	//прибавление для перехода на след pawn
	CurrentPawnIndex = (CurrentPawnIndex + 1) % Pawns.Num();
	if (!CurrentPawn) return;

	UE_LOG(LogSandboxPlayerController, Error, TEXT("Change player pawn"));
	Possess(CurrentPawn);
}

```

SandboxPawn.h

```cpp
	virtual void PossessedBy(AController* NewController) override;
	virtual void UnPossessed() override;
```

SandboxPawn.cpp
```cpp
void ASandboxPawn::PossessedBy(AController* NewController)
{
	Super::PossessedBy(NewController);

	if (!NewController) return;
	UE_LOG(LogSandboxPawn, Error, TEXT("%s possessed %s"), *GetName(), *NewController->GetName());
}

void ASandboxPawn::UnPossessed()
{
	Super::UnPossessed();

	UE_LOG(LogSandboxPawn, Warning, TEXT("%s unpossessed"), *GetName());
}
```

```
//
//	EInputEvent
//
UENUM( BlueprintType, meta=(ScriptName="InputEventType"))
enum EInputEvent
{
	IE_Pressed              =0,
	IE_Released             =1,
	IE_Repeat               =2,
	IE_DoubleClick          =3,
	IE_Axis                 =4,
	IE_MAX                  =5,
};
```

отключает спавн AI автоматически для неуправляемых pawn

![[Pasted image 20250513193403.png]]

## GetAllActorsOfClass

```cpp
//доп класс для UGameplaySatics
#include "Kismet/GameplayStatics.h"

void ASandboxPlayerController::BeginPlay()
{
	Super::BeginPlay();

	//получение всех акторов со сцены
	UGameplayStatics::GetAllActorsOfClass(GetWorld(), ASandboxPawn::StaticClass(), Pawns);
}
```

## Обзор основных классов Unreal 

![[Pasted image 20250513173222.png]]

![[Pasted image 20250513174305.png]]

```
					UObject 
					/      \ 
				   /        \
			AActor         UActorComponent 
			   |                 | 
			APawn           USceneComponent
				|         UStaticMeshComponent 
		   ACharacter	   UCameraComponent 
								 ...
```

От `UObject` напрямую наследуется **огромное количество** классов, представляющих самые разные сущности в движке. Вот несколько важных категорий и примеров:

1. **Ассеты (Assets):** Классы, представляющие ресурсы, которые ты видишь в Content Browser. Им нужны свойства `UObject` для управления памятью, сериализации и отображения в редакторе.
    
    - `UStaticMesh`: Представляет статическую модель (сам ассет, не компонент на сцене).
    - `USkeletalMesh`: Представляет скелетную модель.
    - `UMaterialInterface`, `UMaterial`, `UMaterialInstance`: Представляют материалы и их экземпляры.
    - `UTexture`, `UTexture2D`: Представляют текстуры.
    - `UAnimSequence`, `UAnimMontage`, `UBlendSpace`: Представляют различные анимационные ассеты.
    - `USoundBase`, `USoundWave`, `USoundCue`: Представляют звуковые ассеты.
    - `UBlueprint`: Представляет сам ассет блюпринта.
    - `UDataTable`: Представляет таблицу данных.
    - `ULevel`: Представляет ассет уровня.
    - `UWorld`: Представляет загруженный мир/уровень (хотя часто с ним работают через `GetWorld()`, его класс наследуется от `UObject`).
2. **Объекты Пользовательского Интерфейса (UMG):**
    
    - `UWidget`: Базовый класс для всех элементов интерфейса UMG.
    - `UUserWidget`: Базовый класс для пользовательских виджетов, которые ты создаешь в редакторе UMG.
3. **Подсистемы Движка (Engine Subsystems):** Модульные классы, предоставляющие различную функциональность движка.
    
    - `UEngineSubsystem`
    - `UGameInstanceSubsystem`
    - `UWorldSubsystem`
    - `ULocalPlayerSubsystem`
4. **Основные Объекты Игры и Движка:**
    
    - `UGameInstance`: Объект, который существует на протяжении всей сессии игры (даже при смене уровней).
    - `UEngine`: Глобальный объект движка.
5. **Данные и Конфигурация:**
    
    - `UDataAsset`: Базовый класс для создания ассетов, содержащих только данные.
    - `UDeveloperSettings`: Для настроек проекта, доступных в Project Settings.
    - `UInputMappingContext`, `UInputAction`: Классы системы Enhanced Input.
6. **И многие другие…** Включая различные менеджеры, хелперы, структуры данных, которые используются внутри движка и которым нужны возможности `UObject`.
    

**Ключевая идея:**

Любому классу в Unreal Engine, которому требуется:

- Управление памятью через сборщик мусора (GC).
- Отражение (reflection) для доступа к свойствам и функциям во время выполнения (нужно для Blueprints, редактора, сети).
- Сериализация (сохранение/загрузка).
- Интеграция с редактором (отображение свойств в Details панели).
- Использование макросов `UPROPERTY()`, `UFUNCTION()`, `UCLASS()`, `USTRUCT()`, etc.

Так же pawn может управлять AI 

HUD - класс manages для widget 

Spectator class - это доп класс наблюдателя, нужен когда игрок больше не играет

Player state class - класс для хранения статистики игрока 

Game state class - для много пользовательской игры, через нее на сервер передаются данные о клиенте, о игровом процессе 

Game Instance Class - глобальный класс, который существует на протяжении всей игры 

![[Pasted image 20250513174711.png]]

![[Pasted image 20250513174751.png]]

## Modules, Targets, UnrealBuildTool
---
### GameName.Target.cs. UnrealBuildTool

Правила по которому будет собран проект при запуске игры. 

```cpp
// Copyright Epic Games, Inc. All Rights Reserved.

using UnrealBuildTool;
using System.Collections.Generic;

public class gameCTarget : TargetRules
{
	public gameCTarget( TargetInfo Target) : base(Target)
	{
		Type = TargetType.Game;
		DefaultBuildSettings = BuildSettingsVersion.V2;
		ExtraModuleNames.AddRange( new string[] { "gameC" } );
	}
}
```

Запускается специальная утилита. Запускает данную программу, которая вызывается. То есть мы можем собрать какой то файл, который будет вызывать эту программу

![[Pasted image 20250513194217.png]]

### Module

https://dev.epicgames.com/documentation/en-us/unreal-engine/module-properties-in-unreal-engine?application_version=5.4

Весь код движка состоит из модулей. Как кирпичики. В нем инкапсулирована какая то логика движка. ИИ, специфекты, интерефейс

Наш проект с игрой так же является модулем, который наследуется от ModuleRules

В списке PublicDependencyModuleNames в нем указаны от какие модулей будет зависеть запуск проекта. По умолчанию добавлены 4 модуля движка


![[Pasted image 20241214200746.png]]

В папке runtime лежат исходники движка и каждая папка является модулем 

![[Pasted image 20250513194635.png]]

В папке build можно посмотреть как происходит сборка модуля. Зависит от платформы

![[Pasted image 20250513194729.png]]

## GameName.h  | GameName.cpp


![[Pasted image 20250513194931.png]]

В этих файлах указывается основной игровой модуль. То есть сама игра может состоять из модулей

.h

```cpp
// Copyright Epic Games, Inc. All Rights Reserved.

#pragma once

#include "CoreMinimal.h"

```

.cpp

```cpp
// Copyright Epic Games, Inc. All Rights Reserved.

#include "gameC.h"
#include "Modules/ModuleManager.h"

IMPLEMENT_PRIMARY_GAME_MODULE( FDefaultGameModuleImpl, gameC, "gameC" );

```

### .uproject 

js file

Доп настройки игры и загрузка модулей, версии движка и описания

```cpp
{
	"FileVersion": 3,
	"EngineAssociation": "4.26",
	"Category": "",
	"Description": "",
	"Modules": [
		{
			"Name": "gameC",
			"Type": "Runtime",
			"LoadingPhase": "Default",
			"AdditionalDependencies": [
				"Engine"
			]
		}
	]
}
```

### Forward Declaration. Libraries. Precomiped headers. IWYU подход

https://dev.epicgames.com/documentation/en-us/unreal-engine/include-what-you-use-iwyu-for-unreal-engine-programming?application_version=5.4

Заранее процессировать группу файлов и потом вставлять готовый текст 

```cpp
// Copyright Epic Games, Inc. All Rights Reserved.

using UnrealBuildTool;

public class gameC : ModuleRules
{
	public gameC(ReadOnlyTargetRules Target) : base(Target)
	{
		//Precomiped headers usage 
		//значения при которых будут подключаться sharedpch файлы
		//не использовать 
		//PCHUsage = PCHUsageMode.NoPCHs; 
		PCHUsage = PCHUsageMode.UseExplicitOrSharedPCHs;
	
		PublicDependencyModuleNames.AddRange(new string[] { "Core", "CoreUObject", "Engine", "InputCore" });

		PrivateDependencyModuleNames.AddRange(new string[] {  });

		// Uncomment if you are using Slate UI
		// PrivateDependencyModuleNames.AddRange(new string[] { "Slate", "SlateCore" });
		
		// Uncomment if you are using online features
		// PrivateDependencyModuleNames.Add("OnlineSubsystem");

		// To include OnlineSubsystemSteam, add it to the plugins section in your uproject file with the Enabled attribute set to true
	}
}
```

Данный файл SharedPCHHeaderFile = "Public/EngineSharedPCH.h"; будет добавлен при компилиции модуля

![[Pasted image 20250513195752.png]]

В данном файле будут добавлены заголовки при процессировании, это файлы, код в которых меняется очень редко

![[Pasted image 20250513195848.png]]

### Поиск по документации 

https://dev.epicgames.com/documentation/en-us/unreal-engine/API/Runtime/Engine/Components/UStaticMeshComponent?application_version=5.5

![[Pasted image 20250513200600.png]]

![[Pasted image 20250513200617.png]]

### GameNameEditor.Target.cs.

https://dev.epicgames.com/documentation/en-us/unreal-engine/unreal-engine-build-tool-target-reference?application_version=5.4

Если мы хоти запустить игру под editor то используется editor таргет, если хотим создать stand alone то используется обычный 

Если мы хотим собрать серверную игру, то нужно будет вручную добавить Server.Target.cs

При компиляции наш код собирается в dll файлы

![[Pasted image 20250513202548.png]]

для каждого модуля тоже созданы dll файлы в  категории движка. Когда устанавливается анрил, на компьютер копируются заранее скомпилированные dll файлы в виде бинарных модулей. 

Когда мы хотим скомпилировать анрил из исходников, то компиляция модулей и создание dll происходит на нашей локальной машине 
 
![[Pasted image 20250513202616.png]]

## Макросы. Генерация кода 

### Генерация кода

В анриле реализована собственная reflection system или система рефлексии, которые могут отслеживать собственную структуру и поведение во время ее выполнения 

С помощью ее мы можем получать информацию о типах, вызывать функцию по имени, получать имена элементов, енамов, можем создать итератор, который будет обходить все имена структуры и получать какую то информацию, можем передать указатель на класс, объект которого мы хотим создать

Эдитор 
Сериализация кода - когда мы создаем какие то объекте во вьюпорте измеяем их, перезапускаем эдитор, все значения сохраняются. Так же есть работа с сетью 

### Шаблоны, templates

В данной папке лежат все шаблоны templates 

![[Pasted image 20250513203353.png]]

если мы откроем шаблон, то увидит файл в котором поля поставляются в нужные имена классов. И в результате создания всех переменных создается итоговый файл класса 

![[Pasted image 20250513203444.png]]

### Как происходит билд проекта 

Происходить парсинг, затем запускается специальная утилита, UnrealHeaderTool
это специльный генератор, который обрабатывает все макросы в нашем исходном коде 

![[Pasted image 20250513203614.png]]

Первое что он делает он просматривает все заголовочные файлы .h и ищет в них .generated.h
Это является маркером для unrealHeaderTool, он понимает что данный заголовочный файл нужно обработать. те в нем присутствует специфический анрил тип
 
Затем генератор проходит по всем enum. ustruct, class, upropetry, ufuction и генерирует дополнительный код, который необходим для reflection system. 

Часть кода попадает в generated.h Она не предназначена для чтения человеком. Но можно увидеть что создались обертки вокруг property. А если поискать член класса, который не является propetry (помеченный UPROPERTY) мы ничего не найдем, никакой доп код не был сгенерирован для него

![[Pasted image 20250513204052.png]]

По этому пути лежат сгенерированные файлы, помимо них генерируются так же .cpp файлы. Так же данные файлы не предназначены для чтения человеком. Знать что происходит внутри во время разработки не обязательно 

Так же их можно спокойно удалить, они пересоздаться с помощью unreal.headertool


![[Pasted image 20250513204242.png]]

### Макрос 

Макрос в программировании (и в C++ в частности) — это, по сути, **инструкция препроцессору, которая заменяет определенный идентификатор (имя макроса) на заданный код или выражение _до_ начала фактической компиляции программы.**

1. **Определение макроса:** Ты определяешь макрос с помощью директивы препроцессора `#define`.
    
    - **Простой макрос (объектный):** Заменяет имя на значение.
        
        ```c++
        #define PI 3.14159
        #define GREETING "Hello, World!"
        ```
        
    - **Функциональный макрос:** Может принимать аргументы и выглядит как функция, но это все еще текстовая подстановка.
        
        ```c++
        #define SQUARE(x) (x * x)
        #define MAX(a, b) ((a) > (b) ? (a) : (b))
        ```
        
2. **Препроцессинг:** Перед тем как компилятор начнет разбирать твой C++ код на инструкции для процессора, специальная программа – **препроцессор** – проходит по всему твоему коду.
    
3. **Подстановка:** Когда препроцессор встречает имя макроса, он заменяет это имя на тот текст (код), который был указан в определении макроса.
    
    - Если это функциональный макрос, аргументы также подставляются в тело макроса.
4. **Компиляция:** После того как препроцессор выполнил все замены, измененный код (уже без макросов, а с подставленным кодом) передается компилятору для обычной компиляции.

- **`UCLASS()`, `USTRUCT()`, `UENUM()`:** Эти макросы сообщают Unreal Header Tool (UHT), что нужно сгенерировать дополнительный код для системы отражения, сборки мусора, интеграции с Blueprints и т.д. для этих классов, структур и перечислений.
- **`UPROPERTY(...)`:** Сообщает UHT, что это свойство должно быть видимо для системы отражения, редактора, Blueprints, сети и т.д., в зависимости от параметров.
- **`UFUNCTION(...)`:** Аналогично для функций.
- **`GENERATED_BODY()`, `GENERATED_UCLASS_BODY()`, `GENERATED_USTRUCT_BODY()`:** Эти макросы вставляют код, сгенерированный UHT, в твои классы и структуры.
- **`UE_LOG(...)`:** Макрос для логирования.
- **`check(...)`, `ensure(...)`:** Макросы для проверок и ассертов.
- **`TEXT(...)`:** Макрос для создания строковых литералов, совместимых с разными кодировками символов, используемыми в UE.
- **`_API` макросы (например, `MYPROJECT_API`):** Используются для экспорта символов из DLL, чтобы их можно было использовать в других модулях.

### Макрос. NAMEGAME_API

если пройти по нему, в нем есть другой макрос, который имеет значение компиляции под разные платформы

![[Pasted image 20250513204514.png]]

экспорт под windows
что означает что наш класс может быть экспортирован как dll файл 

![[Pasted image 20250513204608.png]]

Если проект не компилируется, можно перегенировать stl файл 

так же если при начале визаул не понимает какой проект является main 

![[Pasted image 20250513204912.png]]


## Garbage Collector
---
Unreal Object Handling

https://dev.epicgames.com/documentation/en-us/unreal-engine/unreal-object-handling-in-unreal-engine?application_version=5.4

Это специальный процесс, который очищает память. Когда актор или компонент, все указатели и которые видны в reflection system анрила, те UPROPERTY автоматически зануляться 


![[Pasted image 20250513222456.png]]

Start

![[Pasted image 20241214221122.png]]

Pressed Enter

![[Pasted image 20241214221133.png]]

Pressed Tab

![[Pasted image 20241214221149.png]]

GeometryHubActor.h

```cpp

private:
	//этот лог не будет собран сборщиком мусора, так как он не относится к макросу 
	//uproperty не помечен им. Как умным указателем 
	ABaseGeometryActor* NonePropertyActor;
	
	UPROPERTY()
	ABaseGeometryActor* PropertyActor;
	
	void DoActorSpawn4();
};
```

GeometryHubActor.cpp

```cpp
// Called when the game starts or when spawned
void AGeometryHubActor::BeginPlay()
{
	Super::BeginPlay();
	
	DoActorSpawn4();
}

void AGeometryHubActor::DoActorSpawn4()
{
	if (!GetWorld()) return;

	FTransform GeometryTransform = FTransform(FRotator::ZeroRotator, FVector(700.0f, 300.0f, 300.0f));
	NonePropertyActor = GetWorld()->SpawnActorDeferred<ABaseGeometryActor>(GeometryClass, GeometryTransform);

	GeometryTransform = FTransform(FRotator::ZeroRotator, FVector(700.0f, 300.0f, 300.0f));
	PropertyActor = GetWorld()->SpawnActorDeferred<ABaseGeometryActor>(GeometryClass, GeometryTransform);
}

// Called every frame
void AGeometryHubActor::Tick(float DeltaTime)
{
	Super::Tick(DeltaTime);

	UE_LOG(LogGeometryHub, Warning, TEXT("property pointer %i, is valid %i"), PropertyActor !=nullptr, IsValid(PropertyActor));
	UE_LOG(LogGeometryHub, Error, TEXT("none property pointer %i, is valid %i"), NonePropertyActor !=nullptr, IsValid(NonePropertyActor));
}
```

## Clang Format 
---

В настройках версии visual studio иногда нужно включить поддержку clang format и в настройках тоже включить галку enable clang format supp

![[Pasted image 20241217135052.png]]

![[Pasted image 20241217135018.png]]

https://clang.llvm.org/docs/ClangFormatStyleOptions.html

```
Language: Cpp
BasedOnStyle: Microsoft
IndentWidth: '4'
UseTab: Never
TabWidth: '6'
BreakBeforeBraces: Allman
ColumnLimit: '140'
AccessModifierOffset: '-4'
SortIncludes: false
AllowShortBlocksOnASingleLine: false
AlignAfterOpenBracket: DontAlign
AllowShortFunctionsOnASingleLine: Inline
PointerAlignment: Left
AllowShortIfStatementsOnASingleLine: true
```

## Gitignore
---
[[Gitignore]]

## ACharacter
---

Персонажу необходимо проверить что бы он был подключен в include 

Собрать это все в game mode . В гейм моде надо подключить класс управления player controller и сам персонаж character 

в самого персонажа подключить камеру. Подключается в модификаторах доступа protected. Что бы дочернии файлы могли использовать настройку 

.h
```cpp
class UCameraComponent;

protected:
	UPROPERTY(VisibleAnywhere, BlueprintReadWrite, Category = "Components")
    UCameraComponent* CameraComponent;
```
## Build
---

Говорит при билде искать файлы в таком пути 

```cs
		PublicIncludePaths.AddRange(new string[] { "ShootThemUp/Public/Player" });
```

## Movement Base
---

STUBaseCharacter.h

```cpp
public:	
	private:
      void MoveForward(float Amount);
      void MoveRight(float Amount);
};

```

STUBaseCharacter.cpp

```cpp
void ASTUBaseCharacter::SetupPlayerInputComponent(UInputComponent* PlayerInputComponent)
{
	Super::SetupPlayerInputComponent(PlayerInputComponent);

	PlayerInputComponent->BindAxis("MoveForward", this, &ASTUBaseCharacter::MoveForward);
	PlayerInputComponent->BindAxis("MoveRight", this, &ASTUBaseCharacter::MoveRight);
}

void ASTUBaseCharacter::MoveForward(float Amount) 
{
    AddMovementInput(GetActorForwardVector(), Amount);
}

void ASTUBaseCharacter::MoveRight(float Amount) 
{
    AddMovementInput(GetActorRightVector(), Amount);
}

```

## Camera
---
Бинд для инпутов 


![[Pasted image 20241217150123.png]]
![[Pasted image 20241217161702.png]]

![[Pasted image 20241217161717.png]]

Указывается инпут, бинд axis, затем как называется бинд, на что вляет и какая функция должна производиться. 

```cpp
	PlayerInputComponent->BindAxis("MoveForward", this, &ASTUBaseCharacter::MoveForward);
```

Spring arm

.h
```cpp
protected:
    UPROPERTY(VisibleAnywhere, BlueprintReadWrite, Category = "Components")
    USpringArmComponent* SpringArmComponent;

    UPROPERTY(VisibleAnywhere, BlueprintReadWrite, Category = "Components")
    UCameraComponent* CameraComponent;
```

cpp

```cpp
#include "Camera/CameraComponent.h"
#include "GameFramework/SpringArmComponent.h"

ASTUBaseCharacter::ASTUBaseCharacter()
{
    PrimaryActorTick.bCanEverTick = true;

    SpringArmComponent = CreateDefaultSubobject<USpringArmComponent>("SpringArmComponent");
    SpringArmComponent->SetupAttachment(GetRootComponent());
    SpringArmComponent->bUsePawnControlRotation = true;

    CameraComponent = CreateDefaultSubobject<UCameraComponent>("CameraComponent");
    CameraComponent->SetupAttachment(SpringArmComponent);
}

```

## Jump
---

```cpp
    PlayerInputComponent->BindAction("Jump", IE_Pressed, this, &ASTUBaseCharacter::Jump);
```

![[Pasted image 20241217181452.png]]
![[Pasted image 20241217181502.png]]

![[Pasted image 20241217181512.png]]

## Nitro. Character Movement Component
---

![[Pasted image 20241220171417.png]]

![[Pasted image 20241218220530.png]]

STUBaseCharacter.cpp

Замена стандартного character movement на кастомный. Настройка значений при беге 

```cpp
#include "Components/STU_CharacterMovementComponent.h"

// Sets default values
ASTUBaseCharacter::ASTUBaseCharacter(const FObjectInitializer& ObjInit)
	:Super(ObjInit.SetDefaultSubobjectClass<USTU_CharacterMovementComponent>(ACharacter::CharacterMovementComponentName))
{
 //code
}

//настройка значений 

void ASTUBaseCharacter::MoveForward(float Amount)
{
    IsMovingForward = Amount > 0.0f;
    AddMovementInput(GetActorForwardVector(), Amount);
}

void ASTUBaseCharacter::MoveRight(float Amount)
{
    AddMovementInput(GetActorRightVector(), Amount);
}

void ASTUBaseCharacter::OnStartRunning()
{
    WantsToRun = true;
}
void ASTUBaseCharacter::OnStopRunning()
{
    WantsToRun = false;
}

bool ASTUBaseCharacter::IsRunning() const
{
    return WantsToRun && IsMovingForward && !GetVelocity().IsZero();
}
```

STUBaseCharacter.h

```cpp
public:
    UFUNCTION(BlueprintCallable, Category = "Movement")
    bool IsRunning() const;

private:
    bool WantsToRun = false;
    bool IsMovingForward = false;

    void MoveForward(float Amount);
    void MoveRight(float Amount);

    void OnStartRunning();
    void OnStopRunning();
};
```

.h

функция GetMaxSpeed уже существует и переопределяется для последующего вызова 

```cpp

#pragma once

#include "CoreMinimal.h"
#include "GameFramework/CharacterMovementComponent.h"
#include "STU_CharacterMovementComponent.generated.h"

UCLASS()
class SHOOTTHEMUP_API USTU_CharacterMovementComponent : public UCharacterMovementComponent
{
    GENERATED_BODY()

public:
    UPROPERTY(EditDefaultsOnly, BlueprintReadWrite, Category = "Movement", meta = (ClampMin = "1.5", ClampMax = "10.0"))
    float RunModifier = 2.0f;

    virtual float GetMaxSpeed() const override;
};
```

.cpp

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

## Health bar component
---

![[Pasted image 20241220171333.png]]

![[Pasted image 20241220200826.png]]

![[Pasted image 20241220200852.png]]

![[Pasted image 20241220200905.png]]
delete all event tick

STUHealthComponent.h

```cpp
#include "STUHealthComponent.generated.h"

UCLASS(ClassGroup = (Custom), meta = (BlueprintSpawnableComponent))
class SHOOTTHEMUP_API USTUHealthComponent : public UActorComponent
{
    GENERATED_BODY()

public:
    USTUHealthComponent();

    float GetHealth() const { return Health; }

protected:
    UPROPERTY(EditDefaultsOnly, BlueprintReadWrite, Category = "Health", meta = (ClampMin = "0", ClampMax = "1000.0"))
    float MaxHealth = 100.0f;

    virtual void BeginPlay() override;

private:
    float Health = 0.0f;
};
```

STUHealthComponent.cpp

```cpp
#include "Components/STUHealthComponent.h"

USTUHealthComponent::USTUHealthComponent()
{
	PrimaryComponentTick.bCanEverTick = false;
}


// Called when the game starts
void USTUHealthComponent::BeginPlay()
{
	Super::BeginPlay();

	Health = MaxHealth;
}
```

STUBaseCharacter.h

```cpp
class USTUHealthComponent;
class UTextRenderComponent;

protected:
    UPROPERTY(VisibleAnywhere, BlueprintReadWrite, Category = "Components")
    USTUHealthComponent* HealthComponent;

    UPROPERTY(VisibleAnywhere, BlueprintReadWrite, Category = "Components")
    UTextRenderComponent* HealthTextComponent;
```

STUBaseCharacter.cpp

```cpp
#include "Components/STUHealthComponent.h"
#include "Components/TextRenderComponent.h"

// Sets default values
ASTUBaseCharacter::ASTUBaseCharacter(const FObjectInitializer& ObjInit)
    : Super(ObjInit.SetDefaultSubobjectClass<USTU_CharacterMovementComponent>(ACharacter::CharacterMovementComponentName))
{
    HealthComponent = CreateDefaultSubobject<USTUHealthComponent>("HealthComponent");

    HealthTextComponent = CreateDefaultSubobject<UTextRenderComponent>("HealthTextComponent");
    HealthTextComponent->SetupAttachment(GetRootComponent());
}

// Called when the game starts or when spawned
void ASTUBaseCharacter::BeginPlay()
{
    Super::BeginPlay();

    check(HealthComponent);
    check(HealthTextComponent);
}

// Called every frame
void ASTUBaseCharacter::Tick(float DeltaTime)
{
    Super::Tick(DeltaTime);

    const auto Health = HealthComponent->GetHealth();
    HealthTextComponent->SetText(FText::FromString(FString::Printf(TEXT("%.0f"), Health)));
}
```

## Check
---

Проверяет подключен ли каждый из компонентов. Не включается в билде, нужен лишь для проверки

```cpp
// Called when the game starts or when spawned
void ASTUBaseCharacter::BeginPlay()
{
    Super::BeginPlay();

    check(HealthComponent);
    check(HealthTextComponent);
}
```

https://dev.epicgames.com/documentation/en-us/unreal-engine/asserts-in-unreal-engine?application_version=5.4
## Указать границы 
---

Работает в границах от 1,5 - 10.0 

```cpp
    UPROPERTY(EditDefaultsOnly, BlueprintReadWrite, Category = "Movement", meta = (ClampMin = "1.5", ClampMax = "10.0"))
    float RunModifier = 2.0f;
```

## TakeDamage
---

Берем существующую функцию OnTakeDamage

STUHealthComponent.h

```cpp
    UFUNCTION()
    void OnTakeAnyDamage(
        AActor* DamagedActor, float Damage, const class UDamageType* DamageType, class AController* InstigatedBy, AActor* DamageCauser);
```

STUHealthComponent.cpp

```cpp
	AActor* ComponentOwner = GetOwner();
      if (ComponentOwner)
      {
          ComponentOwner->OnTakeAnyDamage.AddDynamic(this, &USTUHealthComponent::OnTakeAnyDamage);
	  }

void USTUHealthComponent::OnTakeAnyDamage(
    AActor* DamagedActor, float Damage, const class UDamageType* DamageType, class AController* InstigatedBy, AActor* DamageCauser)
{
    Health -= Damage;
}
```

## Разное
---

```C++
include "CoreMinimal.h" //определены некоторые базы данных константы
include "GameFramework/Actor.h" //наследуемся от актора, указывает заголовочный файл где объявлен актор 
include "BaseGeometryActor.generated.h" //идет последним всегда 
```

исполняемый файл подключается 1 раз
`#pragma once `

```
## - склейка двух элементов 
```

f12 - позволяет открыть код любого макроса и увидеть как он написан

Проверки на основные части кода, существуют ли они 

![[Pasted image 20241130032849.png]]

![[Pasted image 20241130032826.png]]

![[Pasted image 20241130033001.png]]

Destroy Actor

```cpp

	Geometry->Destroy();
	//Geometry->SetLifeSpan(2.0f)

```