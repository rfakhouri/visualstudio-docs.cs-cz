---
title: Aktualizovat existující šablony položek projektu
ms.date: 01/02/2018
ms.prod: visual-studio-dev15
ms.topic: conceptual
helpviewer_keywords:
- item templates, updating
- Visual Studio templates, updating
- project templates, updating
- updating templates [Visual Studio]
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: b5f72f6cbe2fcf3be2566fd7e51d7366dd2563ae
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54985887"
---
# <a name="how-to-update-existing-templates"></a>Postupy: Aktualizace existujících šablon

Po vytvoření šablony a soubory do komprimovat *ZIP* soubor, můžete upravit šablonu. Můžete to provést ručně změnou soubory v šabloně, nebo tak, že vyexportujete novou šablonu z projektu, který je založen na šabloně.

## <a name="using-the-export-template-wizard-to-update-an-existing-project-template"></a>Pomocí Průvodce exportem šablony, a aktualizovat existující šablony projektu

Visual Studio poskytuje **Průvodce exportem šablony** , který slouží k aktualizaci existující šablony:

1. Otevřít **nový projekt** dialogové okno výběrem **souboru** > **nový** > **projektu**.

1. Vyberte šablonu, kterou chcete aktualizovat, zadejte název a umístění pro váš projekt a zvolte **OK**.

1. Upravte projekt v sadě Visual Studio.

1. Na **projektu** nabídce zvolte **exportovat šablonu**.

    **Průvodce exportem šablony** otevře.

1. Postupujte podle pokynů v průvodci export šablony jako *ZIP* souboru.

1. (Volitelné) Chcete-li přidat šablonu, kterou chcete **nový projekt** dialogové okno, místo *ZIP* soubor v následujícím adresáři: *%USERPROFILE%\Documents\Visual Studio \<verze\>\Templates\ProjectTemplates*. Bude potřeba tento krok proveďte, pokud jste nevybrali možnost **automaticky importovat šablonu do sady Visual Studio** v **Průvodce exportem šablony**.

1. Odstranit starou šablonu *ZIP* souboru.

## <a name="manually-update-an-existing-template"></a>Ručně aktualizovat existující šablony

Bez použití můžete aktualizovat existující šablonu **Průvodce exportem šablony**, tak, že upravíte soubory komprimované *ZIP* souboru.

### <a name="to-manually-update-an-existing-template"></a>Chcete-li ručně aktualizovat existující šablony

1. Vyhledejte *ZIP* soubor, který obsahuje šablonu. Šablony projektů uživatele jsou umístěné na *%USERPROFILE%\Documents\Visual Studio \<verze\>\Templates\ProjectTemplates*.

1. Extrahovat *ZIP* souboru.

1. Upravit nebo odstranit aktuální soubory šablon nebo přidejte nové soubory do šablony.

1. Otevřít, upravit a uložit *.vstemplate* soubor XML pro zpracování chování aktualizované nebo nové soubory.

    Další informace o *.vstemplate* schématu, naleznete v tématu [odkaz na schéma šablon sady Visual Studio (rozšiřitelnost)](../extensibility/visual-studio-template-schema-reference.md). Další informace o můžete parametrizovat ve zdrojových souborech najdete v tématu [parametry šablony](../ide/template-parameters.md).

1. Vyberte soubory v šabloně a v nabídce klepněte pravým tlačítkem nebo kontextu a zvolte **odeslat** > **komprimovanou složku (ZIP)**.

    Do jsou komprimované soubory, které jste vybrali *ZIP* souboru.

1. Vložit nový *ZIP* souboru ve stejném adresáři jako původní *ZIP* souboru.

1. Odstranit extrahované soubory šablony a starou šablonu *ZIP* souboru.

## <a name="see-also"></a>Viz také:

- [Přizpůsobení šablony](../ide/customizing-project-and-item-templates.md)
- [Vytváření šablon projektů a položek](../ide/creating-project-and-item-templates.md)
- [Visual Studio odkaz na schéma šablon](../extensibility/visual-studio-template-schema-reference.md)
- [Parametry šablony](../ide/template-parameters.md)