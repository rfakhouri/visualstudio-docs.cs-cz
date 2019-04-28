---
title: Pravidel nástroje Analýza kódu CA2153 pro poškozený stav výjimky
ms.date: 02/19/2019
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 4b75e45b8a199265eaefe3a2b3c37ed62039e0eb
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62542154"
---
# <a name="ca2153-avoid-handling-corrupted-state-exceptions"></a>CA2153: Vyhněte se zpracování výjimek poškozený stav

|||
|-|-|
|TypeName|AvoidHandlingCorruptedStateExceptions|
|CheckId|CA2153|
|Kategorie|Microsoft.Security|
|Narušující změna|Pevné|

## <a name="cause"></a>Příčina

[Poškozený stav výjimek (rozšíření na straně klienta)](https://msdn.microsoft.com/magazine/dd419661.aspx) znamenat, že paměť poškození existuje v procesu. Toto zachycení nepovolí selhání procesu může vést k ohrožení zabezpečení, pokud útočník lze umístit do oblasti paměti poškozená zneužití.

## <a name="rule-description"></a>Popis pravidla

Rozšíření na straně klienta Určuje, že stav procesu byl poškozený a není zachycena v systému. V poškozeném stavu scénáři obecné obslužné rutiny pouze zachytí výjimku Pokud označíte metodu s <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute?displayProperty=fullName> atribut. Ve výchozím nastavení [Common Language Runtime (CLR)](/dotnet/standard/clr) nevyvolá obslužné rutiny catch pro rozšíření na straně klienta.

Nejbezpečnější možností je Povolit proces při selhání bez zachycování tyto druhy výjimek. I protokolování kódu můžou útočníci zneužít ohrožená místa chyby poškození paměti.

Toto upozornění se aktivuje při zachycování rozšíření na straně klienta pomocí obecné obslužné rutině, která zachytává všechny výjimky, například `catch (System.Exception e)` nebo `catch` s parametrem žádné výjimky.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení

Pokud chcete vyřešit toto upozornění, proveďte jednu z následujících akcí:

- Odeberte <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute> atribut. To obnoví na výchozí chování za běhu, ve kterém nejsou předán obslužné rutiny zachytávání rozšíření na straně klienta.

- Odeberte obslužnou rutinu obecný zachytávací in preference of obslužných rutin, které zachytit specifické výjimky typy. To může zahrnovat rozšíření na straně klienta, za předpokladu, že kód obslužné rutiny můžete bezpečně jejich zpracování (vzácného).

- V obslužné rutiny catch, který předá výjimku volajícího a by měl mít za následek ukončení spuštěného procesu znovu vyvolejte rozšíření na straně klienta.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

Nepotlačujte upozornění na toto pravidlo.

## <a name="pseudo-code-example"></a>Příklad pseudo kódu

### <a name="violation"></a>Porušení

Pseudo následující kód znázorňuje, zjistí toto pravidlo.

```csharp
[HandleProcessCorruptedStateExceptions]
// Method that handles CSE exceptions.
void TestMethod1()
{
    try
    {
        FileStream fileStream = new FileStream("name", FileMode.Create);
    }
    catch (Exception e)
    {
        // Handle exception.
    }
}
```

### <a name="solution-1---remove-the-attribute"></a>Řešení 1 - odebrat atribut

Odebírá <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute> atribut zajistí, že poškozený stav výjimky nejsou zpracovávány metodu.

```csharp
void TestMethod1()
{
    try
    {
        FileStream fileStream = new FileStream("name", FileMode.Create);
    }
    catch (Exception e)
    {
        // Handle exception.
    }
}
```

### <a name="solution-2---catch-specific-exceptions"></a>Řešení 2 - zachytit specifické výjimky

Odebrat obslužnou rutinu obecný zachytávací a zachytit pouze typy určité výjimky.

```csharp
void TestMethod1()
{
    try
    {
        FileStream fileStream = new FileStream("name", FileMode.Create);
    }
    catch (IOException e)
    {
        // Handle IOException.
    }
    catch (UnauthorizedAccessException e)
    {
        // Handle UnauthorizedAccessException.
    }
}
```

### <a name="solution-3---rethrow"></a>Řešení 3 - rethrow

Znovu vyvolá výjimku.

```csharp
[HandleProcessCorruptedStateExceptions]
void TestMethod1()
{
    try
    {
        FileStream fileStream = new FileStream("name", FileMode.Create);
    }
    catch (Exception e)
    {
        // Rethrow the exception.
        throw;
    }
}
```