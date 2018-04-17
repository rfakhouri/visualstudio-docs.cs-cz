---
title: Fragmenty kódu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: 520aa870f85ddc3768720eafb17b0109fb270393
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="code-snippets"></a>Fragmenty kódu

Fragmenty kódu jsou malé bloky opakovaně použitelný kód, který lze vložit do souboru kódu s použitím příkazu nabídky kontext nebo kombinace klávesových zkratek. Obvykle obsahují bloky kódu se často používá jako `try-finally` nebo `if-else` bloky, ale slouží k vložení celé třídy nebo metody.

Fragmenty kódu jsou k dispozici pro různé jazyky, včetně C#, C++, Visual Basic, XML a T-SQL, a další. Chcete-li zobrazit všechny dostupné nainstalované fragmenty kódu pro jazyk, otevřete **Správce fragmentů kódu** z **nástroje** nabídky v sadě Visual Studio a zvolte jazyk, z rozevírací nabídky v horní části.

![Dialogové okno Správce fragmentů kódu](media/code-snippets-manager.png)

Fragmenty kódu jsou přístupné obecné takto:

- Na řádku nabídek zvolte **upravit** > **IntelliSense** > **Vložit fragment...**

- V nabídce klikněte pravým tlačítkem nebo kontextu v editoru kódu, zvolte **fragment kódu** > **Vložit fragment...**

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

Například v jazyce Visual Basic není fragment kódu, která vloží vlastnost. Chcete-li vložit fragment, zvolte **fragment kódu...**   >  **Vložit fragment** v nabídce klikněte pravým tlačítkem nebo kontextu v souboru kódu jazyka Visual Basic. Pak zvolte **kódu, které vypadají** > **vlastnosti, postupy, události** > **definovat vlastnost**.

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

## <a name="see-also"></a>Viz také

[Návod: Vytvoření fragmentu kódu](../ide/walkthrough-creating-a-code-snippet.md)  
[Postupy: distribuce fragmentů kódu](../ide/how-to-distribute-code-snippets.md)  
[Osvědčené postupy pro používání fragmentů kódu](../ide/best-practices-for-using-code-snippets.md)  
[Řešení potíží s fragmenty kódu](../ide/troubleshooting-snippets.md)  
[Fragmenty kódu v C#](../ide/visual-csharp-code-snippets.md)  
[Fragmenty kódu Visual C++](../ide/visual-cpp-code-snippets.md)  
[Fragmenty kódu – odkaz schématu](../ide/code-snippets-schema-reference.md)