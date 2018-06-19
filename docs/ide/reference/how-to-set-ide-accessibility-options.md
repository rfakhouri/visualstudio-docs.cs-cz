---
title: 'Postupy: nastavení možnosti usnadnění přístupu IDE'
description: Zjistěte, jak nastavit možnosti usnadnění v sadě Visual Studio, která vám usnadní jeho integrované vývojové prostředí (IDE) pro každodenní použití, včetně pro osoby, slabým zrakem ke čtení a pro uživatele, kteří mají omezenou pohyblivostí k zápisu.
ms.date: 08/22/2017
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- accessibility [Visual Studio]
ms.assetid: ddc96c4c-0600-46c1-8267-7dce4c44ad24
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f977c30f1f4d6db7ce165de8483c8fd1977922d8
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31952100"
---
# <a name="how-to-set-ide-accessibility-options"></a>Postupy: nastavení možnosti usnadnění přístupu IDE

> [!TIP]
> Další informace o nejnovějších aktualizacích usnadnění přístupu najdete v tématu [vylepšení přístupnosti v Visual Studio 2017 verze 15.3](https://blogs.msdn.microsoft.com/visualstudio/2017/08/14/accessibility-improvements-in-visual-studio-2017-version-15-3/) příspěvku na blogu.

[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] obsahuje funkce, které bylo snazší pro osoby, slabým zrakem ke čtení a pro uživatele, kteří mají omezenou pohyblivostí k zápisu. Tyto funkce patří změna velikosti a barvy textu v editory Změna velikosti textu a tlačítka na panely nástrojů a automatické dokončování metod a parametrů, a další.

 Kromě toho [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] podporuje rozložení programátorského rozložení klávesnice, což usnadňuje nejčastěji psaným znakům. Můžete také upravit výchozí klávesové zkratky, který je k dispozici [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]. Další informace najdete v tématu [identifikuje a přizpůsobení klávesových zkratek](../../ide/identifying-and-customizing-keyboard-shortcuts-in-visual-studio.md).

> [!NOTE]
> Dialogová okna a příkazy nabídek, které vidíte, se mohou lišit od těch popsaných v nápovědě v závislosti na aktivních nastaveních nebo edici. Chcete-li změnit nastavení, zvolte **nastavení importu a exportu** na **nástroje** nabídky. Další informace najdete v tématu [přizpůsobení prostředí Visual Studio IDE](../../ide/personalizing-the-visual-studio-ide.md).

## <a name="editors-dialogs-and-tool-windows"></a>Editory, dialogová okna a nástroje systému windows

 Ve výchozím nastavení, dialogová okna a nástroj windows v [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] použít stejnou velikost písma a barvy jako operační systém. Nastavení Barva rámečku IDE, dialogová okna, panely nástrojů a nástroje systému windows jsou založené barevném schématu: světlý nebo tmavý. Můžete změnit na aktuální barevný motiv v [Obecné, prostředí, dialogové okno Možnosti](../../ide/reference/general-environment-options-dialog-box.md).

 Automaticky otevíraná okna můžete také zobrazit v zobrazení kódu v editoru. Tyto windows můžete vyzvat vás k dispozici členy na aktuální objekt a parametry k dokončení funkce nebo příkaz. Tyto windows může být užitečné, pokud máte potíže s psaním. Však budou narušovat fokusu v editoru kódu, což může být problematické pro některé uživatele. Tyto windows můžete vypnout otevřením dialogového okna Možnosti a vymazání **automatický seznam členů** a **informace o parametrech** v **textového editoru**, **všechny Jazyky**, **Obecné** stránku **možnosti** dialogové okno.

 Můžete přeuspořádat windows v integrované vývojové prostředí (IDE) nejlépe vyhovovat způsobu práce. Můžete ukotvení, float, skrýt nebo automaticky skrýt každý okno nástroje.

 Další informace o tom, jak změnit rozložení oken najdete v tématu [přizpůsobení rozložení oken](../../ide/customizing-window-layouts-in-visual-studio.md).

### <a name="changing-the-size-of-text"></a>Změna velikosti textu

 Můžete změnit nastavení pro nástroj založený na textu, například **příkaz** okně **Immediate** okně a **výstup** okno v **písem a Barvy** podokně **prostředí** možnosti v **nástroje** dialogové okno. Když **[všechna okna textových nástrojů]** je vybraný v **zobrazit nastavení pro** rozevíracího seznamu ve výchozím nastavení je uveden jako **výchozí** v **popředí položky**  a **položky pozadí** rozevírací seznamy. Můžete také změnit nastavení pro zobrazení textu v editoru.

##### <a name="to-change-the-size-of-text-in-text-based-tool-windows-and-editors"></a>Chcete-li změnit velikost textu v systému windows nástroj založený na textu a editory

1.  Z **nástroje** nabídce zvolte **možnosti**.

2.  Zvolte **písma a barev** na **prostředí** složky.

3.  Vyberte možnost na **zobrazit nastavení pro** rozevírací nabídce.

     Chcete-li změnit velikost písma pro text v editoru, zvolte **textového editoru**.

     Chcete-li změnit velikost písma pro text v systému windows nástroj založený na textu, zvolte **[všechna okna textových nástrojů]**.

     Chcete-li změnit velikost písma pro text popisu tlačítka v editoru, zvolte **popisu tlačítka editoru**.

     Chcete-li změnit velikost písma pro text v příkazu dokončení automaticky otevíraná okna, zvolte **dokončování**.

4.  Z **zobrazení položek**, vyberte **prostý Text**.

5.  V **písma**, vyberte nový typ písma.

6.  V **velikost**, vyberte novou velikost písma.

    > [!NOTE]
    >  Chcete-li resetovat velikost textu pro založený na textu panely nástrojů, zvolte **použít výchozí hodnoty**.

7.  Zvolte **OK**.

### <a name="change-the-colors-that-are-used-in-the-ide"></a>Změna barev, které se používají v prostředí IDE

 Můžete také změnit výchozí barvy pro text, indikátory okrajů, mezer a elementy kódu v editoru.

> [!NOTE]
> Pokud chcete použít pro všechny aplikace systému windows v operačním systému vysoký kontrast barvy, stiskněte vlevo **ALT +** doleva **SHIFT + PRINT SCREEN**. Pokud [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] je otevřít, zavřete a znovu otevřete [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] plně implementovat barvy s vysokým kontrastem.


##### <a name="to-change-the-color-of-items-in-the-editor"></a>Chcete-li změnit barvy položek v editoru

1.  Z **nástroje** nabídce zvolte **možnosti**.

2.  V **prostředí** složky, vyberte **písma a barev**.

3.  V **zobrazit nastavení pro**, zvolte **textového editoru**.

4.  Z **zobrazení položek**, vyberte položku, jejichž zobrazení je třeba změnit, jako například **prostý Text**, **okraj indikátoru**, **viditelné mezer**, **Název atributu HTML**, nebo **atribut XML**.

5.  Vyberte zobrazení nastavení z následujících možností: **popředí položky**, **položky pozadí**, a **Bold**.

6.  Zvolte **OK**.

## <a name="toolbars"></a>Panely nástrojů

 Pokud chcete zlepšit použitelnost panelu nástrojů a usnadnění, můžete přidat text k tlačítkům panelu nástrojů.

#### <a name="to-assign-text-to-toolbar-buttons"></a>Chcete-li přiřadit text tlačítka panelu nástrojů

1.  Z **nástroje** nabídce zvolte **přizpůsobit**.

2.  V **přizpůsobit** dialogové okno, vyberte **příkazy** kartě.

3.  Vyberte **nástrojů** a pak klikněte na panelu nástrojů název, který obsahuje tlačítko, které chcete zobrazit text pro.

4.  V seznamu vyberte příkaz, který chcete změnit.

5.  Zvolte **změnit výběr**.

6.  Zvolte **bitové kopie a Text**.

#### <a name="to-modify-the-displayed-text-in-a-button"></a>K úpravě zobrazovaného textu v tlačítka

1.  Znovu vyberte **změnit výběr**.

2.  V blízkosti **název**, insert zadejte nový titulek pro vybrané tlačítko.

## <a name="see-also"></a>Viz také

* [Funkce pro usnadnění přístupu sady Visual Studio](../../ide/reference/accessibility-features-of-visual-studio.md)
* [Prostředky pro navržení aplikací usnadňujících přístup](../../ide/reference/resources-for-designing-accessible-applications.md)
