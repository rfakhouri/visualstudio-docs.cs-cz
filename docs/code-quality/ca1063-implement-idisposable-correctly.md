---
title: "CA1063: Implementace rozhraní IDisposable správně | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ImplementIDisposableCorrectly
- CA1063
helpviewer_keywords:
- CA1063
- ImplementIDisposableCorrectly
ms.assetid: 12afb1ea-3a17-4a3f-a1f0-fcdb853e2359
caps.latest.revision: "17"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 33c9b3d7b3cdcfc49c3fac14e5ba3a2dcfc2fc49
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="ca1063-implement-idisposable-correctly"></a>CA1063: Implementuje správně IDisposable
|||  
|-|-|  
|TypeName|ImplementIDisposableCorrectly|  
|CheckId|CA1063|  
|Kategorie|Microsoft.Design|  
|Narušující změna|Nenarušující|  
  
## <a name="cause"></a>příčina  
 `IDisposable`není správně implementována. Jsou zde uvedeny některé příčiny tohoto problému:  
  
-   Rozhraní IDisposable je znovu implementované v třídě.  
  
-   Dokončení znovu přepsána.  
  
-   Uvolnění přepsána.  
  
-   Není veřejné, Dispose() zapečetěné nebo s názvem uvolnění.  
  
-   Dispose(bool) není chráněný, virtuální nebo nezapečetěné.  
  
-   V nezapečetěných typy musí volat Dispose() Dispose(true).  
  
-   Pro nezapečetěné typy dokončení implementace nevyvolá obojím Dispose(bool) nebo finalizační metodu třídy případu.  
  
 Porušení některého z těchto vzory aktivují toto upozornění.  
  
 Každý nezapečetěných kořenový typ rozhraní IDisposable musíte zadat vlastní chráněná virtuální void Dispose(bool) metoda. Dispose() by měly volat Dipose(true) a dokončení by měly volat Dispose(false). Pokud vytváříte typ rozhraní IDisposable nezapečetěných kořenové, musíte definovat Dispose(bool) a volání. Další informace najdete v tématu [čištění nespravovaných prostředků](/dotnet/standard/garbage-collection/unmanaged) v [pokynů pro návrh Framework](/dotnet/standard/design-guidelines/index) části dokumentace rozhraní .NET Framework.  
  
## <a name="rule-description"></a>Popis pravidla  
 Všechny typy IDisposable by měly správně implementovat vzor Dispose.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Zkontrolujte v kódu a zjistěte, který z následujících řešení opraví tento porušení.  
  
-   Rozhraní IDisposable odeberte ze seznamu rozhraní, které jsou implementované {0} a místo toho přepsat implementace metody Dispose základní třídy.  
  
-   Odeberte finalizační metodu z typu {0}, přepsat metodu Dispose (bool uvolnění) a uveďte logiku finalizace v kódové cestě 'uvolnění, pokud má hodnotu false.  
  
-   Odeberte {0}, přepsat metodu Dispose (bool uvolnění) a uveďte logiku uvolnění v kódové cestě 'uvolnění, kde je true.  
  
-   Zkontrolujte, zda že tento {0} je deklarován jako veřejné a uzavřené.  
  
-   Přejmenujte {0} 'uvolnění a ujistěte se, že je deklarován jako veřejné a uzavřené.  
  
-   Ujistěte se, že tento {0} je deklarován jako chráněný, virtuální a nezapečetěné.  
  
-   {0} upravte tak, aby volá Dispose(true) a potom volá GC. Funkce SuppressFinalize na aktuální instanci objektu ('this' nebo 'Mi' v [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]) a potom se vrátí.  
  
-   {0} upravte tak, aby volá Dispose(false) a potom se vrátí.  
  
-   Pokud píšete třídu rozhraní IDisposable nezapečetěných kořenové, ujistěte se, že implementace rozhraní IDisposable dodržuje vzor, který je popsán výše v této části.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Nepotlačujte upozornění na toto pravidlo.  
  
## <a name="pseudo-code-example"></a>Příklad pseudo kódu  
 Následující kód pseudo poskytuje obecné příklad, jak by měla být Dispose(bool) implementována ve třídě, která používá spravovaná a nativní prostředky.  
  
```  
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