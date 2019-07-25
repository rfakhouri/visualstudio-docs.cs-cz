---
title: 'Krok 10: Napsání kódu pro přídavná tlačítka a zaškrtávací políčko'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- csharp
- vb
ms.assetid: 185cf370-ab39-4ac0-b6bc-601d5b95a4a2
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 10d1dcd4cb4a4dfca76d8af3fe6690076d91c72c
ms.sourcegitcommit: 59e5758036223ee866f3de5e3c0ab2b6dbae97b6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/23/2019
ms.locfileid: "68416682"
---
# <a name="step-10-write-code-for-additional-buttons-and-a-check-box"></a>Krok 10: Napsání kódu pro přídavná tlačítka a zaškrtávací políčko
Nyní jste připraveni provést další čtyři metody. Tento kód můžete zkopírovat a vložit, ale pokud se chcete dozvědět nejvíc od tohoto kurzu, zadejte kód a použijte technologii IntelliSense.

 Tento kód přidá funkce do tlačítek, které jste přidali dříve. Bez tohoto kódu nejsou tlačítka dělat nic. Tlačítka používají kód ve svých <xref:System.Windows.Forms.Control.Click> událostech (a zaškrtávací políčko <xref:System.Windows.Forms.CheckBox.CheckedChanged> používá událost) k provedení různých akcí při aktivaci ovládacích prvků. Například `clearButton_Click` událost, která se aktivuje po kliknutí na tlačítko **Vymazat obrázek** , vymaže aktuální obrázek nastavením jeho vlastnosti **Image** na **hodnotu null** (nebo, **Nothing**). Každá událost v kódu obsahuje komentáře, které vysvětlují, co kód dělá.

 ![odkaz na video](../data-tools/media/playvideo.gif)ve verzi videa tohoto tématu najdete v [kurzu 1: Vytvoření prohlížeče obrázků v Visual Basic-video 5](http://go.microsoft.com/fwlink/?LinkId=205216) nebo [kurz 1: Vytvoření prohlížeče obrázků ve C# videu 5.](http://go.microsoft.com/fwlink/?LinkId=205206) Tato videa používají starší verzi sady Visual Studio, takže existují mírné rozdíly v některých příkazech nabídky a dalších prvcích uživatelského rozhraní. Koncepty a postupy však fungují podobně v aktuální verzi sady Visual Studio.

> [!NOTE]
> Osvědčeným postupem: Vždy přikomentujte kód. Komentáře jsou informace, které uživatel přečte, a je to čas, kdy se váš kód může pochopit. Vše na řádku komentáře program ignoruje. V jazyce C#Visual se zadáním dvou dvojitých lomítek na začátku (//) zobrazí komentář k řádku a v Visual Basic zadáte komentář řádku, který začíná jednoduchou uvozovkou (').

## <a name="to-write-code-for-additional-buttons-and-a-check-box"></a>Psaní kódu pro další tlačítka a zaškrtávací políčko

- Přidejte následující kód do souboru kódu **Form1** (*Form1.cs* nebo *Form1. vb*). Vyberte kartu **VB** pro zobrazení kódu Visual Basic.

     [!code-vb[VbExpressTutorial1Step9_10#2](../ide/codesnippet/VisualBasic/step-10-write-code-for-additional-buttons-and-a-check-box_1.vb)]
     [!code-csharp[VbExpressTutorial1Step9_10#2](../ide/codesnippet/CSharp/step-10-write-code-for-additional-buttons-and-a-check-box_1.cs)]

## <a name="to-continue-or-review"></a>Chcete-li pokračovat nebo přezkoumat

- Pokud chcete přejít na další krok kurzu, přečtěte si [krok 11: Spusťte program a vyzkoušejte další funkce](../ide/step-11-run-your-program-and-try-other-features.md).

- Pokud se chcete vrátit k předchozímu kroku kurzu [, přečtěte si krok 9: Přečtěte si, pokomentujte a](../ide/step-9-review-comment-and-test-your-code.md)otestujte svůj kód.
