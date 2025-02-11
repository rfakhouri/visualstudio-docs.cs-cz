---
title: 'Krok 10: Napsání kódu pro přídavná tlačítka a zaškrtávací políčko'
ms.date: 08/30/2019
ms.assetid: 185cf370-ab39-4ac0-b6bc-601d5b95a4a2
ms.topic: tutorial
ms.prod: visual-studio-windows
ms.technology: vs-ide-general
ms.devlang:
- csharp
- vb
dev_langs:
- csharp
- vb
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 281c98ca52b6dd18ee726e3191d47d6755fd8326
ms.sourcegitcommit: 9c07ae6fb18204ea080c8248994a683fa12e5c82
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/04/2019
ms.locfileid: "70293620"
---
# <a name="step-10-write-code-for-additional-buttons-and-a-check-box"></a>Krok 10: Napsání kódu pro přídavná tlačítka a zaškrtávací políčko

Nyní jste připraveni provést další čtyři metody. Tento kód můžete zkopírovat a vložit, ale pokud se chcete dozvědět nejvíc od tohoto kurzu, zadejte kód a použijte technologii IntelliSense.

Tento kód přidá funkce do tlačítek, které jste přidali dříve. Bez tohoto kódu nejsou tlačítka dělat nic. Tlačítka používají kód ve svých <xref:System.Windows.Forms.Control.Click> událostech (a zaškrtávací políčko <xref:System.Windows.Forms.CheckBox.CheckedChanged> používá událost) k provedení různých akcí při aktivaci ovládacích prvků. Například `clearButton_Click` událost (nebo `ClearButton_Click`), která se aktivuje po kliknutí na tlačítko **Vymazat obrázek** , vymaže aktuální obrázek nastavením jeho vlastnosti **Image** na **hodnotu null** (nebo, **Nothing**). Každá událost v kódu obsahuje komentáře, které vysvětlují, co kód dělá.

> [!TIP]
> Osvědčeným postupem: Vždy přikomentujte kód. Komentáře jsou informace, které uživatel přečte, a je to čas, kdy se váš kód může pochopit. Vše na řádku komentáře program ignoruje. V C#aplikaci můžete zadat komentář k řádku zadáním dvou lomítka na začátku (//) a v Visual Basic přidáte komentář k řádku, který začíná jednoduchou uvozovkou (').

## <a name="how-to-write-code-for-additional-buttons-and-a-check-box"></a>Postup psaní kódu pro další tlačítka a zaškrtávací políčko

Přidejte následující kód do souboru kódu **Form1** (*Form1.cs* nebo *Form1. vb*).
> [!IMPORTANT]
> Pomocí ovládacího prvku programovací jazyk v pravém horním rohu této stránky můžete zobrazit fragment C# kódu nebo Visual Basic fragment kódu.<br><br>![Řízení programovacího jazyka pro Docs.Microsoft.com](../ide/media/docs-programming-language-control.png)

  [!code-csharp[VbExpressTutorial1Step9_10#2](../ide/codesnippet/CSharp/step-10-write-code-for-additional-buttons-and-a-check-box_1.cs)]

  [!code-vb[VbExpressTutorial1Step9_10#2](../ide/codesnippet/VisualBasic/step-10-write-code-for-additional-buttons-and-a-check-box_1.vb)]

## <a name="next-steps"></a>Další kroky

* Pokud chcete přejít na další krok kurzu, přečtěte si [krok 11: Spusťte program a vyzkoušejte další funkce](../ide/step-11-run-your-program-and-try-other-features.md).

* Pokud se chcete vrátit k předchozímu kroku kurzu [, přečtěte si krok 9: Přečtěte si, pokomentujte a](../ide/step-9-review-comment-and-test-your-code.md)otestujte svůj kód.

## <a name="see-also"></a>Viz také:

* [Kurz 2: Vytvoření časovaného matematického kvízu](tutorial-2-create-a-timed-math-quiz.md)
* [Kurz 3: Vytvořit porovnávací hru](tutorial-3-create-a-matching-game.md)
