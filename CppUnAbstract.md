Abstract - конспект. Этот файл коспект использования C++ в unreal engine
## Логирование. Макрос в UE
---

```cpp
UE_LOG(LogTemp, Display, TEXT("Hello Unreal!"));
UE_LOG(LogTemp, Warning, TEXT("Hello Unreal!"));
UE_LOG(LogTemp, Error, TEXT("Hello Unreal!"));
```

![[Pasted image 20241112194755.png]]

Вывод логов в различных цветах и типах
Можно выделить или нажать на макрос и его скопировать 

Идентификтатор 
%d , %i - целые числа
%f - float

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
	UE_LOG(LogTemp, Display, TEXT("HasWeapon: %d"), static_cast<int>(HasWeapon)); //переобразование из одного тип в другой
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

В файле лежат все уровни логировния, которым присвоен счет от 0 до 7+ . Присвоение all = 7 . Выведутся все уровни до 7. Такие 

## Тип FString. 
---

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

//FromInt - получает на входе инт, а выходе возвращает string
//SanitizeFloat - получает на вход числа double, float будет авто переведен в double, на выходе получит тоже string
//? - работает как if else, если if = "true", тринарный оператор

Вывод на экран вьюпорта значений. Нужно подключить библотеку, затем в функции указать. 

```cpp
#include "Engine/Engine.h"
```

GEngine->AddOnScreenDebugMessage

![[Pasted image 20241112225525.png]]

![[Pasted image 20241112225518.png]]

## Работа с Tick
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

![[Pasted image 20241114073000.png]]
## Макрос UPROPERTY
---

Вставляется в .h заголовок. Позволяет выводить значения для изменения во вьюпорте 

```cpp
protected:
	// Called when the game starts or when spawned
	virtual void BeginPlay() override;

	UPROPERTY(EditAnywhere, Category = "Weapon")
	int32 WeaponsNum = 4;

	UPROPERTY(EditDefaultsOnly, Category = "Stat")
	int32 KillsNum = 7;

	UPROPERTY(EditInstanceOnly, Category = "Health")
	float Health = 34.1535633;

	UPROPERTY(EditAnywhere, Category = "Health")
	bool IsDead = false;

	UPROPERTY(VisibleAnywhere, Category = "Weapon")
	bool HasWeapon = true;
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
### Static Mesh Component и Root

Необходимо добавить библиотеку в заголовочный файл

```cpp
#include "Components/StaticMeshComponent.h"
```

Затем добавить что он был виден во вьюпорте. Он будет отсылаться к коду в cpp файле

```cpp
public:	
	// Sets default values for this actor's properties
	ABaseGeometryActor();

	UPROPERTY(VisibleAnywhere)
		UStaticMeshComponent* BaseMesh;
```

![[Pasted image 20241114064326.png]]

Так же в cpp файле нужно добавить код, который позволяет добавить меш. Так же здесь добавляется гизмо. Рут актора 

```cpp
// Sets default values.
ABaseGeometryActor::ABaseGeometryActor()
{
 	// Set this actor to call Tick() every frame.  You can turn this off to improve performance if you don't need it.
	PrimaryActorTick.bCanEverTick = true;

	BaseMesh = CreateDefaultSubobject<UStaticMeshComponent>("BaseMesh");
	SetRootComponent(BaseMesh);
}
```

![[Pasted image 20241114064639.png]]

## Тип FTransform
---

```cpp
	FTransform Transform = GetActorTransform();
	FVector Location = Transform.GetLocation();
	FRotator Rotation = Transform.Rotator();
	FVector Scale = Transform.GetScale3D();

	UE_LOG(LogBaseGeometry, Warning, TEXT("Actor name %s"), *GetName());
	UE_LOG(LogBaseGeometry, Warning, TEXT("Transform %s"), *Transform.ToString());UE_LOG(LogBaseGeometry, Warning, TEXT("Transform %s"), *Transform.ToString());
	UE_LOG(LogBaseGeometry, Warning, TEXT("Location %s"), *Location.ToString());
	UE_LOG(LogBaseGeometry, Warning, TEXT("Rotation %s"), *Rotation.ToString());
	UE_LOG(LogBaseGeometry, Warning, TEXT("Scale %s"), *Scale.ToString());

	UE_LOG(LogBaseGeometry, Error, TEXT("Human transform %s"), *Transform.ToHumanReadableString());
