---
title: "Aktualizace existujících šablon projektů a položek v sadě Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 01/02/2018
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- item templates, updating
- Visual Studio templates, updating
- project templates, updating
- updating templates [Visual Studio]
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 9401f8a9a07f7098575ff267825982a03024e968
ms.sourcegitcommit: 9357209350167e1eb7e50b483e44893735d90589
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/05/2018
---
# <a name="how-to-update-existing-templates"></a>Postupy: aktualizace existujících šablon

Po vytvoření šablony a komprimovat soubory do souboru ZIP, můžete upravit šablonu. Můžete to provést ruční změnou soubory v šabloně, nebo tak, že vyexportujete novou šablonu z projektu, který je založený na šabloně.

## <a name="using-the-export-template-wizard-to-update-an-existing-project-template"></a>Pomocí Průvodce šablonou exportovat, a aktualizovat existující šablony projektu

Visual Studio poskytuje **Průvodce exportem šablony** , můžete použít k aktualizaci existující šablony:

1. Otevřete **nový projekt** dialogové okno a vybrat **soubor** > **nový** > **projektu**.

1. Vyberte šablonu, kterou chcete aktualizovat, zadejte název a umístění pro svůj projekt a zvolte **OK**.

1. Změňte na projekt v sadě Visual Studio.

1. Na **projektu** nabídce zvolte **exportovat šablonu...** .

    **Průvodce exportem šablony** otevře.

1. Postupujte podle pokynů v Průvodci vyexportujte šablonu jako soubor ZIP.

1. (Volitelné) Chcete-li přidat šablonu, kterou chcete **nový projekt** dialogové okno pole, uložte soubor .zip v následujícím adresáři: %USERPROFILE%\Documents\Visual Studio \<verze\>\Templates\ProjectTemplates. Bude nutné tento krok proveďte, pokud jste nevybrali možnost **automaticky importovat šablonu do sady Visual Studio** v **Průvodce exportem šablony**.

1. Odstraňte původní soubor .zip šablony.

## <a name="manually-updating-an-existing-template"></a>Ruční aktualizace existující šablony

Můžete aktualizovat existující šablony bez použití **Průvodce exportem šablony**, úpravou soubory v komprimovaném souboru ZIP.

### <a name="to-manually-update-an-existing-template"></a>Chcete-li ručně aktualizovat existující šablony

1. Vyhledejte soubor .zip, který obsahuje šablony. Šablony projektů uživatele jsou obvykle umístěné na %USERPROFILE%\Documents\Visual Studio \<verze\>\Templates\ProjectTemplates.

1. Rozbalte soubor .zip.

1. Upravit nebo odstranit aktuální soubory šablon nebo přidejte nové soubory do šablony.

1. Otevřít, upravit a uložit .vstemplate soubor XML pro zpracování chování aktualizované nebo nové soubory.

    Další informace o schématu .vstemplate najdete v tématu [odkaz na schéma šablon sady Visual Studio (rozšiřitelnost)](../extensibility/visual-studio-template-schema-reference.md). Další informace o můžete parametrizovat ve zdrojových souborech najdete v tématu [parametry šablony](../ide/template-parameters.md).

1. Vyberte soubory v šabloně a v nabídce klikněte pravým tlačítkem nebo kontextu a zvolte **poslat** > **komprimované složky (ZIP)**.

    Do souboru .zip jsou komprimované soubory, které jste vybrali.

1. Nový soubor .zip umístěte do stejného adresáře jako starý soubor .zip.

1. Odstraňte extrahované soubory šablony a původní soubor .zip šablony.

## <a name="see-also"></a>Viz také

[Přizpůsobení šablon](../ide/customizing-project-and-item-templates.md)  
[Vytváření šablon projektů a položek](../ide/creating-project-and-item-templates.md)  
[Odkaz na schéma šablon sady Visual Studio](../extensibility/visual-studio-template-schema-reference.md)  
[Parametry šablony](../ide/template-parameters.md)  
[Postupy: Vytváření startovních sad](../ide/how-to-create-starter-kits.md)