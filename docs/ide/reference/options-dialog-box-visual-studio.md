---
title: Dialogové okno Možnosti (Visual Studio)
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- vs.toolsoptionspages
helpviewer_keywords:
- Tools Options settings
- Options dialog box
- Options dialog box, development environment
- tools [Visual Studio], customizing
ms.assetid: 02b09877-1df1-4531-a0d1-a4ca17c7f857
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 13af30391d73c94418131b95cd2ad02bc4f48116
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31946647"
---
# <a name="options-dialog-box-visual-studio"></a>Dialogové okno Možnosti (Visual Studio)
**Možnosti** dialogové okno umožňuje nakonfigurovat integrované vývojové prostředí (IDE) vašim potřebám. Můžete například vytvořit výchozí umístění pro uložení pro projekty, změnit výchozí vzhled a chování systému windows a vytvoření zkratky pro často používané příkazy. Existují také možnosti specifické pro platformu a vývoj jazyk. Dostanete **možnosti** z **nástroje** nabídky.

> [!NOTE]
> K dispozici v dialogových oken, názvy a umístění příkazy nabídky, které vidíte, se může lišit od co je popsáno v nápovědě v závislosti na aktivním nastavení nebo edici. Chcete-li změnit nastavení, zvolte **nastavení importu a exportu** na **nástroje** nabídky. Další informace najdete v tématu [přizpůsobení prostředí Visual Studio IDE](../../ide/personalizing-the-visual-studio-ide.md).


## <a name="layout-of-the-options-dialog-box"></a>Rozložení dialogové okno Možnosti
 **Možnosti** dialogové okno je rozdělené do dvou částí: navigačního podokna na levé straně a zobrazení oblast na pravé straně. V navigačním podokně ovládacího prvku strom obsahuje uzel, složky, například prostředí, textový Editor, projekty a řešení a správy zdrojového kódu. Rozbalte uzel všechny složky k zobrazení seznamu stránek možností, které obsahuje. Když vyberete uzel pro konkrétní stránky, zobrazí se jeho možnosti v oblasti zobrazení.

 Možnosti pro IDE funkci v navigačním podokně nezobrazí, dokud nebude tato funkce je načten do paměti. Proto nemusí být zobrazeny stejné možnosti jako zahájit novou relaci, která se zobrazí jako skončila poslední. Při vytváření projektu nebo spustit příkaz, který používá konkrétní aplikace, uzlů pro příslušné možnosti se přidají do dialogové okno Možnosti. Tyto přidat možnosti zůstává k dispozici funkci IDE zůstává v paměti.

> [!NOTE]
> Některé kolekce nastavení oboru na počet stránek, které se zobrazují v navigačním podokně dialogové okno Možnosti. Můžete zobrazit všechny možné stránky tak, že vyberete **zobrazit všechna nastavení**.


## <a name="how-options-are-applied"></a>Použití možností
 Kliknutím na OK v **možnosti** dialogové okno uloží všechna nastavení na všech stránkách. Kliknutím na tlačítko Storno na libovolné stránce zruší všechny žádosti o změnu, včetně všech právě probíhají jiné **možnosti** stránky. Některé změny nastavení možnosti, například těch, které probíhají [písma a barvy, prostředí, dialogové okno Možnosti](../../ide/reference/fonts-and-colors-environment-options-dialog-box.md), bude pouze se projeví po můžete zavřít a znovu otevřete Visual Studio.

### <a name="show-all-settings"></a>Zobrazit všechna nastavení
 Výběr nebo unselecting **zobrazit všechna nastavení** platí všechny změny provedené v **možnosti** dialogové okno, i když ještě neklikli **OK**.

## <a name="see-also"></a>Viz také

- [Vlastní nastavení editoru](../../ide/customizing-the-editor.md)