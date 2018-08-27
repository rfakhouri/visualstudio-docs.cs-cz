---
title: 'CA1062: Ověřte argumenty veřejných metod | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- CA1062
- ValidateArgumentsOfPublicMethods
- Validate arguments of public methods
helpviewer_keywords:
- CA1062
- ValidateArgumentsOfPublicMethods
ms.assetid: db1f69ca-68f7-477e-94f3-d135cc5dfcbc
caps.latest.revision: 29
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 8fd4534c333dfe31801d13a99b6ee7b3f0c25e33
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/24/2018
ms.locfileid: "42902932"
---
# <a name="ca1062-validate-arguments-of-public-methods"></a>CA1062: Ověřte argumenty veřejných metod
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [CA1062: Ověřte argumenty veřejných metod](https://docs.microsoft.com/visualstudio/code-quality/ca1062-validate-arguments-of-public-methods).

|||
|-|-|
|TypeName|ValidateArgumentsOfPublicMethods|
|CheckId|CA1062|
|Kategorie|Microsoft.Design|
|Narušující změna|Pevné|

## <a name="cause"></a>příčina
 Externě viditelná metoda přístupů přes ukazatel, jeden z jeho argumenty odkazu bez ověření, zda je tento argument `null` (`Nothing` v jazyce Visual Basic).

## <a name="rule-description"></a>Popis pravidla
 Všechny argumenty odkazu předané externě viditelným metodám by měly být porovnány `null`. V případě potřeby, vyvolejte <xref:System.ArgumentNullException> když má argument hodnotu `null`.

 Pokud metodu lze volat z neznámého sestavení, protože je deklarována jako veřejná nebo chráněná, měli byste ověřit všechny parametry metody. Pokud metoda je navržen pro být volány pouze známé sestavení, by měl provést metodu interní a použít <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> atribut sestavení, který obsahuje metodu.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, ověřit každý argument odkazu proti `null`.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Toto pravidlo upozornění můžete potlačit, pokud jste si jistí, že parametr přes ukazatel byl ověřen voláním jiného volání metody ve funkci.

## <a name="example"></a>Příklad
 Následující příklad ukazuje metodu, která porušuje pravidlo a metodu, která splňuje pravidlo.

 [!code-csharp[FxCop.Design.ValidateArguments#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.ValidateArguments/cs/fxcop.design.validatearguments.copyctors.cs#1)]
 [!code-csharp[FxCop.Design.ValidateArguments#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.ValidateArguments/cs/FxCop.Design.ValidateArguments.cs#1)]
 [!code-vb[FxCop.Design.ValidateArguments#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Design.ValidateArguments/vb/FxCop.Design.ValidateArguments.vb#1)]

## <a name="example"></a>Příklad
 V [!INCLUDE[vsprvslong](../includes/vsprvslong-md.md)], toto pravidlo nemůže zjistit, že parametry jsou předávány na jinou metodu, která provádí ověření.

 [!code-csharp[FxCop.Design.ValidateArguments#2](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.ValidateArguments/cs/fxcop.design.validatearguments.copyctors.cs#2)]
 [!code-csharp[FxCop.Design.ValidateArguments#2](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.ValidateArguments/cs/FxCop.Design.ValidateArguments.cs#2)]
 [!code-vb[FxCop.Design.ValidateArguments#2](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Design.ValidateArguments/vb/FxCop.Design.ValidateArguments.vb#2)]

## <a name="example"></a>Příklad
 Kopírovací konstruktory, které pole nebo vlastnosti, které jsou objekty referenční naplnění také CA1062 pravidla porušit. Porušení dojde, protože může být zkopírovaný objektu, který je předán konstruktoru kopie `null` (`Nothing` v jazyce Visual Basic). Chcete-li vyřešit porušení zásad, můžete metodu statické (sdílené v jazyce Visual Basic) zkontrolujte, zda zkopírovaný objektu není null.

 V následujícím `Person` příklad třídy, `other` objekt, který je předán `Person` může být kopírovací konstuktor `null`.

```

public class Person
{
    public string Name { get; private set; }
    public int Age { get; private set; }

    public Person(string name, int age)
    {
        Name = name;
        Age = age;
    }

    // Copy constructor CA1062 fires because other is dereferenced
    // without being checked for null
    public Person(Person other)
        : this(other.Name, other.Age)
    {
    }
}

```

## <a name="example"></a>Příklad
 Následující revize `Person` například `other` objekt, který je předán konstruktoru kopie se nejdříve kontroluje u hodnoty null v `PassThroughNonNull` metody.

```
public class Person
{
    public string Name { get; private set; }
    public int Age { get; private set; }

    public Person(string name, int age)
    {
        Name = name;
        Age = age;
    }

    // Copy constructor
    public Person(Person other)
        : this(PassThroughNonNull(other).Name,
          PassThroughNonNull(other).Age)
    {
    }

    // Null check method
    private static Person PassThroughNonNull(Person person)
    {
        if (person == null)
            throw new ArgumentNullException("person");
        return person;
    }
}

```



