---
title: 'CA2007: Nečekejte přímo na úlohu'
ms.date: 03/08/2019
ms.topic: reference
f1_keywords:
- CA2007
- DoNotDirectlyAwaitATaskAnalyzer
helpviewer_keywords:
- CA2007
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
ms.openlocfilehash: 0d3ab899ad660c637492a4c3d229779481184e95
ms.sourcegitcommit: 209ed0fcbb8daa1685e8d6b9a97f3857a4ce1152
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/16/2019
ms.locfileid: "69547002"
---
# <a name="ca2007-do-not-directly-await-a-task"></a>CA2007: Nečekejte přímo na úlohu

|||
|-|-|
|TypeName|DoNotDirectlyAwaitATaskAnalyzer|
|CheckId|CA2007|
|Kategorie|Microsoft.Reliability|
|Narušující změna|Nenarušující|

## <a name="cause"></a>příčina

Asynchronní metoda [čeká](/dotnet/csharp/language-reference/keywords/await) <xref:System.Threading.Tasks.Task> přímo.

## <a name="rule-description"></a>Popis pravidla

Když asynchronní metoda čeká <xref:System.Threading.Tasks.Task> přímo, pokračování probíhá ve stejném vláknu, které úlohu vytvořilo. Toto chování může být nákladné v souvislosti s výkonem a může způsobit zablokování ve vlákně uživatelského rozhraní. Zvažte volání <xref:System.Threading.Tasks.Task.ConfigureAwait(System.Boolean)?displayProperty=nameWithType> , abyste vyvolali svůj záměr na pokračování.

Toto pravidlo bylo představeno pomocí [analyzátorů FxCop](install-fxcop-analyzers.md) a neexistuje ve starší analýze FxCop.

## <a name="how-to-fix-violations"></a>Jak opravit porušení

Chcete-li opravit porušení, <xref:System.Threading.Tasks.Task.ConfigureAwait%2A> zavolejte na <xref:System.Threading.Tasks.Task>očekáváno. Pro `false` `true` parametrmůžete`continueOnCapturedContext` předat buď nebo.

- Volání `ConfigureAwait(true)` na úlohu má stejné chování jako neexplicitní volání <xref:System.Threading.Tasks.Task.ConfigureAwait%2A>. Explicitním voláním této metody umožníte čtenářům, aby měli v úmyslu provést pokračování v původním kontextu synchronizace.

- Zavolejte `ConfigureAwait(false)` na úkol pro naplánování pokračování fondu vláken, čímž se vyhnete zablokování vlákna uživatelského rozhraní. Předávání `false` je vhodné pro knihovny nezávislé na aplikaci.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

Toto upozornění můžete potlačit, pokud víte, že příjemce není aplikace grafického uživatelského rozhraní (GUI), nebo pokud uživatel <xref:System.Threading.SynchronizationContext>nemá.

## <a name="example"></a>Příklad

Následující fragment kódu vygeneruje upozornění:

```csharp
public async Task Execute()
{
    Task task = null;
    await task;
}
```

Chcete-li opravit porušení, <xref:System.Threading.Tasks.Task.ConfigureAwait%2A> zavolejte na <xref:System.Threading.Tasks.Task>očekávaný:

```csharp
public async Task Execute()
{
    Task task = null;
    await task.ConfigureAwait(false);
}
```

## <a name="configurability"></a>Konfigurovatelnost

Můžete nakonfigurovat, zda chcete vyloučit asynchronní metody, které nevracejí hodnotu z tohoto pravidla. Chcete-li vyloučit tyto druhy metod, přidejte do souboru. editorconfig v projektu následující dvojici klíč-hodnota:

```ini
# Package version 2.9.0 and later
dotnet_code_quality.CA2007.exclude_async_void_methods = true

# Package version 2.6.3 and earlier
dotnet_code_quality.CA2007.skip_async_void_methods = true
```

Můžete také nakonfigurovat, na které výstupní typy sestavení se má toto pravidlo použít. Chcete-li například použít toto pravidlo pouze na kód, který vytvoří konzolovou aplikaci nebo dynamicky propojenou knihovnu (tj. není to aplikace uživatelského rozhraní), přidejte do souboru. editorconfig v projektu následující dvojici klíč-hodnota:

```ini
dotnet_code_quality.CA2007.output_kind = ConsoleApplication, DynamicallyLinkedLibrary
```

Další informace najdete v tématu [Konfigurace analyzátorů FxCop](configure-fxcop-analyzers.md).

## <a name="see-also"></a>Viz také:

- [Mám očekávat úlohu s ConfigureAwait (NEPRAVDA)?](https://github.com/Microsoft/vs-threading/blob/master/doc/cookbook_vs.md#should-i-await-a-task-with-configureawaitfalse)
- [Instalace analyzátorů FxCop v aplikaci Visual Studio](install-fxcop-analyzers.md)