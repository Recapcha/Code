
Что это? 
Что оно делает?
Описание

```cpp
    //статический метод, изменяет цвет яблока, принимает ссылку на яблоко, которому нужно изменить цвет и цвет который нужно поставить
    static void ChangeColor(AppleClass &apple, string color)
    {
        
    }
```

Вот основные соглашения об именовании в Unreal Engine:

- **Классы:** Начинаются с префикса `A` (для классов, наследующих от `AActor`) или `U` (для классов, наследующих от `UObject`). Например, `ACharacter`, `UUserWidget`.
- **Структуры:** Начинаются с префикса `F`. Например, `FVector`, `FLinearColor`.
- **Перечисления (Enums):** Начинаются с префикса `E`. Например, `EMovementMode`, `ECollisionChannel`.
- **Переменные:**
    - **Члены класса:** Начинаются с префикса `m_`. Например, `m_Health`, `m_Name`. В некоторых командах могут использовать просто `_` префикс, например `_health`.
    - **Локальные переменные:** Начинаются с маленькой буквы, camelCase. Например, `currentHealth`, `playerScore`.
    - **Глобальные переменные:** Начинаются с `g_`. (Использовать глобальные переменные следует очень осторожно).
- **Функции:** Начинаются с большой буквы, PascalCase. Например, `SetHealth()`, `UpdateScore()`.
- **Интерфейсы:** Начинаются с префикса `I`. Например, `IInteractable`, `IDamageable`.
- **Булевы переменные:** Начинаются с префикса `b`. Например, `bIsAlive`, `bCanJump`.
- **Типы (typedefs):** Начинаются с префикса `F`. Например, `FString`.

**Примеры:**

```c++
// Класс Actor
UCLASS()
class MYPROJECT_API AMyCharacter : public ACharacter
{
    GENERATED_BODY()

private:
    // Переменная-член класса
    float m_Health;

public:
    // Функция
    void SetHealth(float NewHealth);

    // Перечисление
    enum class EMovementMode
    {
        Walking,
        Running,
        Swimming
    };

    // Структура
    struct FMyStruct
    {
        int32 Value;
    };
};

void AMyCharacter::SetHealth(float NewHealth)
{
    // Локальная переменная
    float clampedHealth = FMath::Clamp(NewHealth, 0.0f, 100.0f);
    m_Health = clampedHealth;
}
```