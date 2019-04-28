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
ms.openlocfilehash: bf3e13697f39f7d0f531549d4c018b9f42872596
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62545225"
---
# <a name="ca2007-do-not-directly-await-a-task"></a>CA2007: Nečekejte přímo na úlohu

|||
|-|-|
|TypeName|DoNotDirectlyAwaitATaskAnalyzer|
|CheckId|CA2007|
|Kategorie|Microsoft.Reliability|
|Narušující změna|Nenarušující|

## <a name="cause"></a>Příčina

Asynchronní metoda [čeká](/dotnet/csharp/language-reference/keywords/await) <xref:System.Threading.Tasks.Task> přímo.

## <a name="rule-description"></a>Popis pravidla

Když asynchronní metoda čeká <xref:System.Threading.Tasks.Task> přímo, dojde k pokračování ve stejném vlákně, která úkol vytvořila. Toto chování může být náročné na výkon a může vést k zablokování vlákna uživatelského rozhraní. Zvažte možnost volání <xref:System.Threading.Tasks.Task.ConfigureAwait(System.Boolean)?displayProperty=nameWithType> který signalizuje, že váš záměr pro pokračování.

Toto pravidlo byla zavedena v systémech [analyzátory FxCop](install-fxcop-analyzers.md) a neexistuje v "starší" (analýza statického kódu) FxCop.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení

Chcete-li opravit porušení, zavolejte <xref:System.Threading.Tasks.Task.ConfigureAwait%2A> na očekávaný <xref:System.Threading.Tasks.Task>. Můžete předat buď `true` nebo `false` pro `continueOnCapturedContext` parametru.

- Volání `ConfigureAwait(true)` na úkol má stejné chování jako volání nejsou explicitně <xref:System.Threading.Tasks.Task.ConfigureAwait%2A>. Explicitně voláním této metody, že umožníte tím čtenáři vědět, že chcete záměrně provést pokračování v původní kontextu synchronizace.

- Volání `ConfigureAwait(false)` na úkol k naplánování pokračování s fondem vláken, a tím zabránit zablokování vlákna uživatelského rozhraní. Předání `false` je dobrou volbou pro knihovny nezávislé na aplikaci.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

Toto upozornění můžete potlačit, pokud víte, že takový příjemce není aplikace v jazyce grafické uživatelské rozhraní (GUI) nebo pokud uživatel nemá <xref:System.Threading.SynchronizationContext>.

## <a name="example"></a>Příklad

Následující fragment kódu generuje toto upozornění:

```csharp
public async Task Execute()
{
    Task task = null;
    await task;
}
```

Chcete-li opravit porušení zásad, zavolejte <xref:System.Threading.Tasks.Task.ConfigureAwait%2A> na očekávaný <xref:System.Threading.Tasks.Task>:

```csharp
public async Task Execute()
{
    Task task = null;
    await task.ConfigureAwait(false);
}
```

## <a name="configurability"></a>Možnosti konfigurace:

Můžete nakonfigurovat, zda mají být vyloučeny asynchronní metody, které nevracejí hodnotu z tohoto pravidla. K vyloučení těchto druzích metod, přidejte následující dvojice klíč hodnota do souboru .editorconfig ve vašem projektu:

```
# Package version 2.9.0 and later
dotnet_code_quality.CA2007.exclude_async_void_methods = true

# Package version 2.6.3 and earlier
dotnet_code_quality.CA2007.skip_async_void_methods = true
```

Můžete také nakonfigurovat, které výstupní typy sestavení použít toto pravidlo. Například tohoto pravidla lze použít pouze pro kód, který vytvoří aplikace konzoly nebo dynamicky propojené knihovny (to znamená, ne aplikace uživatelského rozhraní), přidejte do souboru .editorconfig ve vašem projektu následující dvojice klíč hodnota:

```
dotnet_code_quality.CA2007.output_kind = ConsoleApplication, DynamicallyLinkedLibrary
```

Další informace najdete v tématu [analyzátory FxCop konfigurace](configure-fxcop-analyzers.md).

## <a name="see-also"></a>Viz také:

- [By měla očekávat úlohu s ConfigureAwait(false)?](https://github.com/Microsoft/vs-threading/blob/master/doc/cookbook_vs.md#should-i-await-a-task-with-configureawaitfalse)
- [Nainstalujte analyzátory FxCop v sadě Visual Studio](install-fxcop-analyzers.md)