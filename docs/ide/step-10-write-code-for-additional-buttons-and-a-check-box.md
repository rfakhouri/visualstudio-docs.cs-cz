---
title: 'Krok 10: Napište kód pro přídavná tlačítka a zaškrtávací políčko'
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 185cf370-ab39-4ac0-b6bc-601d5b95a4a2
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 889cf092ae77eae7ef190c48b2949ddca646dc2a
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60097294"
---
# <a name="step-10-write-code-for-additional-buttons-and-a-check-box"></a>Krok 10: Napište kód pro přídavná tlačítka a zaškrtávací políčko
Nyní jste připraveni provést další čtyři metody. Mohli byste zkopírovat a vložit tento kód, ale pokud chcete získat maximum z tohoto kurzu zadejte kód a používat technologii IntelliSense.

 Tento kód přidá funkce pro tlačítka, který jste přidali dříve. Bez tohoto kódu tlačítka nic nedělají. Tlačítka používají kód v jejich <xref:System.Windows.Forms.Control.Click> události (a zaškrtávací políčko používá <xref:System.Windows.Forms.CheckBox.CheckedChanged> událostí) k provádění různých akcí, když aktivujete ovládací prvky. Například `clearButton_Click` událost, která se aktivuje při výběru **Vymazat obrázek** tlačítko, vymaže aktuální obrázek nastavením jeho **Image** vlastnost **null**(nebo **nic**). Každá událost v kódu obsahuje poznámky, které popisují, co kód dělá.

 ![odkaz na video](../data-tools/media/playvideo.gif)video verzi tohoto tématu naleznete v tématu [kurz 1: Vytvoření prohlížeče obrázků v jazyce Visual Basic - Video 5](http://go.microsoft.com/fwlink/?LinkId=205216) nebo [kurz 1: Vytvoření prohlížeče obrázků v C# – Video 5](http://go.microsoft.com/fwlink/?LinkId=205206). Tato videa používají starší verzi sady Visual Studio, takže existují mírné rozdíly v některých příkazech nabídek a jiných prvcích uživatelského rozhraní. Nicméně koncepty a postupy fungují podobně jako v aktuální verzi sady Visual Studio.

> [!NOTE]
>  Jako osvědčený postup: Vždy komentujte svůj kód. Komentáře jsou informace pro osobu, která ke čtení a stojí za čas, aby byl srozumitelnější kód. Vše na řádku komentáře je programem ignorováno. V jazyce Visual C# komentujete řádek zadáním dvou lomítek na začátku (/ /), a v jazyce Visual Basic komentujete řádek začínající jednoduché uvozovky (').

## <a name="to-write-code-for-additional-buttons-and-a-check-box"></a>Napsat kód pro přídavná tlačítka a zaškrtávací políčko

- Přidejte následující kód, který vaše **Form1** souboru s kódem (*Form1.cs* nebo *Form1.vb*). Zvolte **VB** kartu k zobrazení kódu jazyka Visual Basic.

     [!code-vb[VbExpressTutorial1Step9_10#2](../ide/codesnippet/VisualBasic/step-10-write-code-for-additional-buttons-and-a-check-box_1.vb)]
     [!code-csharp[VbExpressTutorial1Step9_10#2](../ide/codesnippet/CSharp/step-10-write-code-for-additional-buttons-and-a-check-box_1.cs)]

## <a name="to-continue-or-review"></a>Chcete-li pokračovat nebo přezkoumat

- Přechod k dalšímu kroku výukového programu naleznete v tématu [krok 11: Spusťte program a vyzkoušejte další funkce](../ide/step-11-run-your-program-and-try-other-features.md).

- Chcete-li vrátit k předchozímu kroku tutoriálu, přečtěte si téma [krok 9: Zkontrolujte, komentáře a testují vytvořený kód](../ide/step-9-review-comment-and-test-your-code.md).
