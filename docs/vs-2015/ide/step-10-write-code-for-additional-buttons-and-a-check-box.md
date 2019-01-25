---
title: 'Krok 10: Napsat kód pro přídavná tlačítka a zaškrtávací políčko | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
ms.assetid: 185cf370-ab39-4ac0-b6bc-601d5b95a4a2
caps.latest.revision: 23
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 58e50e7d70c485a4a49564ec0a57ba03b74e4a85
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54786022"
---
# <a name="step-10-write-code-for-additional-buttons-and-a-check-box"></a>Krok 10: Napsání kódu pro přídavná tlačítka a zaškrtávací políčko
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nyní jste připraveni provést další čtyři metody. Mohli byste zkopírovat a vložit tento kód, ale pokud chcete získat maximum z tohoto kurzu zadejte kód a používat technologii IntelliSense.  
  
 Tento kód přidá funkce pro tlačítka, který jste přidali dříve. Bez tohoto kódu tlačítka nic nedělají. Tlačítka používají kód v jejich `Click` události (a zaškrtávací políčko používá `CheckChanged` událostí) k provádění různých akcí, když aktivujete ovládací prvky. Například `clearButton_Click` událost, která se aktivuje při výběru **Vymazat obrázek** tlačítko, vymaže aktuální obrázek nastavením jeho `Image` vlastnost `null` (nebo `nothing`). Každá událost v kódu obsahuje poznámky, které popisují, co kód dělá.  
  
 ![odkaz na video](../data-tools/media/playvideo.gif "PlayVideo")video verzi tohoto tématu naleznete v tématu [kurz 1: Vytvoření prohlížeče obrázků v jazyce Visual Basic - Video 5](http://go.microsoft.com/fwlink/?LinkId=205216) nebo [kurz 1: Vytvoření prohlížeče obrázků v C# – Video 5](http://go.microsoft.com/fwlink/?LinkId=205206). Tato videa používají starší verzi sady Visual Studio, takže existují mírné rozdíly v některých příkazech nabídek a jiných prvcích uživatelského rozhraní. Nicméně koncepty a postupy fungují podobně jako v aktuální verzi sady Visual Studio.  
  
> [!NOTE]
>  Jako osvědčený postup: Vždy komentujte svůj kód. Komentáře jsou informace pro osobu, která ke čtení a stojí za čas, aby byl srozumitelnější kód. Vše na řádku komentáře je programem ignorováno. V jazyce Visual C# komentujete řádek zadáním dvou lomítek na začátku (/ /), a v jazyce Visual Basic komentujete řádek začínající jednoduché uvozovky (').  
  
### <a name="to-write-code-for-additional-buttons-and-a-check-box"></a>Napsat kód pro přídavná tlačítka a zaškrtávací políčko  
  
-   Přidejte následující kód do souboru kódu Form1 (Form1.cs nebo Form1.vb). Zvolte **VB** kartu k zobrazení kódu jazyka Visual Basic.  
  
     [!code-csharp[VbExpressTutorial1Step9_10#2](../snippets/csharp/VS_Snippets_VBCSharp/vbexpresstutorial1step9_10/cs/form1.cs#2)]
     [!code-vb[VbExpressTutorial1Step9_10#2](../snippets/visualbasic/VS_Snippets_VBCSharp/vbexpresstutorial1step9_10/vb/form1.vb#2)]  
  
### <a name="to-continue-or-review"></a>Chcete-li pokračovat nebo přezkoumat  
  
-   Přechod k dalšímu kroku výukového programu naleznete v tématu [krok 11: Spusťte Program a vyzkoušejte další funkce](../ide/step-11-run-your-program-and-try-other-features.md).  
  
-   Chcete-li vrátit k předchozímu kroku tutoriálu, přečtěte si téma [krok 9: Zkontrolujte, komentáře a testují vytvořený kód](../ide/step-9-review-comment-and-test-your-code.md).
