---
title: Řešení potíží s šablonu Visual Studia a načítání šablony položky
ms.date: 01/02/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: troubleshooting
helpviewer_keywords:
- templates [Visual Studio], troubleshooting
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: 4bb6a10e92bf8f26ffbcb81796b3c5c8371600b5
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31943316"
---
# <a name="how-to-troubleshoot-templates"></a>Postupy: řešení problémů se šablonami

Pokud šablonu se nepodaří načíst ve vývojovém prostředí, existuje několik způsobů, jak vyhledat potíže.

## <a name="validate-the-vstemplate-file"></a>Ověřit soubor vstemplate

Pokud *vstemplate* soubor v šabloně neodpovídající schéma šablony sady Visual Studio, šablona se nemusí zobrazit v **nový projekt** dialogové okno.

### <a name="to-validate-the-vstemplate-file"></a>K ověření souboru vstemplate

1. Vyhledejte *.zip* soubor, který obsahuje šablony.

1. Extrahování *.zip* souboru.

1. Na **soubor** ve Visual Studiu zvolte v nabídce zvolte **otevřete** > **soubor**.

1. Vyberte *vstemplate* souboru šablony a vyberte **otevřete**.

1. Ověřte, že soubor XML *vstemplate* souboru dodržuje schéma šablony. Další informace o *vstemplate* schématu, najdete v části [odkaz na schéma šablon](../extensibility/visual-studio-template-schema-reference.md).

    > [!NOTE]
    > Získat podporu technologie IntelliSense při vytváření *vstemplate* soubor, přidejte `xmlns` atribut `VSTemplate` elementu a přiřaďte ho hodnotu http://schemas.microsoft.com/developer/vstemplate/2005.

1. Uložte a zavřete *vstemplate* souboru.

1. Vyberte soubory obsažené v šabloně, klikněte pravým tlačítkem a zvolte **poslat** > **komprimované složky (ZIP)**. Do jsou komprimované soubory, které jste vybrali *.zip* souboru.

1. Umístěte nové *.zip* souboru ve stejném adresáři jako starý *.zip* souboru.

1. Odstranit extrahované soubory šablony a starou šablonu *.zip* souboru.

## <a name="enable-diagnostic-logging"></a>Povolit protokolování diagnostiky

Můžete povolit protokolování diagnostiky pro zjišťování šablony podle kroků v [zjišťování Poradce při potížích šablony (rozšíření)](../extensibility/troubleshooting-template-discovery.md).

## <a name="see-also"></a>Viz také

- [Řešení potíží s zjišťování šablony (rozšíření)](../extensibility/troubleshooting-template-discovery.md)
- [Přizpůsobení šablony](../ide/customizing-project-and-item-templates.md)
- [Vytváření šablon projektů a položek](../ide/creating-project-and-item-templates.md)
- [Odkaz na schéma šablon](../extensibility/visual-studio-template-schema-reference.md)