---
title: "CA1062: Ověřte argumenty veřejných metod | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA1062
- ValidateArgumentsOfPublicMethods
- Validate arguments of public methods
helpviewer_keywords:
- CA1062
- ValidateArgumentsOfPublicMethods
ms.assetid: db1f69ca-68f7-477e-94f3-d135cc5dfcbc
caps.latest.revision: "27"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: eb659fa8bfd18d8caf4a7473f6cd53809d0a126b
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="ca1062-validate-arguments-of-public-methods"></a>CA1062: Ověřte argumenty veřejných metod
|||  
|-|-|  
|TypeName|ValidateArgumentsOfPublicMethods|  
|CheckId|CA1062|  
|Kategorie|Microsoft.Design|  
|Narušující změna|Bez ukončování řádků|  
  
## <a name="cause"></a>příčina  
 Metodu externě viditelné dereferences jeden z jeho argumentů odkazu bez ověření, zda je daný argument `null` (`Nothing` v jazyce Visual Basic).  
  
## <a name="rule-description"></a>Popis pravidla  
 Je třeba zkontrolovat všechny argumenty odkaz, které se budou předávat externě viditelné metody `null`. V případě potřeby throw <xref:System.ArgumentNullException> když argument je `null`.  
  
 Pokud metodu lze volat z neznámé sestavení, protože je deklarovaná veřejných nebo chráněné, měli byste ověřit, všechny parametry metody. Pokud metoda je navržená tak, že má být volána pouze známé sestavení, měli byste Zkontrolujte metodu interní a použít <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> atribut sestavení, které obsahuje metodu.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Opravit porušení toto pravidlo, ověření každého argumentu odkaz proti `null`.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Upozornění od tohoto pravidla můžete potlačit, pokud jste si jistí, že parametr dereferenced byl ověřen voláním jiné metody ve funkci.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje metodu, která porušuje pravidlo a metodu, která splňuje pravidlo.  
  
 ```csharp
 using System;

namespace DesignLibrary
{
    public class Test
    {
        // This method violates the rule.
        public void DoNotValidate(string input)
        {
            if (input.Length != 0)
            {
                Console.WriteLine(input);
            }
        }

        // This method satisfies the rule.
        public void Validate(string input)
        {
            if (input == null)
            {
                throw new ArgumentNullException("input");
            }
            if (input.Length != 0)
            {
                Console.WriteLine(input);
            }
        }
    }
}
```

```vb
Imports System

Namespace DesignLibrary

    Public Class Test

        ' This method violates the rule.
        Sub DoNotValidate(ByVal input As String)

            If input.Length <> 0 Then
                Console.WriteLine(input)
            End If

        End Sub

        ' This method satisfies the rule.
        Sub Validate(ByVal input As String)

            If input Is Nothing Then
                Throw New ArgumentNullException("input")
            End If

            If input.Length <> 0 Then
                Console.WriteLine(input)
            End If

        End Sub

    End Class

End Namespace
```
  
## <a name="example"></a>Příklad  
 V [!INCLUDE[vsprvslong](../code-quality/includes/vsprvslong_md.md)], toto pravidlo nezjistí, že parametry jsou předávány na jinou metodu, která provádí ověření.  

```csharp
public string Method(string value)
{
    EnsureNotNull(value);

    // Fires incorrectly    
    return value.ToString();
}

private void EnsureNotNull(string value)
{
    if (value == null)
        throw new ArgumentNullException("value");
}
```

```vb
Public Function Method(ByVal value As String) As String
    EnsureNotNull(value)

    ' Fires incorrectly    
    Return value.ToString()
End Function

Private Sub EnsureNotNull(ByVal value As String)
    If value Is Nothing Then
        Throw (New ArgumentNullException("value"))
    End If
End Sub
```

## <a name="example"></a>Příklad  
 Kopírovací konstruktory, která naplní pole nebo vlastnosti, které jsou objekty odkaz můžete také porušení CA1062 pravidlo. Vzhledem k tomu může být zkopírovaný objekt, který je předán konstruktor copy, dojde k narušení `null` (`Nothing` v jazyce Visual Basic). K vyřešení porušení zásady, použijte statickou metodu (sdílené v jazyce Visual Basic) zkontrolujte, že objekt zkopírovaný není null.  
  
 V následujícím `Person` příkladu třída `other` objekt, který je předán `Person` kopírovací konstruktor může být `null`.  
  
```csharp  
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
 V následující revize `Person` například `other` objekt, který je předán konstruktor copy, nejprve se kontroluje na null v `PassThroughNonNull` metoda.  
  
```csharp  
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