```

![[Pasted image 20241114070425.png]]

## ENUM
---

В заголовочном файле указываем состояния которые используются. Для них всегда используется uint8 и так же в начале названия указывается буква E... 

```cpp
UENUM(BlueprintType)
enum class EMovementType : uint8
{
	Sin,
	Static
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

Создаются обычным способом материалы. Затем в них создаются параметры. В коде можно взять материал и управлять параметров в этом материале. Важен не название материала, а параметр в нем. 

Если будут два разных материала, но одинаковые параметры внутри, код будет работать

![[Pasted image 20241117012658.png]]

![[Pasted image 20241117013133.png]]

```cpp
#include "Materials/MaterialInstanceDynamic.h"
```

Создание функции с ссылкой на параметр в материале, для изменения.

```cpp
	void SetColor(const FLinearColor& Color);
```

```cpp
void ABaseGeometryActor::SetColor(const FLinearColor& Color)
{
	UMaterialInstanceDynamic* DynMaterial = BaseMesh->CreateAndSetMaterialInstanceDynamic(0);
	if (DynMaterial)
	{
		DynMaterial->SetVectorParameterValue("Color", Color);
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

## Timer
---

Таймер позволяет установить время и на каждый тик будет происходить действие 

Обозначаем переменные отвечающую за частоту срабатывания 

.h

```cpp
USTRUCT 

	UPROPERTY(EditAnywhere, Category = "Design")
	float TimerRate = 3.0f;
```

Создаем дискриптор Timer Handle, будет иметь доступ к нему. Сможем поставить его на паузу или остановить. Так же создаем счетчик и максимальное значение. Эти значения потом будут сравниваться 

```cpp
private:
	FTimerHandle TimerHandle;

