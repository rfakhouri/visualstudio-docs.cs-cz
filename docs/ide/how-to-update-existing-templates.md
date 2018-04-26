---
title: Aktualizace existujících šablon projektů a položek v sadě Visual Studio
ms.date: 01/02/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- item templates, updating
- Visual Studio templates, updating
- project templates, updating
- updating templates [Visual Studio]
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: f5cf764f76d72b17128c46f2b7ec16ffcf4153cf
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-update-existing-templates"></a>Postupy: aktualizace existujících šablon

Po vytvoření šablony a komprimovat soubor do *.zip* souboru, můžete upravit šablonu. Můžete to provést ruční změnou soubory v šabloně, nebo tak, že vyexportujete novou šablonu z projektu, který je založený na šabloně.

## <a name="using-the-export-template-wizard-to-update-an-existing-project-template"></a>Pomocí Průvodce šablonou exportovat, a aktualizovat existující šablony projektu

Visual Studio poskytuje **Průvodce exportem šablony** , můžete použít k aktualizaci existující šablony:

1. Otevřete **nový projekt** dialogové okno a vybrat **soubor** > **nový** > **projektu**.

1. Vyberte šablonu, kterou chcete aktualizovat, zadejte název a umístění pro svůj projekt a zvolte **OK**.

1. Změňte na projekt v sadě Visual Studio.

1. Na **projektu** nabídce zvolte **exportovat šablonu**.

    **Průvodce exportem šablony** otevře.

1. Postupujte podle pokynů v průvodci export šablony jako *.zip* souboru.

1. (Volitelné) Chcete-li přidat šablonu, kterou chcete **nový projekt** dialogové okno, místo *.zip* soubor v následujícím adresáři: *%USERPROFILE%\Documents\Visual Studio \<verze\>\Templates\ProjectTemplates*. Bude nutné tento krok proveďte, pokud jste nevybrali možnost **automaticky importovat šablonu do sady Visual Studio** v **Průvodce exportem šablony**.

1. Odstranit starou šablonu *.zip* souboru.

## <a name="manually-update-an-existing-template"></a>Ručně aktualizovat existující šablony

Můžete aktualizovat existující šablony bez použití **Průvodce exportem šablony**, úpravou souborů komprimovaný *.zip* souboru.

### <a name="to-manually-update-an-existing-template"></a>Chcete-li ručně aktualizovat existující šablony

1. Vyhledejte *.zip* soubor, který obsahuje šablony. Šablony projektů uživatele jsou umístěny na *%USERPROFILE%\Documents\Visual Studio \<verze\>\Templates\ProjectTemplates*.

1. Extrahování *.zip* souboru.

1. Upravit nebo odstranit aktuální soubory šablon nebo přidejte nové soubory do šablony.

1. Otevřít, upravit a uložit *.vstemplate* soubor XML pro zpracování chování aktualizované nebo nové soubory.

    Další informace o *.vstemplate* schématu, najdete v části [odkaz na schéma šablon sady Visual Studio (rozšiřitelnost)](../extensibility/visual-studio-template-schema-reference.md). Další informace o můžete parametrizovat ve zdrojových souborech najdete v tématu [parametry šablony](../ide/template-parameters.md).

1. Vyberte soubory v šabloně a v nabídce klikněte pravým tlačítkem nebo kontextu a zvolte **poslat** > **komprimované složky (ZIP)**.

    Do jsou komprimované soubory, které jste vybrali *.zip* souboru.

1. Uveďte nové *.zip* souboru ve stejném adresáři jako starý *.zip* souboru.

1. Odstranit extrahované soubory šablony a starou šablonu *.zip* souboru.

## <a name="see-also"></a>Viz také

- [Přizpůsobení šablony](../ide/customizing-project-and-item-templates.md)
- [Vytváření šablon projektů a položek](../ide/creating-project-and-item-templates.md)
- [Visual Studio odkaz na schéma šablon](../extensibility/visual-studio-template-schema-reference.md)
- [Parametry šablony](../ide/template-parameters.md)
- [Postupy: vytváření Startovních sad](../ide/how-to-create-starter-kits.md)