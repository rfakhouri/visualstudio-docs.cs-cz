---
title: 'CA1063: Implementuje správně IDisposable'
ms.date: 02/12/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- ImplementIDisposableCorrectly
- CA1063
helpviewer_keywords:
- CA1063
- ImplementIDisposableCorrectly
ms.assetid: 12afb1ea-3a17-4a3f-a1f0-fcdb853e2359
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ac3827dd8ed34a118bb3e4eaaed47bf7400cef90
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31900209"
---
# <a name="ca1063-implement-idisposable-correctly"></a>CA1063: Implementuje správně IDisposable

|||
|-|-|
|TypeName|ImplementIDisposableCorrectly|
|CheckId|CA1063|
|Kategorie|Microsoft.Design|
|Narušující změna|Nenarušující|

## <a name="cause"></a>příčina

`IDisposable` není správně implementována. Jsou zde uvedeny některé příčiny tohoto problému:

- Rozhraní IDisposable je znovu implementované v třídě.

- Dokončení znovu přepsána.

- Uvolnění přepsána.

- Není veřejné, Dispose() zapečetěné nebo s názvem uvolnění.

- Dispose(bool) není chráněný, virtuální nebo nezapečetěné.

- V nezapečetěných typy musí volat Dispose() Dispose(true).

- Pro nezapečetěné typy dokončení implementace nevyvolá obojím Dispose(bool) nebo finalizační metodu třídy případu.

Porušení některého z těchto vzory aktivují toto upozornění.

Každý nezapečetěné typ, který deklaruje a implementuje rozhraní IDisposable musíte zadat vlastní chráněná virtuální void Dispose(bool) metoda. Dispose() by měly volat Dipose(true) a dokončení by měly volat Dispose(false). Pokud vytváříte nezapečetěných typ, který deklaruje a implementuje rozhraní IDisposable, musíte definovat Dispose(bool) a pojmenujte ji. Další informace najdete v tématu [vymazání nespravovaných prostředků](/dotnet/standard/garbage-collection/unmanaged) v [pokynů pro návrh rozhraní .NET Framework](/dotnet/standard/design-guidelines/index).

## <a name="rule-description"></a>Popis pravidla

Všechny typy IDisposable by měly správně implementovat vzor Dispose.

## <a name="how-to-fix-violations"></a>Jak opravit porušení

Zkontrolujte v kódu a zjistěte, který z následujících řešení opraví tento porušení.

- Odebrat ze seznamu rozhraní, které jsou implementované pomocí rozhraní IDisposable {0} a místo toho přepsat implementace metody Dispose základní třídy.

- Odeberte finalizační metodu z typu {0}přepsat metodu Dispose (bool uvolnění) a uveďte logiku finalizace v kódové cestě 'uvolnění, pokud má hodnotu false.

- Odebrat {0}, přepsat metodu Dispose (bool uvolnění) a uveďte logiku uvolnění v kódové cestě 'uvolnění, kde je true.

- Ujistěte se, že {0} je deklarován jako veřejné a zapečetěná.

- Přejmenujte {0} k 'uvolnění a ujistěte se, že je deklarován jako veřejné a uzavřené.

- Ujistěte se, že {0} je deklarován jako chráněný, virtuální a nezapečetěné.

- Upravit {0} tak, aby zavolá Dispose(true), pak zavolá GC. Funkce SuppressFinalize na aktuální instanci objektu ('this' nebo 'Mi' v [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]) a potom se vrátí.

- Upravit {0} tak, aby volá Dispose(false) a potom se vrátí.

- Pokud vytváříte nezapečetěných typ, který deklaruje a implementuje rozhraní IDisposable, ujistěte se, že implementace rozhraní IDisposable dodržuje vzor, který je popsán výše v této části.

## <a name="when-to-suppress-warnings"></a>Při potlačení upozornění

Nepotlačujte upozornění na toto pravidlo.

## <a name="pseudo-code-example"></a>Příklad pseudo kódu

Následující kód pseudo poskytuje obecné příklad, jak by měla být Dispose(bool) implementována ve třídě, která používá spravovaná a nativní prostředky.

```csharp
public class Resource : IDisposable
{
    private IntPtr nativeResource = Marshal.AllocHGlobal(100);
    private AnotherResource managedResource = new AnotherResource();

    // Dispose() calls Dispose(true)
    public void Dispose()
    {
        Dispose(true);
        GC.SuppressFinalize(this);
    }

    // NOTE: Leave out the finalizer altogether if this class doesn't
    // own unmanaged resources itself, but leave the other methods
    // exactly as they are.
    ~Resource()
    {
        // Finalizer calls Dispose(false)
        Dispose(false);
    }

    // The bulk of the clean-up code is implemented in Dispose(bool)
    protected virtual void Dispose(bool disposing)
    {
        if (disposing)
        {
            // free managed resources
            if (managedResource != null)
            {
                managedResource.Dispose();
                managedResource = null;
            }
        }
        // free native resources if there are any.
        if (nativeResource != IntPtr.Zero)
        {
            Marshal.FreeHGlobal(nativeResource);
            nativeResource = IntPtr.Zero;
        }
    }
}
```