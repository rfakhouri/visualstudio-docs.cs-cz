---
title: Fragmenty kódu
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
f1_keywords:
- vs.ExpansionManagerImport
- vs.codesnippetmanager
helpviewer_keywords:
- surround with
- code snippets
author: gewarren
ms.author: gewarren
manager: douge
dev_langs:
- CSharp
- VB
- CPP
ms.workload:
- multiple
ms.openlocfilehash: 2d41a5a3995c9c93f17f090e5befc10a0bd544c3
ms.sourcegitcommit: d9e4ea95d0ea70827de281754067309a517205a1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/29/2018
ms.locfileid: "37117209"
---
# <a name="code-snippets"></a>Fragmenty kódu

Fragmenty kódu jsou malé bloky opakovaně použitelný kód, který lze vložit do souboru kódu s použitím příkazu nabídky kontext nebo kombinace klávesových zkratek. Obvykle obsahují bloky kódu běžně používané jako `try-finally` nebo `if-else` bloky, ale slouží k vložení celé třídy nebo metody.

Fragmenty kódu jsou k dispozici pro různé jazyky, včetně C#, C++, Visual Basic, XML a T-SQL, a další. Chcete-li zobrazit všechny dostupné nainstalované fragmenty kódu pro jazyk, otevřete **Správce fragmentů kódu** z **nástroje** nabídky v sadě Visual Studio a zvolte jazyk, z rozevírací nabídky v horní části.

![Dialogové okno Správce fragmentů kódu](media/code-snippets-manager.png)

Fragmenty kódu jsou přístupné obecné takto:

- Na řádku nabídek zvolte **upravit** > **IntelliSense** > **Vložit fragment kódu**

- V nabídce klikněte pravým tlačítkem nebo kontextu v editoru kódu, zvolte **fragment kódu** > **Vložit fragment kódu**

- Pomocí klávesnice, stiskněte klávesu **Ctrl**+**tisíc**+**X**

## <a name="expansion-snippets-and-surround-with-snippets"></a>Rozšíření fragmenty a obklopit fragmenty

V sadě Visual Studio jsou dva druhy fragment kódu: fragmenty rozšíření, které jsou přidány do zadaného kurzoru a může nahradit zástupce fragment kódu a příkazu Obklopit s s fragmenty (C# a C++ pouze), které jsou přidány kolem vybraného bloku kódu.

Příkladem fragment rozšíření: v jazyce C# tryf zástupce slouží k vložení blok try-finally –:

```csharp
try
{

}
finally
{

}
```

Kliknutím můžete vložit tento fragment kódu **Vložit fragment** v místní nabídce okně kódu, pak **Visual C#**, pak zadejte `tryf`a potom stiskněte klávesu **kartě**. Nebo můžete zadat `tryf` a stiskněte klávesu **kartě** dvakrát.

Příkladem fragment obklopit: v jazyce C++ zástupce `if` lze použít jako fragment vložení nebo jako fragment obklopit. Pokud vyberete řádek kódu (například `return FALSE;`) a potom zvolte **příkazu Obklopit s** > **Pokud**, fragmentu je rozšířena kolem řádku:

```cpp
if (true)
{
    return FALSE;
}
```

## <a name="snippet-replacement-parameters"></a>Fragment kódu nahrazující parametry

Fragmenty kódu může obsahovat nahrazující parametry, které jsou zástupné symboly, které je třeba nahradit podle přesné kód, který vytváříte. V předchozím příkladu `true` je parametr nahrazení, který by nahraďte vhodné podmínky. Nahrazení, které se opakuje pro každou instanci parametr nahrazení v tomto fragmentu kódu.

Například v jazyce Visual Basic není fragment kódu, která vloží vlastnost. Chcete-li vložit fragment, zvolte **fragment kódu** > **Vložit fragment** v nabídce klikněte pravým tlačítkem nebo kontextu v souboru kódu jazyka Visual Basic. Pak zvolte **kódu, které vypadají** > **vlastnosti, postupy, události** > **definovat vlastnost**.

![Nabídka fragmentu kódu pro definování vlastnosti](media/code-snippets-vb-property.png)

Následující kód je vložen:

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

Pokud změníte `newPropertyValue` k `m_property`, pak všechny instance řetězce `newPropertyValue` se změnilo. Pokud změníte `String` k `Int` v deklarace vlastnosti pak hodnota v set se také změní na `Int`.

## <a name="see-also"></a>Viz také:

- [Návod: Vytvoření fragmentu kódu](../ide/walkthrough-creating-a-code-snippet.md)
- [Postupy: distribuce fragmentů kódu](../ide/how-to-distribute-code-snippets.md)
- [Osvědčené postupy pro používání fragmentů kódu](../ide/best-practices-for-using-code-snippets.md)
- [Řešení potíží s fragmenty kódu](../ide/troubleshooting-snippets.md)
- [Fragmenty kódu v C#](../ide/visual-csharp-code-snippets.md)
- [Fragmenty kódu Visual C++](../ide/visual-cpp-code-snippets.md)
- [Referenční informace ke schématu fragmentů kódu](../ide/code-snippets-schema-reference.md)