---
title: Fragmenty kódu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.ExpansionManagerImport
- vs.codesnippetmanager
helpviewer_keywords:
- surround with
- code snippets
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
- CPP
ms.workload:
- multiple
ms.openlocfilehash: 89de993337ecd214c7771faf17b24f90fa5e0110
ms.sourcegitcommit: 0f44ec8ba0263056ad04d2d0dc904ad4206ce8fc
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/06/2019
ms.locfileid: "70766258"
---
# <a name="code-snippets"></a>Fragmenty kódu

Fragmenty kódu jsou malé bloky opakovaně použitelného kódu, který lze vložit do souboru kódu pomocí příkazu nabídky po kliknutí pravým tlačítkem myši (kontextová nabídka) nebo kombinace klávesových zkratek. Obvykle obsahují často používané bloky kódu, například `try-finally` nebo `if-else` bloky, ale lze je použít k vložení celé třídy nebo metod.

> [!NOTE]
> Toto téma se vztahuje k sadě Visual Studio ve Windows. Visual Studio pro Mac naleznete v tématu [fragmenty kódu (Visual Studio pro Mac)](/visualstudio/mac/snippets).

Fragmenty kódu jsou k dispozici pro mnoho jazyků, včetně C#, C++, Visual Basic, XML a T-SQL, pro pojmenování. Chcete-li zobrazit všechny dostupné fragmenty nainstalované pro jazyk, otevřete **Správce fragmentů kódů** z nabídky **nástroje** (nebo stiskněte klávesy **CTRL**+**K**, **CTRL**+**B**) a zvolte jazyk z rozevírací nabídka v horní části.

![Dialogové okno Správce fragmentů kódů](media/code-snippets-manager.png)

K fragmentům kódu je možné přistupovat následujícími obecnými způsoby:

- Na panelu nabídek vyberte možnost **Upravit** > **IntelliSense** > **Vložit fragment** .

- V editoru kódu kliknutím pravým tlačítkem myši nebo v místní nabídce vyberte **fragment** > kódu**Vložit fragment**

- Na klávesnici stiskněte klávesu **CTRL**+**K**,**CTRL**+**X**

## <a name="expansion-snippets-and-surround-with-snippets"></a>Fragmenty rozšíření a obklopení s fragmenty

V aplikaci Visual Studio existují dva druhy fragmentů kódu: fragmenty rozšíření, které jsou přidány v zadaném místě vložení a mohou nahradit zástupce fragmentu a obklopit s fragmenty (C# a C++ pouze), které jsou přidány kolem vybraného bloku kódu.

Příklad fragmentu rozšíření: v C# místní tryf se používá k vložení bloku try-finally:

```csharp
try
{

}
finally
{

}
```

Tento fragment kódu můžete vložit kliknutím na **Vložit fragment** v místní nabídce (kontextové nabídce) v okně Code (kontextová nabídka), potom na **vizuál C#** , `tryf`zadáním a stisknutím klávesy **TAB**. Nebo můžete zadat `tryf` a stisknout klávesu **TAB** dvakrát.

Příklad obklopit s fragmentem kódu: v C++ zástupce `if` lze použít buď jako fragment vložení, nebo jako obklopit s fragmentem kódu. Pokud vyberete řádek kódu `return FALSE;`(například) a pak zvolíte možnost **uzavřít pomocí** > **if**, fragment kódu se rozbalí kolem řádku:

```cpp
if (true)
{
    return FALSE;
}
```

## <a name="snippet-replacement-parameters"></a>Parametry nahrazení fragmentů

Fragmenty kódu mohou obsahovat náhradní parametry, což jsou zástupné symboly, které je nutné nahradit, aby odpovídaly přesnému kódu, který píšete. V předchozím příkladu `true` je náhradní parametr, který byste nahradili příslušnou podmínkou. Náhrada, kterou provedete, se opakuje pro každou instanci stejného parametru nahrazení ve fragmentu.

Například v Visual Basic existuje fragment kódu, který vloží vlastnost. Chcete-li **Vložit fragment kódu, vyberte možnost** > **Vložit fragment kódu** z místní nabídky nebo z kontextové nabídky v souboru kódu Visual Basic. Pak zvolte vlastnosti **vzorů** > kódu **, procedury, události** > **definují vlastnost**.

![Nabídka fragmentu kódu pro definování vlastnosti](media/code-snippets-vb-property.png)

Je vložen následující kód:

```vb
Private newPropertyValue As String
Public Property NewProperty() As String
    Get
        Return newPropertyValue
    End Get
    Set(ByVal value As String)
        newPropertyValue = value
    End Set
End Property
```

Změníte `newPropertyValue` -li na `m_property` `newPropertyValue` , pak dojde ke změně každé instance. Pokud se v `String` deklaraci vlastnosti změní na `Int` , pak je hodnota v metodě set také změněna na `Int`.

## <a name="see-also"></a>Viz také:

- [Návod: Vytvoření fragmentu kódu](../ide/walkthrough-creating-a-code-snippet.md)
- [Postupy: Distribuce fragmentů kódu](../ide/how-to-distribute-code-snippets.md)
- [Osvědčené postupy pro používání fragmentů kódu](../ide/best-practices-for-using-code-snippets.md)
- [Řešení potíží s fragmenty](../ide/troubleshooting-snippets.md)
- [C#fragmenty kódu](../ide/visual-csharp-code-snippets.md)
- [Vizuální C++ fragmenty kódu](../ide/visual-cpp-code-snippets.md)
- [Referenční informace ke schématu fragmentů kódu](../ide/code-snippets-schema-reference.md)
- [Fragmenty kódu (Visual Studio pro Mac)](/visualstudio/mac/snippets)
