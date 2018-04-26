---
title: 'Postupy: Rozdělení třídy na částečné třídy (návrhář tříd)'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- Class Designer, partial classes
- partial classes, Class Designer
ms.assetid: 6f6b0b30-3996-4569-9200-20482b3adf90
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 3d0aa5b844b3743ab80c11971caa26340effe671
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-split-a-class-into-partial-classes-class-designer"></a>Postupy: rozdělení třídy na částečné třídy (návrhář tříd)

Můžete použít `partial` – klíčové slovo (`Partial` v jazyce Visual Basic) k rozdělení deklaraci třídu nebo strukturu mezi několik deklarace. Můžete vytvořit tolik částečné deklarace podle potřeby.

Deklarací může být v jednom nebo více zdrojových souborů. Všechny deklarace musí být ve stejném sestavení a o stejný obor názvů.

Částečné třídy jsou užitečné v několika situacích. Na velkých projektech například třída rozdělit do několika souborů umožňuje více než jeden programátory pro práci na projekt současně. Při práci s kódem, který generuje Visual Studio, můžete změnit třída bez nutnosti znovu vytvořit zdrojový soubor. (Kód, který generuje Visual Studio příklady kódu obálky Windows Forms a Web Service.) Můžete vytvořit tak kód, který používá automaticky vygenerované třídy, aniž by bylo nutné upravit soubor, který Visual Studio vytvoří.

Existují dva druhy částečné metody. V jazyce C# označují se jako deklarace a implementace; v jazyce Visual Basic se nazývají deklarace a implementaci.

**Třídy návrháře** podporuje částečné třídy a metody. Obrazce typu v diagramu tříd odkazuje na umístění jediné deklaraci pro třídu. Pokud třídu je definováno ve více souborech, můžete zadat umístění které deklarace **návrhář tříd** použije nastavením **nové umístění člen** vlastnost **vlastnosti**  okno. To znamená, když dvakrát kliknete na obrazec Třída **návrhář tříd** přejde ke zdrojovému souboru, který obsahuje deklaraci třídy, které se identifikovanou pomocí **nové umístění člen** vlastnost. Když dvakrát kliknete na částečné metoda v obrazci třídy **návrhář tříd** přejde do deklarace částečné metody. Také v **vlastnosti** okně **název souboru** vlastnost odkazuje na umístění deklarace. Pro částečné třídy **název souboru** uvádí všechny soubory, které obsahují deklarace a implementaci kód pro tuto třídu. Pro částečné metody, ale **název souboru** uvádí jenom soubor, který obsahuje deklarace částečné metody.

Následující příklady rozdělení definice třídy `Employee` do dvou deklarace, z nichž každý definuje jiný postup. Dva částečné definice v příkladech může být do jednoho zdrojového souboru nebo ve dvou různých zdrojové soubory.

> [!NOTE]
> Visual Basic používá definice částečné třídy pro oddělení Visual Studio – generovaného kódu z uživatelem definovaných kódu. Kód je rozdělené na samostatné zdrojové soubory. Například **Windows Form Designer** definuje částečné třídy pro ovládací prvky, jako `Form`. Neměli upravovat generovaného kódu v těchto ovládacích prvků.


Další informace o částečné typy v jazyce Visual Basic najdete v tématu [částečné](/dotnet/visual-basic/language-reference/modifiers/partial).

## <a name="visual-basic-example"></a>Příklad jazyka Visual Basic

Rozdělení definice třídy v jazyce Visual Basic, použijte `Partial` – klíčové slovo, jak je znázorněno v následujícím příkladu.

```vb
' First part of class definition.
Partial Public Class Employee
    Public Sub CalculateWorkHours()
    End Sub
End Class

' Second part of class definition.
Partial Public Class Employee
    Public Sub CalculateTaxes()
    End Sub
End Class
```

## <a name="c-example"></a>Příklad jazyka C#

Rozdělení definice třídy v jazyce C#, použijte `partial` – klíčové slovo, jak je znázorněno v následujícím příkladu.

```csharp
// First part of class definition.
public partial class Employee
{
    public void CalculateWorkHours()
    {
    }
}

// Second part of class definition.
public partial class Employee
{
    public void CalculateTaxes()
    {
    }
}
```

## <a name="see-also"></a>Viz také

- [Částečné třídy a metody](/dotnet/csharp/programming-guide/classes-and-structs/partial-classes-and-methods)
- [partial (typ)](/dotnet/csharp/language-reference/keywords/partial-type)
- [partial (metoda) (referenční dokumentace jazyka C#)](/dotnet/csharp/language-reference/keywords/partial-method)
- [Partial](/dotnet/visual-basic/language-reference/modifiers/partial)