---
title: Upozornění analýzy kódu anonymní metoda
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- methods, anonymous
- code analysis, anonymous methods
- anonymous methods, code analysis
ms.assetid: bf0a1a9b-b954-4d46-9c0b-cee65330ad00
dev_langs:
- CSharp
- VB
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: a10c5baaed3a98e44d581b6ddb8d6e3a1883d079
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62560232"
---
# <a name="anonymous-methods-and-code-analysis"></a>Anonymní metody a analýza kódu

*Anonymní metoda* je metoda, která nemá žádný název. Anonymní metody se nejčastěji používají k předání bloku kódu jako parametr delegátu. Tento článek vysvětluje, jak analýzy kódu zpracovává upozornění a metriky pro anonymní metody.

## <a name="anonymous-methods-declared-in-a-member"></a>Anonymní metody s deklarací v člena

Upozornění a metriky pro anonymní metody, která je deklarována v členu, například metoda nebo přístupový objekt, jsou spojeny s člena, který deklaruje metodu. Nejsou přidružené člena, který volá metodu.

Například ve třídě následující upozornění, které se nacházejí v deklaraci **anonymousMethod** by měla být zvýšena proti **– metoda1** a ne **Method2**.

```vb
Delegate Function ADelegate(ByVal value As Integer) As Boolean

Class AClass
    Sub Method1()
        Dim anonymousMethod As ADelegate = Function(ByVal value As Integer) value > 5
        Method2(anonymousMethod)
    End Sub
    Sub Method2(ByVal anonymousMethod As ADelegate)
        anonymousMethod(10)
    End Sub
End Class
```

```csharp
delegate void Delegate();

class Class
{
    void Method1()
    {
        Delegate anonymousMethod = delegate()
        {
          Console.WriteLine("");
        }
        Method2(anonymousMethod);
    }

    void Method2(Delegate anonymousMethod)
    {
        anonymousMethod();
    }
}
```

## <a name="inline-anonymous-methods"></a>Vložené anonymní metody

Upozornění a metriky pro anonymní metody, která je deklarována jako vložené přiřazení k poli jsou spojeny s konstruktoru. Pokud toto pole je deklarován jako `static` (`Shared` v jazyce Visual Basic), upozornění a metriky, které jsou spojeny s konstruktoru třídy. V opačném případě jsou spojeny s konstruktor instance.

Například ve třídě následující upozornění, které se nacházejí v deklaraci **anonymousMethod1** proti implicitně generovaný výchozí konstruktor třídy, bude vyvolána **třídy**. Upozornění, které se nacházejí v **anonymousMethod2** se uplatňuje třídy implicitně generovaný konstruktor.

```vb
Delegate Function ADelegate(ByVal value As Integer) As Boolean
Class AClass
    Dim anonymousMethod1 As ADelegate = Function(ByVal value As Integer) value > 5
    Shared anonymousMethod2 As ADelegate = Function(ByVal value As Integer) value > 5

    Sub Method1()
        anonymousMethod1(10)
        anonymousMethod2(10)
    End Sub
End Class
```

```csharp
delegate void Delegate();

class Class
{
    Delegate anonymousMethod1 = delegate()
    {
       Console.WriteLine("");
    }

    static Delegate anonymousMethod2 = delegate()
    {
       Console.WriteLine("");
    }

    void Method()
    {
       anonymousMethod1();
       anonymousMethod2();
    }
}
```

Třída může obsahovat vložené anonymní metody, který přiřazuje hodnotu pole, která má víc konstruktorů. V takovém případě metriky a upozorněními jsou spojeny s všechny konstruktory není-li tento konstruktor zřetězený jiný konstruktor ve stejné třídě.

Například ve třídě následující upozornění, které se nacházejí v deklaraci **anonymousMethod** by měla být zvýšena proti **Class(int)** a **Class(string)**, ale Ne před **Class()**.

```vb
Delegate Function ADelegate(ByVal value As Integer) As Boolean

Class AClass

    Dim anonymousMethod As ADelegate = Function(ByVal value As Integer) value > 5

    SubNew()
        New(CStr(Nothing))
    End Sub

    Sub New(ByVal a As Integer)
    End Sub

    Sub New(ByVal a As String)
    End Sub
End Class
```

```csharp
delegate void Delegate();

class Class
{
    Delegate anonymousMethod = delegate()
    {
       Console.WriteLine("");
    }

    Class() : this((string)null)
    {
    }

    Class(int a)
    {
    }

    Class(string a)
    {
    }
}
```

Upozornění jsou vyvolány proti konstruktory, protože kompilátor výstupy metodu jedinečný pro každý konstruktor, který není zřetězený ke jiného konstruktoru. Kvůli tomuto chování nedodržení, která nastane v **anonymousMethod** musí být potlačeno samostatně. To také znamená, že pokud je nový konstruktor zavedená, upozornění, které byly dříve potlačeny proti **Class(int)** a **Class(string)** musí také být potlačeno proti nový konstruktor.

Můžete alternativně vyřešit tento problém v jednom ze dvou způsobů:

- Deklarovat **anonymousMethod** v běžných konstruktor, který všechny konstruktory řetězce.
- Deklarovat **anonymousMethod** v inicializační metoda, která je volána všechny konstruktory.

## <a name="see-also"></a>Viz také:

- [Analýza kvality spravovaného kódu](../code-quality/code-analysis-for-managed-code-overview.md)