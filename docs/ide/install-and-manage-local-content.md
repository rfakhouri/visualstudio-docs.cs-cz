---
title: Instalovat místní nápovědě sady Visual Studio
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-help-viewer
ms.topic: conceptual
f1_keywords:
- hv_manage
helpviewer_keywords:
- changing content installation source [Help Viewer]
- updating local content [Help Viewer]
- Help Viewer, content installation source
- Help Viewer, updating local content
- Help Viewer, changing content installation source
- installing local content [Help Viewer]
- content installation source [Help Viewer]
- downloading content [Help Viewer]
- removing local content [Help Viewer]
- Help Viewer, removing local content
- Help Viewer, installing local content
- Help Viewer, downloading content
ms.assetid: efd9df4c-2e69-4c50-992c-9678a8d8cf19
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 702c1124e3b14f8bfec4f514edd8e1e7def6b776
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="install-and-manage-local-content"></a>Instalace a Správa místního obsahu

Pomocí prohlížeče Microsoft Help Viewer můžete přidat, odebrat, aktualizovat a přesouvat obsah, který je nainstalován v počítači podle vašich potřeb vývoj softwaru.

Ke správě obsahu v místním počítači, musíte se přihlásit pomocí účtu, který má oprávnění správce. Kromě toho nemusí být schopné spravovat místní obsah Pokud pracujete v podnikovém prostředí, protože správce systému může rozhodování pro vaši organizaci. Další informace najdete v tématu [Příručka správce Help Viewer](../ide/help-viewer-administrator-guide.md).

## <a name="change-the-content-installation-source"></a>Změna zdroje instalace obsahu

Ve výchozím nastavení nainstaluje Prohlížeč nápovědy obsah pomocí služby Microsoft online service jako zdroj. Byste obvykle neměli měnit zdroji obsahu Pokud pracujete v podnikovém prostředí, pro který správce systému již nainstalována obsah v jiném umístění.

### <a name="to-change-the-content-installation-source"></a>Chcete-li změnit zdroj instalace obsahu

1.  Na **spravovat obsahu** , zvolte **disku** tlačítko.

    > [!NOTE]
    > **Disku** možnost není dostupná, pokud správce zabránil Změna zdroje instalace obsahu. Další informace najdete v tématu [Příručka správce Help Viewer](../ide/help-viewer-administrator-guide.md).

2.  Proveďte jeden z následujících kroků:

    -   Zadejte cestu *.msha* soubor nebo adresa URL koncového bodu služby.

    -   Zvolte Procházet (**...** ) tlačítko přejděte do *.msha* souboru.

    -   V seznamu vyberte položku, který byl naposledy použit.

## <a name="download-and-install-content-locally"></a>Stáhnout a nainstalovat obsah místně

Je-li stáhnout a nainstalovat obsah v místním počítači, můžete zobrazit témata, pokud nemáte připojení k Internetu.

> [!IMPORTANT]
> Pro instalaci obsahu, musíte se přihlásit pomocí účtu, který má oprávnění správce.

> [!NOTE]
> Pokud Visual Studio IDE je nastavené na jiný jazyk než anglický, můžete nainstalovat anglickou obsah, lokalizovaný obsah nebo obojí. Však žádný obsah se zobrazí po nainstalování pouze v angličtině a **zahrnují anglické obsahu do všech navigační karty a F1 požadavky** zaškrtávací políčko **možnosti prohlížeče** dialogové okno je zrušeno.

### <a name="to-download-and-install-content"></a>Ke stažení a nainstalování obsahu

1.  Vyberte **spravovat obsah** kartě.

2.  V obsahu seznamu, vyberte **přidat** odkaz vedle kniha nebo knihy, které chcete stáhnout a nainstalovat.

     Knihy je přidán do **změny čekající na zpracování** seznam a odhadovanou velikost knihy nebo knihy, které jste zadali, se zobrazí pod tohoto seznamu. Protože některé knihy sdílet témata, může být menší než výsledkem přidání společně velikosti každých adresáře, který jste zadali velikost stažených více knih.

3.  Vyberte **aktualizace** tlačítko.

     Knihy nebo knihy, které jste zadali jsou nainstalovány společně s žádné aktualizace pro knihy, které už máte ve vašem počítači. Časy instalace se liší, ale můžete sledovat průběh na stavovém řádku.

## <a name="remove-local-content"></a>Odebrání lokálního obsahu

Můžete ušetřit místo na disku odstraněním nežádoucí obsahu z vašeho počítače.

> [!IMPORTANT]
> Musíte mít oprávnění správce k odebrání obsahu.

> [!NOTE]
> Žádný obsah se zobrazí, pokud Visual Studio IDE je nastavené na jiný jazyk než anglický, můžete odebrat lokalizovaný obsah a **zahrnují anglické obsahu do všech navigační kartě a F1 požadavky** zaškrtávací políčko **možnosti prohlížeče** dialogové okno je zrušeno.

### <a name="to-remove-content"></a>Odebrání obsahu

1.  Vyberte **spravovat obsah** kartě.

2.  V obsahu seznamu, vyberte **odebrat** odkaz vedle knihy nebo knih, které chcete odebrat.

     Knihy je přidán do **změny čekající na zpracování** seznamu.

3.  Vyberte **aktualizace** tlačítko.

     Knihy nebo knihy, které jste zadali, se odeberou z vašeho počítače.

## <a name="update-local-content"></a>Aktualizace lokálního obsahu

Stavový řádek označuje, když jsou k dispozici aktualizace nainstalovaných obsah.

> [!IMPORTANT]
> Pokud chcete **Help Viewer** Pokud chcete automaticky zjišťovat online aktualizace, je nutné otevřít **možnosti prohlížeče** dialogové okno a potom vyberte **přejděte do režimu online ke kontrole aktualizací obsahu**zaškrtávací políčko.

### <a name="to-update-local-content"></a>Aktualizace lokálního obsahu

-   V pravém dolním rohu stavového řádku, vyberte **kliknutím sem stáhnete teď** odkaz.

 Časy aktualizace se může lišit, ale můžete podívat na průběh aktualizace ve stavovém řádku.

## <a name="move-local-content"></a>Přesunout lokálního obsahu

Přesunutím nainstalované obsahu z místního počítače do sdílené síťové složky nebo do jiného oddílu v místním počítači, můžete ušetřit místo na disku.

> [!IMPORTANT]
> Chcete-li přesunout obsah, musí se přihlásit pomocí účtu, který má oprávnění správce.

### <a name="to-move-local-content"></a>Chcete-li přesunout lokálního obsahu

1.  Na **spravovat obsahu** , zvolte **přesunout** tlačítko pod **místní cesta k úložišti**.

     **Přesunout obsahu** otevře se dialogové okno.

2.  V **k** textového pole zadejte jiné umístění pro obsah a potom zvolte **OK** tlačítko.

3.  Vyberte **Zavřít** když obsah se přesunul.

## <a name="see-also"></a>Viz také

- [Microsoft Help Viewer 2.2](../ide/microsoft-help-viewer.md)