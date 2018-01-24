---
title: "Fragmenty kódu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.ExpansionManagerImport
- vs.codesnippetmanager
helpviewer_keywords:
- code snippets, replacement parameters
- code snippets, surround with
- replacement parameters
- code snippets, expansion
- surround with
- code snippets
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: e2b973b00e132973b8569bc5cad8c1f1318317cd
ms.sourcegitcommit: 49aa031cbebdd9c7ec070c713afb1a97d1ecb701
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2018
---
# <a name="code-snippets"></a>Fragmenty kódu

Fragmenty kódu jsou malé bloky opakovaně použitelný kód, který lze vložit do souboru kódu s použitím příkazu nabídky kontext nebo kombinace klávesových zkratek. Obvykle obsahují bloky kódu se často používá jako je například try-finally – nebo if-else bloky, ale slouží k vložení celé třídy nebo metody.

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

Kliknutím můžete vložit tento fragment kódu **Vložit fragment** v místní nabídce okně kódu, pak **Visual C#**, pak zadejte `tryf`a potom stiskněte klávesu **kartě**, nebo můžete můžete zadat `tryf` a stiskněte klávesu **kartě** dvakrát.

Příkladem fragment obklopit: v jazyce C++ zástupce `if` lze použít jako fragment vložení nebo jako fragment obklopit. Pokud vyberete řádek kódu (například `return FALSE;`) a potom klikněte na **příkazu Obklopit s**, pak **Pokud**, fragmentu je rozšířena kolem řádku:

```cpp
if (true)
{
    return FALSE;
}
```

## <a name="snippet-replacement-parameters"></a>Fragment kódu nahrazující parametry

Fragmenty kódu může obsahovat nahrazující parametry, které jsou zástupné symboly, které je třeba nahradit podle přesné kód, který vytváříte. V předchozím příkladu `true` je parametr nahrazení, který by nahraďte vhodné podmínky. Nahrazení, které se opakuje pro každou instanci parametr nahrazení v tomto fragmentu kódu.

Například v jazyce Visual Basic není fragment kódu, která vloží vlastnost. Klikněte na tlačítko **Vložit fragment** v místní nabídce okně kódu, pak **kódu, které vypadají**, pak **vlastnosti, postupy, události**, pak zadejte vlastnosti. Následující kód je vložen:

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

## <a name="code-snippet-manager"></a>Správce fragmentů kódu

Zobrazí se všechny fragmenty kódu, které jsou aktuálně nainstalovány a jejich umístění na disku, výběrem **nástroje**, **Správce fragmentů kódu**. Fragmenty kódu jsou zobrazeny podle jazyka.

Můžete přidávat a odebírat fragment kódu adresářů pomocí **přidat** a **odebrat** tlačítka v **Správce fragmentů kódu** dialogové okno. Chcete-li přidat jednotlivé fragmenty kódu, použijte **Import** tlačítko.

## <a name="see-also"></a>Viz také

[Návod: Vytvoření fragmentu kódu](../ide/walkthrough-creating-a-code-snippet.md)  
[Postupy: Distribuce fragmentů kódu](../ide/how-to-distribute-code-snippets.md)  
[Doporučené postupy pro používání fragmentů kódu](../ide/best-practices-for-using-code-snippets.md)  
[Řešení potíží s fragmenty kódu](../ide/troubleshooting-snippets.md)  
[Fragmenty kódu v jazyce Visual C#](../ide/visual-csharp-code-snippets.md)  
[Fragmenty kódu v jazyce Visual C#](../ide/visual-cpp-code-snippets.md)  
[Fragmenty kódu – odkaz schématu](../ide/code-snippets-schema-reference.md)