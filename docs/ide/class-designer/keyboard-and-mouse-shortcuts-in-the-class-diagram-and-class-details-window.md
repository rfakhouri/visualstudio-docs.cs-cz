---
title: Klávesové zkratky a zkratky myši v diagramu tříd a okně podrobností třídy (návrhář tříd)
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- vs.classdetails.window
helpviewer_keywords:
- class diagrams, keyboard shortcuts
- class diagrams, mouse shortcuts
ms.assetid: c12d8dac-9902-4fde-b721-2a8116da53b7
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0762287c47494b0dd0d3f4d444d7143c8688ec2b
ms.sourcegitcommit: 56018fb1f52f17bf35ae2ce71c50c763486e6173
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/04/2018
---
# <a name="keyboard-and-mouse-shortcuts-in-the-class-diagram-and-class-details-window-class-designer"></a>Klávesnice a myši zkratky v okně diagramu tříd a podrobností třídy (návrhář tříd)

Klávesnice kromě myši můžete provést navigační akce v **návrhář tříd** a v **podrobností třídy** okno.

## <a name="use-the-mouse-in-class-designer"></a>Pomocí myši v Návrháři tříd

Podporovány jsou následující akce myši v diagramech tříd:

|Kombinace myši|Kontext|Popis|
|-----------------------|-------------|-----------------|
|Dvakrát klikněte na|elementy obrazců|Otevře se editor kódu.|
|Dvakrát klikněte na|Konektor typu Lupa|Rozbalit nebo sbalit typu Lupa.|
|Dvakrát klikněte na|Popisek konektor typu Lupa|Vyvolá **zobrazit rozhraní** příkaz.|
|Kolečka myši|Diagram – třída|Posuňte se svisle.|
|SHIFT + kolečka myši|Diagram – třída|Posuňte se vodorovně.|
|CTRL + kolečka myši|Diagram – třída|Přiblížení.|
|CTRL + Shift + klikněte na|Diagram – třída|Přiblížení.|

## <a name="use-the-mouse-in-the-class-details-window"></a>Pomocí myši v okně podrobností třídy

Používáním myši, můžete změnit vzhled **podrobností třídy** okno a data zobrazuje následujícími způsoby:

-   Kliknutím na libovolnou buňku upravovat umožňuje upravit obsah této buňky. Vaše změny se projeví na všech místech data jsou uložena nebo zobrazit, včetně v okně vlastností a ve zdrojovém kódu.

-   Kliknutím na libovolnou buňku řádku způsobí, že okně Vlastnosti pro zobrazení vlastností pro element reprezentována příslušném řádku.

-   Chcete-li změnit šířku sloupce, přetáhněte hranice na pravé straně záhlaví sloupce, dokud sloupec je požadovanou šířku.

-   Můžete rozbalit nebo sbalit prostředí nebo vlastnost uzlů kliknutím symboly šipku nalevo od řádek.

-   Okno podrobností třídy nabízí několik tlačítka pro vytvoření nové členy v aktuální třídě a pro procházení mezi prostorů členy v okně podrobností třídy mřížky. Další informace najdete v tématu tlačítka okno podrobností třídy.

## <a name="use-the-keyboard-in-class-designer"></a>Použití klávesnice v Návrháři tříd

Podporovány jsou následující akce klávesnice v diagramech tříd:

