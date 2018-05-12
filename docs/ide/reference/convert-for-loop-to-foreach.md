---
title: Refaktorovat kódu pro převod pro opakování ve smyčce bude foreach – příkaz
ms.date: 05/10/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: douge
dev_langs:
- CSharp
ms.workload:
- dotnet
ms.openlocfilehash: 34758473bcbee8ccad7d9dff9df2f1478ca1202c
ms.sourcegitcommit: 046a9adc5fa6d6d05157204f5fd1a291d89760b7
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/11/2018
---
# <a name="refactoring-to-convert-between-a-for-loop-and-a-foreach-statement"></a>Refaktoring pro převod mezi smyčky a ForEach – příkaz

Tyto refaktoring platí pro:

- C#

## <a name="convert-a-for-loop-to-a-foreach-statement"></a>Převést pro opakování ve smyčce bude foreach – příkaz

Pokud máte [pro](/dotnet/csharp/language-reference/keywords/for) smyčky v kódu, můžete tento refaktoring převeďte ho na [foreach](/dotnet/csharp/language-reference/keywords/foreach-in) příkaz.

### <a name="why-convert"></a>Proč převést

Důvodů, proč můžete chtít převést [pro](/dotnet/csharp/language-reference/keywords/for) cykly k [foreach](/dotnet/csharp/language-reference/keywords/foreach-in) příkaz patří:

- Počet proměnné iterace ve smyčce kromě nepoužívejte jako index pro přístup k položce.

- Chcete zjednoduší kódování a snížit pravděpodobnost chyb logiku v inicializátoru, podmínku a příkazy iterace.

### <a name="how-to-use-it"></a>Způsobu jeho použití

1. Umístěte kurzor na první řádek `for` smyčky.

1. Stiskněte klávesu **Ctrl**+**.** nebo klikněte na tlačítko šroubovák ![šroubovák ikonu](../media/screwdriver-icon.png) ikonu na okraji souboru kódu.

   ![Převést do nabídky foreach](media/convert-to-foreach.png)

1. Vyberte **převést na 'foreach'**. Nebo vyberte **zobrazení náhledu změn** otevřete [zobrazení náhledu změn](../../ide/preview-changes.md) dialogové okno a potom vyberte **použít**.

## <a name="convert-a-foreach-statement-to-a-for-loop"></a>Převést příkazu foreach k smyčky for

Pokud máte [foreach](/dotnet/csharp/language-reference/keywords/foreach-in) příkaz ve vašem kódu, můžete tento refaktoring převeďte ho na [pro](/dotnet/csharp/language-reference/keywords/for) smyčky.

### <a name="why-convert"></a>Proč převést

Důvodů, proč můžete chtít převést [foreach](/dotnet/csharp/language-reference/keywords/foreach-in) příkaz, který má [pro](/dotnet/csharp/language-reference/keywords/for) smyčky patří:

- Chcete použít počet proměnné iterace ve smyčce, pro víc věcí než jenom přístup k položce.

- Jste [iterace v rámci vícerozměrné](/dotnet/csharp/programming-guide/arrays/using-foreach-with-arrays) a chcete mít větší kontrolu nad prvků pole.

### <a name="how-to-use-it"></a>Způsobu jeho použití

1. Umístěte kurzor na první řádek `foreach` příkaz.

1. Stiskněte klávesu **Ctrl**+**.** nebo klikněte na tlačítko šroubovák ![šroubovák ikonu](../media/screwdriver-icon.png) ikonu na okraji souboru kódu.

   ![Převést na nabídky](media/convert-to-for.png)

1. Vyberte **převést na 'pro'**. Nebo vyberte **zobrazení náhledu změn** otevřete [zobrazení náhledu změn](../../ide/preview-changes.md) dialogové okno a potom vyberte **použít**.

1. Protože refaktoring zavádí nové proměnné počet iterací **přejmenovat** pole se zobrazí v pravém horním rohu editoru. Pokud chcete zvolit jiný název pro proměnnou, zadejte ho a stiskněte klávesu **Enter** nebo vyberte **použít** v **přejmenovat** pole. Pokud nechcete, aby vybrat nový název, stiskněte klávesu **Esc** nebo vyberte **použít** pro zavření **přejmenovat** pole.

## <a name="see-also"></a>Viz také

- [Refactoring](../refactoring-in-visual-studio.md)
- [Náhled změn](../../ide/preview-changes.md)