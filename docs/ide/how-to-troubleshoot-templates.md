---
title: "Řešení potíží s šablonu Visual Studia a šablony položky načítání | Microsoft Docs"
ms.custom: 
ms.date: 01/02/2018
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- templates [Visual Studio], troubleshooting
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: d9242d053044fa66e6eb3d506382cf7cfb5d0295
ms.sourcegitcommit: f89ed5fc2e5078213e30a6ade4604e34df48181f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/13/2018
---
# <a name="how-to-troubleshoot-templates"></a>Postupy: řešení problémů se šablonami

Pokud šablonu se nepodaří načíst ve vývojovém prostředí, existuje několik způsobů, jak vyhledat potíže.

## <a name="validate-the-vstemplate-file"></a>Ověřit soubor .vstemplate

Pokud soubor .vstemplate v šabloně nedrží schéma šablony sady Visual Studio, šablona se nemusí zobrazit v **nový projekt** dialogové okno.

### <a name="to-validate-the-vstemplate-file"></a>K ověření souboru .vstemplate

1. Vyhledejte soubor .zip, který obsahuje šablony.

1. Rozbalte soubor .zip.

1. Na **soubor** ve Visual Studiu zvolte v nabídce zvolte **otevřete** > **soubor**.

1. Vyberte soubor .vstemplate pro šablonu a vyberte **otevřete**.

1. Ověřte, že XML soubor .vstemplate dodržuje schéma šablony. Další informace o schématu .vstemplate najdete v tématu [odkaz na schéma šablon](../extensibility/visual-studio-template-schema-reference.md).

    > [!NOTE]
    > Chcete-li získat podporu technologie IntelliSense při vytváření souboru .vstemplate, přidejte `xmlns` atribut `VSTemplate` elementu a přiřaďte ho hodnotu http://schemas.microsoft.com/developer/vstemplate/2005.

1. Uložte a zavřete soubor .vstemplate.

1. Vyberte soubory obsažené v šabloně, klikněte pravým tlačítkem a zvolte **poslat** > **komprimované složky (ZIP)**. Do souboru .zip jsou komprimované soubory, které jste vybrali.

1. Nový soubor .zip umístíte ve stejném adresáři jako starý soubor .zip.

1. Odstraňte extrahované soubory šablony a původní soubor .zip šablony.

## <a name="enable-diagnostic-logging"></a>Povolit protokolování diagnostiky

Můžete povolit protokolování diagnostiky pro zjišťování šablony podle kroků v [zjišťování Poradce při potížích s šablony (rozšíření)](../extensibility/troubleshooting-template-discovery.md).

## <a name="see-also"></a>Viz také

[Řešení potíží s zjišťování šablony (rozšíření)](../extensibility/troubleshooting-template-discovery.md)  
[Přizpůsobení šablon](../ide/customizing-project-and-item-templates.md)  
[Vytváření šablon projektů a položek](../ide/creating-project-and-item-templates.md)  
[Odkaz na schéma šablon](../extensibility/visual-studio-template-schema-reference.md)