|Key|Kontext|Popis|
|---------|-------------|-----------------|
|Klávesy se šipkami|Obrazce typu uvnitř|Navigační stromu stylu na obsah tvar (podporuje se zabalení kolem obrazce). Levý a pravý klíče rozbalit nebo sbalit aktuální položkou. Pokud je rozšíření a přejděte do nadřazené, pokud není (viz zobrazení stromu navigační podrobné chování).|
|Klávesy se šipkami|Nejvyšší úrovně tvarů|Přesunutí obrazce v diagramu.|
|SHIFT + ŠIPKA klíče|Obrazce typu uvnitř|Výběr průběžné vytváření skládající se z elementy obrazce například členové, vnořené typy nebo přihrádky. Tyto zástupce zabalení kolem nepodporují.|
|DOMOVSKÉ|Obrazce typu uvnitř|Přejděte na název obrazec nejvyšší úrovně.|
|DOMOVSKÉ|Nejvyšší úrovně tvarů|Přejděte do první z nich v diagramu.|
|END|Obrazce typu uvnitř|Přejděte na posledním elementem viditelné do vnitřní oblasti tvaru.|
|END|Nejvyšší úrovně tvarů|Přejděte k poslednímu obrazce v diagramu.|
|SHIFT + HOME|Obrazec uvnitř typu|Vybere elementů v rámci tvaru s aktuální položkou počáteční a koncovou s položkou nejvyšší na stejném tvaru.|
|SHIFT + END|Obrazec uvnitř typu|Stejné jako SHIFT + HOME, ale ve směru osy shora dolů.|
|ZADEJTE|Všechny kontexty|Vyvolá výchozí akci na tvar, který je taky dostupné prostřednictvím poklikejte na soubor. Ve většině případů to je kód zobrazení, ale některé prvky definovat jinak (cukroví, prostoru pro hlavičky, popisky typu Lupa).|
|+/-|Všechny kontexty|Pokud aktuálně nastavený fokus element rozšíření, tyto klíče rozbalit nebo sbalit obsah elementu.|
|>|Všechny kontexty|U elementů s podřízenými položkami rozšíří elementu, pokud je a přejde na prvním podřízeným objektem.|
|<|Všechny kontexty|Přejde na nadřazený element.|
|ALT + SHIFT + L|Uvnitř obrazce typu + na obrazce typu.|Přejde na aktuálně vybrané obrazce typu Lupa, pokud je k dispozici.|
|ALT + SHIFT + B|Uvnitř obrazce typu + na obrazce typu.|Pokud základní typ seznamu se zobrazí na obrazce typu a má více než jednu položku, to přepne stav rozšíření seznamu (nebo sbalení).|
|DELETE|Na typ a nastavte komentář u tvarů|Vyvolá **odebrání Diagram** příkaz.|
|DELETE|Na nic jiného.|Vyvolá **odstranit z kódu** příkazu (členy, parametry, přidružení, dědičnosti, popisky typu Lupa).|
|CTRL + DELETE|Všechny kontexty|Vyvolá **odstranit z kódu** na výběr.|
|KARTA|Všechny kontexty|Přejde na další podřízené v rámci stejné nadřazené položky (podporuje zabalení).|
|SHIFT + TAB|Všechny kontexty|Přejde na předchozí podřízenou v rámci stejné nadřazené položky (podporuje zabalení).|
|MÍSTO|Všechny kontexty|Přepne výběr u aktuálního elementu.|

## <a name="use-the-keyboard-in-the-class-details-window"></a>Použití klávesnice v okně podrobností třídy

> [!NOTE]
> Následující vazeb klíče byly vybrali možnost konkrétně tak, aby napodoboval možností psát kód.

Pomocí těchto klíčů můžete přejít **podrobností třídy** okno:

|||
|-|-|
|Key|Výsledek|
|, (čárkou)|Pokud kurzor se nachází v parametru řádek, zadejte do čárkami přesune kurzor do pole Název parametru Další. Pokud je kurzor na posledním řádku parametru metody, přesune ho ukazatele \<přidat parametr > pole, které můžete použít k vytvoření nového parametru.<br /><br /> Pokud kurzor se nachází jinde v **podrobností třídy** okně zadáním čárkou oznámena přidá čárkami v aktuální oblasti.|
|; (středníkem)<br /><br /> or<br /><br /> ) (Zavřít závorky)|Přesuňte se ukazatelem do pole název další člen řádku v **podrobností třídy** okno mřížky.|
|Tabulátor|Posune kurzor na další pole, nejprve přesouvání zleva doprava a pak shora dolů. Pokud kurzor přechází z pole, ve které jste zadali text, **podrobností třídy** zpracovává tento text a uloží ji, pokud nevytváří k chybě.<br /><br /> Pokud se nachází kurzor na prázdné pole, jako \<přidat parametr >, karta, přesune ho do prvního pole na další řádek.|
|\<místo >|Posune kurzor na další pole, nejprve přesouvání zleva doprava a pak shora dolů. Pokud se nachází kurzor na prázdné pole, jako \<přidat parametr >, přesune ho do prvního pole na další řádek. Všimněte si, že \<místo > zadali ihned po čárkou se ignoruje.<br /><br /> Pokud je kurzor do pole Summary, zadáním mezeru přidá znak mezery.<br /><br /> Pokud kurzor se nachází v skrýt sloupce daného řádku, zadejte místo přepne hodnota políčka Skrýt.|
|CTRL + Tab|Umožňuje přepnout do jiného okna dokumentu. Například přepínač z **podrobností třídy** okno na soubor otevřete kód.|
|ESC (řídicí)|Pokud jste začali zadávat text v poli, stisknutím klávesy ESC funguje jako klíč vrácení zpět, vrácení v polích na původní hodnotu. Pokud má právě fokus Obecné, okno podrobností třídy, ale žádné konkrétní buňky má právě fokus, stisknutím klávesy ESC přesouvá fokus směrem od **podrobností třídy** okno.|
|Šipka nahoru a Šipka dolů|Tyto klíče přesuňte se ukazatelem z řádků v svisle **podrobností třídy** okno mřížky.|
|Šipka doleva|Pokud je kurzor ve sloupci Název, kliknutím na šipku vlevo sbalí aktuálního uzlu v hierarchii (je-li otevřít).|
|Šipka doprava|Pokud je kurzor ve sloupci Název, kliknutím na šipku vpravo rozšíří aktuálního uzlu v hierarchii (je-li sbalený).|

## <a name="see-also"></a>Viz také

- [Vytváření a konfigurace členů typů](creating-and-configuring-type-members.md)