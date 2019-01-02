---
title: 'Krok 6: Přidejte časovač'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: conceptual
ms.assetid: 09e7930b-cab6-4a22-9a6f-72e23f489585
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 36ca514f4bfb5b3c73d2f72b06afdab72a987ed0
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53885408"
---
# <a name="step-6-add-a-timer"></a>Krok 6: Přidejte časovač
V dalším kroku přidejte <xref:System.Windows.Forms.Timer> ovládacího prvku do porovnávací hry. Časovač čeká zadaný počet milisekund a potom vyvolá událost označovanou jako *značek*. To je užitečné při spuštění akce nebo opakování akce v pravidelných intervalech. V takovém případě můžete pomocí časovače povolit hráči zvolit dvě ikony a pokud se ikony neshodují, po krátké době tyto ikony opět skrýt.

## <a name="to-add-a-timer"></a>Přidání časovače

1.  Z panelu nástrojů v **Návrháře formulářů Windows**, zvolte **časovače** (v **součásti** kategorie) a klikněte na tlačítko **Enter** klíč, nebo dvakrát klikněte na časovač a přidejte ovládací prvek časovače do formuláře. Ikona časovače, volá **Timer1**, by se měla zobrazit v prostoru pod formulářem, jak je znázorněno na následujícím obrázku.

     ![Časovač](../ide/media/express_timer.png)
**časovače**

    > [!NOTE]
    >  Pokud je panel nástrojů prázdný, je nutné před otevřením sady nástrojů vybrat nástroj Návrhář a nikoli kód formuláře.

2.  Zvolte **Timer1** ikonu vyberte časovač. V **vlastnosti** okno, přepněte zobrazení z událostí na vlastnosti. Nastavte časovače **Interval** vlastnost **750**, ale ponechat jeho **povoleno** vlastnost nastavena na **False**. **Interval** vlastnost sděluje časovači, jak dlouho se má čekat mezi *značky*, nebo při aktivaci jeho <xref:System.Windows.Forms.Timer.Tick> událostí. Hodnota 750 říká časovači, aby před vyvoláním události impulzu čekal tři čtvrtiny sekundy (750 milisekund). Budete volat <xref:System.Windows.Forms.Timer.Start> metoda ke spuštění časovače, až poté, co hráč zvolí druhý popisek.

3.  Časovač zvolte ikonu ovládacího prvku v **Návrháře formulářů Windows** a klikněte na tlačítko **Enter** klíče nebo dvakrát klikněte na časovač, chcete-li přidat prázdný obslužná rutina události impulzu. Nahraďte kód následujícím kódem, nebo ručně zadejte následující kód do obslužné rutiny události.

     [!code-csharp[VbExpressTutorial4Step6#7](../ide/codesnippet/CSharp/step-6-add-a-timer_1.cs)]
     [!code-vb[VbExpressTutorial4Step6#7](../ide/codesnippet/VisualBasic/step-6-add-a-timer_1.vb)]

     Obslužná rutina události impulzu provádí tři věci: Nejprve zkontroluje, zda není spuštěn časovač, voláním <xref:System.Windows.Forms.Timer.Stop> metody. Potom použije dvě referenční proměnné `firstClicked` a `secondClicked`k nastavení ikon dvou popisků, které hráč zvolí znovu neviditelné. Nakonec resetuje `firstClicked` a `secondClicked` referenční proměnné k `null` v jazyce Visual C# a `Nothing` v jazyce Visual Basic. Tento krok je důležitý, protože ukazuje, jak se program sám resetuje. Teď ji není udržování přehledu o některý <xref:System.Windows.Forms.Label> ovládací prvky a je připravený k si hráč znovu zvolí popisek.

    > [!NOTE]
    >  Objekt časovače má `Start()` metodu, která spustí časovač, a `Stop()` metodu, která ho zastaví. Při nastavení časovače **povoleno** vlastnost **True** v **vlastnosti** okna, spustí tikání ihned po spuštění programu. Ale když necháte nastavené na **False**, nespustí tikání až do jeho `Start()` metoda je volána. Za normálních okolností časovač vyvolá událost impulzu znovu a znovu, pomocí **Interval** a určí počet milisekund k čekání mezi impulzy. Jste si všimli jak časovače `Stop()` metoda je volána uvnitř události impulzu. To vloží časovač do *jednorázovém režimu*, což znamená, že `Start()` metoda je volána, čeká na zadaný interval, spustí jednu událost impulzu a poté se zastaví.

4.  Chcete-li vidět nový časovač v akci, přejděte k editoru kódu a přidejte následující kód do horní a dolní část `label_Click()` metoda obslužné rutiny události. (Přidáte `if` příkaz do horní části a tři příkazy do dolní části; zbývající část metody zůstává stejná.)

     [!code-csharp[VbExpressTutorial4Step6#8](../ide/codesnippet/CSharp/step-6-add-a-timer_2.cs)]
     [!code-vb[VbExpressTutorial4Step6#8](../ide/codesnippet/VisualBasic/step-6-add-a-timer_2.vb)]

     Kód v horní části metody kontroluje, zda byl spuštěn časovač, kontrolou hodnoty **povoleno** vlastnost. Tímto způsobem, pokud hráč vybere první a druhý popisek ovládacích prvků a spustí se časovač, výběr třetího popisku nespustí žádnou akci.

     Kód v dolní části metody nastaví `secondClicked` referenční proměnnou můžete sledovat na druhý ovládací prvek popisku, hráč vybral, a pak nastaví barvu ikony tohoto popisku na černou, aby byla viditelná. Poté spustí časovač v jednorázovém režimu, takže čeká 750 milisekund a potom vyvolá jednu událost impulzu. Obslužné rutiny události cyklů časovače skryje dvě ikony a obnoví `firstClicked` a `secondClicked` referenční proměnné, takže je formulář připraven hráč vybere jinou dvojici ikon.

5.  Uložte program a spusťte jej. Vyberte ikonu, která se stane viditelnou.

6.  Vyberte jinou ikonu. Objeví se krátce a pak obě ikony zmizí. Tento postup několikrát zopakujte. Formulář nyní sleduje první a druhou ikonu, které jste vybrali, a používá časovač k pozastavení před skrytím ikon.

## <a name="to-continue-or-review"></a>Chcete-li pokračovat nebo přezkoumat

-   Přechod k dalšímu kroku výukového programu naleznete v tématu [krok 7: Zachování dvojic viditelných](../ide/step-7-keep-pairs-visible.md).

-   Chcete-li vrátit k předchozímu kroku tutoriálu, přečtěte si téma [krok 5: Přidejte odkazy na jmenovky](../ide/step-5-add-label-references.md).
