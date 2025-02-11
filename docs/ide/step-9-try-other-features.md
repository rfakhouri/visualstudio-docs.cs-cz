---
title: 'Krok 9: Vyzkoušení dalších funkcí'
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 1b0c5c80-e5a6-4f69-a4a4-0e89a82d4de0
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 24637ba56c3dfa2d9ce9c7e70452bcdc6788b51b
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/09/2019
ms.locfileid: "68918718"
---
# <a name="step-9-try-other-features"></a>Krok 9: Vyzkoušení dalších funkcí
Chcete-li získat další informace, zkuste změnit ikony a barvy, přidat časovač hry a zvuky. Chcete-li, aby hra byla náročnější, zkuste zvětšit hrací plochu a upravte časovač.

Pokud si chcete stáhnout dokončenou verzi ukázky, přečtěte si [ukázku s kurzem kompletní porovnávací hru](https://code.msdn.microsoft.com/Complete-Matching-Game-4cffddba).

## <a name="to-try-other-features"></a>Vyzkoušení dalších funkcí

- Nahraďte ikony a barvy těmi, které zvolíte.

    > [!TIP]
    > Zkuste se podívat na vlastnost [ForeColor](<xref:System.Windows.Forms.Control.ForeColor%2A>) popisku.

- Přidejte časovač hry, který sleduje, jak dlouho hráči trvá, než vyhraje.

    > [!TIP]
    > K tomu můžete přidat popisek pro zobrazení uplynulého času ve formuláři nad <xref:System.Windows.Forms.TableLayoutPanel>a přidat další časovač pro sledování času. Použijte kód ke spuštění časovače, když hráč zahájí hru, a zastavení časovače, jakmile hráč spojí poslední dvě ikony.

- Pokud hráč najde shodu, přidejte zvuk, jiný zvuk, když hráč odkryje dvě ikony, které neodpovídají, a třetí zvuk, když program znovu skryje ikony.

    > [!TIP]
    > Chcete-li přehrát zvuky, můžete použít <xref:System.Media> obor názvů. Další informace najdete v tématu [přehráníC#zvuku v aplikaci model Windows Forms App ()](http://youtu.be/qOh4ooHg1UU) nebo [o tom, jak přehrát zvuk v Visual Basic](http://youtu.be/-4oPDeQrtMs) .

- Udělejte hru obtížnější tím, že zvětšíte hrací plochu.

    > [!TIP]
    > Budete muset udělat více než jenom přidat řádky a sloupce do kontejneru TableLayoutPanel – budete taky muset vzít v úvahu počet ikon, které vytvoříte.

- Udělejte hru náročnější tím, že skryjete první ikonu, pokud je hráč příliš pomalý a nezvolí druhou ikonu do vypršení určitého časového limitu.

## <a name="to-continue-or-review"></a>Chcete-li pokračovat nebo přezkoumat

- Pokud si nevíte rady nebo máte otázky k programování, můžete zveřejnit svůj dotaz na jednom z diskuzních fór MSDN. Viz [Visual Basic Fórum](https://social.msdn.microsoft.com/Forums/vstudio/home?forum=vbgeneral) a [vizuální C# Fórum](https://social.msdn.microsoft.com/Forums/vstudio/home?forum=csharpgeneral).

- K dispozici jsou užitečné bezplatné video výukové materiály. Další informace o programování v Visual Basic najdete v tématu [Visual Basic základy: Vývoj pro absolutní začátečníky](https://channel9.msdn.com/Series/Visual-Basic-Development-for-Absolute-Beginners). Další informace o programování v vizuálů C#najdete v tématu [ C# základy: Vývoj pro absolutní začátečníky](https://channel9.msdn.com/Series/C-Sharp-Fundamentals-Development-for-Absolute-Beginners).

- Pokud se chcete vrátit k předchozímu kroku kurzu [, přečtěte si krok 8: Přidejte metodu k ověření, zda hráč zvítězil](../ide/step-8-add-a-method-to-verify-whether-the-player-won.md).
