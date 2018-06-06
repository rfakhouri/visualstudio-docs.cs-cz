---
title: 'Krok 3: Nastavte vlastnosti svého formuláře'
ms.custom: ''
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-acquisition
ms.topic: conceptual
ms.assetid: 634ef037-1525-48c8-ac7f-abf04be69376
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0d4bf7645f3143aa9c8b7b73361f2ba454dbb323
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/04/2018
ms.locfileid: "34748501"
---
# <a name="step-3-set-your-form-properties"></a>Krok 3: Nastavte vlastnosti svého formuláře
V dalším kroku použijete **vlastnosti** okno Změnit způsob vzhled formuláře.

 ![odkaz na video](../data-tools/media/playvideo.gif)video verzi tohoto tématu naleznete v části [kurzu 1: vytvoření prohlížeče obrázků v jazyce Visual Basic – Video 1](http://go.microsoft.com/fwlink/?LinkId=205209) nebo [kurzu 1: vytvoření prohlížeče obrázků v jazyce C# - Video 1](http://go.microsoft.com/fwlink/?LinkId=205199). Tyto videa pomocí starší verze sady Visual Studio, takže drobné rozdíly v některé příkazy a další prvky uživatelského rozhraní. Však koncepty a postupy fungují podobně jako v aktuální verzi sady Visual Studio.

## <a name="to-set-your-form-properties"></a>Chcete-li nastavit vlastnosti svého formuláře

1.  Ujistěte se, zvažujete **Návrhář formulářů Windows**. V sadě Visual Studio integrované vývojové prostředí (IDE), vyberte **Form1.cs [Design]** karta (nebo **Form1.vb [Design]** karta v jazyce Visual Basic).

2.  Zvolte kamkoli do formuláře **Form1** ji vyberte. Podívejte se na **vlastnosti** okno, které by měl být nyní zobrazuje vlastnosti pro daný formulář. Formuláře mají různé vlastnosti. Například můžete nastavit popředí a barvu pozadí, nadpisu, který se zobrazí v horní části formuláře, velikost formuláře a další vlastnosti.

    > [!NOTE]
    >  Pokud **vlastnosti** okno se nezobrazí, ukončete program výběrem druhou mocninu **Zastavte ladění** tlačítka na panelu nástrojů nebo pouze zavřete okno. Pokud program se zastaví a stále nevidíte **vlastnosti** okně na řádku nabídek zvolte **zobrazení** > **vlastnosti – okno**.

3.  Po výběru formuláře se najít **Text** vlastnost **vlastnosti** okno. V závislosti na tom, jak tento seznam je řazen možná budete muset posuňte se dolů. Zvolte **Text**, typ **Prohlížeč obrázků**a potom zvolte **Enter**.  Formulář by měl mít nyní text **Prohlížeč obrázků** v jeho záhlaví a **vlastnosti** okno by měl vypadat podobně jako na následujícím obrázku.

     ![Vlastnosti – okno](../ide/media/express_edittextproperty.png)
**vlastnosti** okna

    > [!NOTE]
    >  Vlastnosti lze provést řazení podle **Categorized** nebo **podle abecedy** zobrazení. Můžete přepínat mezi těmito dvěma zobrazeními pomocí tlačítek na **vlastnosti** okno. V tomto kurzu je snazší najít vlastnosti prostřednictvím **podle abecedy** zobrazení.

4.  Přejděte zpět na **Návrhář formulářů Windows**. Zvolte popisovač pravém přetažení formuláře, který je bílý čtvereček v dolní části formuláře a zobrazí se následující.

     ![Přetáhněte popisovač](../ide/media/express_bottomrt_drag.png) popisovač přetažení

     Přetažením úchytu změnit velikost formuláře, takže je formulář širší a o něco vyšší.

5.  Podívejte se na **vlastnosti** okně a Všimněte si, že **velikost** došlo ke změně vlastností. **Velikost** změny vlastností pokaždé, když změníte velikost formuláře. Zkuste přetažením úchytu formuláře k jeho velikost na velikost formuláře přibližně **550, 350** (nemusí být přesné), která by měla fungovat i pro tento projekt. Jako alternativu, můžete zadat hodnoty přímo v **velikost** vlastnost a potom zvolte **Enter** klíč.

6.  Spusťte program znovu. Mějte na paměti, můžete použít některou z následujících metod ke spuštění programu.

    -   Vyberte **F5** klíč.

    -   Na řádku nabídek zvolte **ladění** > **spustit ladění**.

    -   Na panelu nástrojů vyberte **spustit ladění** tlačítko, které se zobrazí takto.

         ![Spuštění ladění tlačítka panelu nástrojů](../ide/media/express_icondebug.png)
**spustit ladění** tlačítka panelu nástrojů

     Stejně jako před rozhraní IDE vytvoří a spustí program a zobrazí se okno.

7.  Než přejdete k dalšímu kroku, zastavte program, protože rozhraní IDE neumožní změníte váš program je spuštěn. Pamatujte si, že se k ukončete program můžete použít některou z následujících metod.

    -   Na panelu nástrojů vyberte **Zastavte ladění** tlačítko.

    -   Na řádku nabídek zvolte **ladění** > **Zastavte ladění**.

    -   Vyberte **X** tlačítka na horním rohu **Form1** okno.

## <a name="to-continue-or-review"></a>Chcete-li pokračovat nebo přezkoumat

-   Chcete-li přejít k dalšímu kroku kurzu, přečtěte si téma [krok 4: Rozvrhněte svůj formulář pomocí ovládacího prvku TableLayoutPanel](../ide/step-4-lay-out-your-form-with-a-tablelayoutpanel-control.md).

-   Chcete-li vrátit k předchozímu kroku kurzu, přečtěte si téma [krok 2: Spusťte svůj program](../ide/step-2-run-your-program.md).
