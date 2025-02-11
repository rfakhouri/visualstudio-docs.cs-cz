---
title: 'Postupy: Rozdělení třídy na částečné třídy (návrhář tříd) | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- Class Designer, partial classes
- partial classes, Class Designer
ms.assetid: 6f6b0b30-3996-4569-9200-20482b3adf90
caps.latest.revision: 14
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 23d344d2f350b5b7a2e376e8856c916d9baa01f2
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2019
ms.locfileid: "65702614"
---
# <a name="how-to-split-a-class-into-partial-classes-class-designer"></a>Postupy: Rozdělení třídy na částečné třídy (návrhář tříd)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Deklarace třídy nebo struktury mezi několik deklarací můžete rozdělit pomocí `Partial` – klíčové slovo v jazyce Visual Basic nebo `partial` – klíčové slovo v jazyce Visual C#. Můžete použít tolik částečné deklarace chcete v tolika jiných zdrojových souborů, nebo v jednom zdrojovém souboru. Všechny deklarace však musí být ve stejném sestavení a stejný obor názvů.  
  
 Částečné třídy jsou užitečné v několika situacích. Například při práci na velkých projektech oddělení třídu do více než jeden soubor umožňuje více než jeden programátorovi, aby na něm pracovat ve stejnou dobu. Při práci s kódem, který generuje sada Visual Studio, můžete změnit třídu bez nutnosti znovu vytvářet zdrojový soubor. (Příklady kódu, který generuje sada Visual Studio zahrnují kód obálku Windows Forms a webové služby.) Můžete tedy vytvořit kód, který používá automaticky generovaný třídy, aniž byste museli upravovat soubor, který sada Visual Studio vytvoří.  
  
 Existují dva druhy částečné metody. V jazyce Visual C# jsou volány deklarace a implementaci; v jazyce Visual Basic se nazývají deklaraci a implementaci.  
  
 Návrhář tříd podporuje částečné třídy a metody. Tvar typu v diagramu tříd, odkazuje na umístění jediné deklaraci částečné třídy. Pokud je částečná třída definovaná ve více souborech, můžete zadat umístění které deklarace návrhář tříd použijete tak, že nastavíte **umístění nového člena** vlastnost v **vlastnosti** okna. To znamená, když dvakrát kliknete na tvar třídy, návrhář tříd se dostane do zdrojového souboru, který obsahuje deklaraci třídy, který je identifikován **umístění nového člena** vlastnost. Když dvakrát kliknete na částečné metody ve třídě tvaru, návrhář tříd přejde na deklaraci částečné metody. Také v **vlastnosti** okně **název_souboru** vlastnost odkazuje na umístění prohlášení. Pro částečné třídy **název_souboru** uvádí všechny soubory, které obsahují deklarace a implementaci kód pro danou třídu. Ale pro částečné metody **název_souboru** obsahuje pouze soubor, který obsahuje deklaraci částečné metody.  
  
 Následující příklady rozdělení definice třídy `Employee` do dvě deklarace, z nichž každý definuje jiný postup. Dvě Částečná definice v příkladech může být v jednom zdrojovém souboru nebo ve dvou různých zdrojových souborů.  
  
> [!NOTE]
> Visual Basic používá definicí částečné třídy pro oddělení sady Visual Studio – kód generovaný z uživatelem definovaných kódu. Kód je rozdělené na samostatné zdrojové soubory. Například **Návrhář formulářů Windows** definuje částečné třídy pro ovládací prvky, jako `Form`. Generovaný kód v těchto ovládacích prvků byste neměli měnit.  
  
 Další informace o částečné typy v jazyce Visual Basic najdete v tématu [částečné](https://msdn.microsoft.com/library/7adaef80-f435-46e1-970a-269fff63b448).  
  
## <a name="example"></a>Příklad  
 Pro rozdělení definice třídy v jazyce Visual Basic, použijte `Partial` – klíčové slovo, jak je znázorněno v následujícím příkladu.  
  
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
 Pro rozdělení definice třídy v jazyce Visual C#, použijte `partial` – klíčové slovo, jak je znázorněno v následujícím příkladu.  
  
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
 [Částečné třídy a metody](https://msdn.microsoft.com/library/804cecb7-62db-4f97-a99f-60975bd59fa1)   
 [partial (typ)](https://msdn.microsoft.com/library/27320743-a22e-4c7b-b0b3-53afe3607334)   
 [partial (metoda) (referenční dokumentace jazyka C#)](https://msdn.microsoft.com/library/43f40242-17e0-4452-8573-090503ad3137)   
 [Partial](https://msdn.microsoft.com/library/7adaef80-f435-46e1-970a-269fff63b448)
