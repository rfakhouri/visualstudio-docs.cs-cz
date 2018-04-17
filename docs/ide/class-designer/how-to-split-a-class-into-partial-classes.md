---
title: 'Postupy: rozdělení třídy na částečné třídy (návrhář tříd) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
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
ms.openlocfilehash: 672f0c5a6170b169e9fcfff6332724e2e1bff62f
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-split-a-class-into-partial-classes-class-designer"></a>Postupy: Rozdělení třídy na částečné třídy (návrhář tříd)
Prohlášení o třídu nebo strukturu mezi několik deklarace můžete rozdělit pomocí `Partial` – klíčové slovo v jazyce Visual Basic nebo `partial` – klíčové slovo v jazyce C#. Můžete vytvořit tolik částečné deklarace tak, jak chcete v tolik jiných zdrojových souborů, nebo do jednoho zdrojového souboru. Všechny deklarace však musí být ve stejném sestavení a o stejný obor názvů.  
  
Částečné třídy jsou užitečné v několika situacích. Při práci na velkých projektech, například třída rozdělit do více než jeden soubor umožňuje více než jeden programátory v práci ve stejnou dobu. Při práci s kódem, který generuje Visual Studio, můžete změnit třída bez nutnosti znovu vytvořit zdrojový soubor. (Kód, který generuje Visual Studio příklady kódu obálky Windows Forms a Web Service.) Můžete vytvořit tak kód, který používá automaticky vygenerované třídy, aniž by bylo nutné upravit soubor, který Visual Studio vytvoří.  
  
Existují dva druhy částečné metody. V jazyce C# označují se jako deklarace a implementace; v jazyce Visual Basic se nazývají deklarace a implementaci.  
  
Návrhář tříd podporuje částečné třídy a metody. Obrazce typu v diagramu tříd odkazuje na umístění jediné deklaraci pro třídu. Pokud třídu je definováno ve více souborech, můžete zadat umístění které deklarace návrhář tříd použije nastavením **nové umístění člen** vlastnost **vlastnosti** okno. To znamená, když dvakrát kliknete na obrazec Třída návrhář tříd, které se přejde na zdrojový soubor, který obsahuje deklaraci třídy, které se identifikovanou pomocí **nové umístění člen** vlastnost. Když dvakrát kliknete na částečné metoda ve tvaru třída návrhář tříd přejde na deklarace částečné metody. Také v **vlastnosti** okně **název souboru** vlastnost odkazuje na umístění deklarace. Pro částečné třídy **název souboru** uvádí všechny soubory, které obsahují deklarace a implementaci kód pro tuto třídu. Pro částečné metody, ale **název souboru** uvádí jenom soubor, který obsahuje deklarace částečné metody.  
  
Následující příklady rozdělení definice třídy `Employee` do dvou deklarace, z nichž každý definuje jiný postup. Dva částečné definice v příkladech může být do jednoho zdrojového souboru nebo ve dvou různých zdrojové soubory.  
  
> [!NOTE]
>  Visual Basic používá definice částečné třídy pro oddělení Visual Studio – generovaného kódu z uživatelem definovaných kódu. Kód je rozdělené na samostatné zdrojové soubory. Například **Windows Form Designer** definuje částečné třídy pro ovládací prvky, jako `Form`. Neměli upravovat generovaného kódu v těchto ovládacích prvků.  
  
Další informace o částečné typy v jazyce Visual Basic najdete v tématu [částečné](/dotnet/visual-basic/language-reference/modifiers/partial).  
  
## <a name="example"></a>Příklad  
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

## <a name="example"></a>Příklad  
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
[Částečné třídy a metody](/dotnet/csharp/programming-guide/classes-and-structs/partial-classes-and-methods)   
[partial (typ)](/dotnet/csharp/language-reference/keywords/partial-type)   
[partial (metoda) (referenční dokumentace jazyka C#)](/dotnet/csharp/language-reference/keywords/partial-method)   
[Partial](/dotnet/visual-basic/language-reference/modifiers/partial)