	const int32 MaxTimerCount = 5;
	int32 TimerCount = 0;
```

.cpp

```cpp
#include "TimerManager.h"
```

begin play
```cpp
	GetWorldTimerManager().SetTimer(TimerHandle, this, &ABaseGeometryActor::OnTimerFired, GeometryData.TimerRate, true);
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

![[Pasted image 20241130015955.png]]

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

## UFUNCTION
---

![[Pasted image 20241211123548.png]]

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

## Делегаты. 
---

![[Pasted image 20241211181650.png]]

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

## Pawn. GameModeBase
---

Настройка основного GameModeBase и замена там Pawn. Для управления в стороны

![[Pasted image 20241212162503.png]]

![[Pasted image 20241212163003.png]]

gameCGameModeBase.cpp

```cpp
#include "gameCGameModeBase.h"
#include "SandboxPawn.h"

AgameCGameModeBase::AgameCGameModeBase()
{
	DefaultPawnClass = ASandboxPawn::StaticClass();
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
		AgameCGameModeBase();
};
```

SandboxPawn.cpp

```cpp
#include "SandboxPawn.generated.h"

UCLASS()
class GAMEC_API ASandboxPawn : public APawn
{
	GENERATED_BODY()

public:
	// Sets default values for this pawn's properties
	ASandboxPawn();

	UPROPERTY(VisibleAnywhere)
	USceneComponent* SceneComponent;

	UPROPERTY(EditAnywhere)
		float Velocity = 300.0f;

protected:
	// Called when the game starts or when spawned
	virtual void BeginPlay() override;

public:	
	// Called every frame
	virtual void Tick(float DeltaTime) override;

	// Called to bind functionality to input
	virtual void SetupPlayerInputComponent(class UInputComponent* PlayerInputComponent) override;

private:
	FVector VelocityVector = FVector::ZeroVector;

	void MoveForward(float Amount);
	void MoveRight(float Amount);
};
```

SandboxPawn.cpp

```cpp
#include "SandboxPawn.h"
#include "Components/InputComponent.h"

DEFINE_LOG_CATEGORY_STATIC(LogSandboxPawn, All, All)

// Sets default values
ASandboxPawn::ASandboxPawn()
{
 	// Set this pawn to call Tick() every frame.  You can turn this off to improve performance if you don't need it.
	PrimaryActorTick.bCanEverTick = true;

	SceneComponent = CreateDefaultSubobject<USceneComponent>("SceneComponent");
	SetRootComponent(SceneComponent);

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

	if (!VelocityVector.IsZero())
	{
		const FVector NewLocation = GetActorLocation() + Velocity * DeltaTime * VelocityVector;
		SetActorLocation(NewLocation);
	}
}

// Called to bind functionality to input
void ASandboxPawn::SetupPlayerInputComponent(UInputComponent* PlayerInputComponent)
{
	Super::SetupPlayerInputComponent(PlayerInputComponent);

	PlayerInputComponent->BindAxis("MoveForward", this, &ASandboxPawn::MoveForward);
	PlayerInputComponent->BindAxis("MoveRight", this, &ASandboxPawn::MoveRight);
}

void ASandboxPawn::MoveForward(float Amount)
{
	UE_LOG(LogSandboxPawn, Display, TEXT("Move forward: %f"), Amount)
	VelocityVector.X = Amount;
}

void ASandboxPawn::MoveRight(float Amount)
{
	UE_LOG(LogSandboxPawn, Display, TEXT("Move right: %f"), Amount)
	VelocityVector.Y = Amount;
}
```

## Player Controller
---
![[Pasted image 20241212233801.png]]

SandboxPlayerController.h

```cpp
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
	virtual void SetupInputComponent() override;
	virtual void BeginPlay() override;

private:
	UPROPERTY()
	TArray<AActor*> Pawns;

	int32 CurrentPawnIndex = 0;

	void ChangePawn();
};
```

SandboxPlayerController.cpp
```cpp
#include "SandboxPlayerController.h"
#include "Components/InputComponent.h"
#include "Kismet/GameplayStatics.h"
#include "SandboxPawn.h"

DEFINE_LOG_CATEGORY_STATIC(LogSandboxPlayerController, All, All)

void ASandboxPlayerController::SetupInputComponent()
{
	Super::SetupInputComponent();

	if (InputComponent)
	{
		InputComponent->BindAction("ChangePawn", IE_Pressed, this, &ASandboxPlayerController::ChangePawn);
	}
}

void ASandboxPlayerController::BeginPlay()
{
	Super::BeginPlay();


	UGameplayStatics::GetAllActorsOfClass(GetWorld(), ASandboxPawn::StaticClass(), Pawns);
}

void ASandboxPlayerController::ChangePawn()
{
	if (Pawns.Num() <= 1) return;

	ASandboxPawn* CurrentPawn = Cast<ASandboxPawn>(Pawns[CurrentPawnIndex]);
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

## Modules, Targets, UnrealBuildTool
---
![[Pasted image 20241214200746.png]]

## Garbage Collector
---

![[Pasted image 20241214220752.png]]

Start

![[Pasted image 20241214221122.png]]

Pressed Enter

![[Pasted image 20241214221133.png]]

Pressed Tab

![[Pasted image 20241214221149.png]]

GeometryHubActor.h

```cpp

private:
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
```
.vs
*.sln
DerivedDataCache/
Intermediate/
Saved/
Binaries/
Build/
```

https://github.com/github/gitignore/blob/main/UnrealEngine.gitignore

```
# Visual Studio 2015 user specific files
.vs/

# Compiled Object files
*.slo
*.lo
*.o
*.obj

# Precompiled Headers
*.gch
*.pch

# Compiled Dynamic libraries
*.so
*.dylib
*.dll

# Fortran module files
*.mod

# Compiled Static libraries
*.lai
*.la
*.a
*.lib

# Executables
*.exe
*.out
*.app
*.ipa

# These project files can be generated by the engine
*.xcodeproj
*.xcworkspace
*.sln
*.suo
*.opensdf
*.sdf
*.VC.db
*.VC.opendb

# Precompiled Assets
SourceArt/**/*.png
SourceArt/**/*.tga

# Binary Files
Binaries/*
Plugins/**/Binaries/*

# Builds
Build/*

# Whitelist PakBlacklist-<BuildConfiguration>.txt files
!Build/*/
Build/*/**
!Build/*/PakBlacklist*.txt

# Don't ignore icon files in Build
!Build/**/*.ico

# Built data for maps
*_BuiltData.uasset

# Configuration files generated by the Editor
Saved/*

# Compiled source files for the engine to use
Intermediate/*
Plugins/**/Intermediate/*

# Cache files for the editor to use
DerivedDataCache/*
```

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