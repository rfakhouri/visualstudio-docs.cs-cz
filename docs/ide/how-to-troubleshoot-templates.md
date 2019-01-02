---
title: Řešení potíží s šablony projektu a načítání šablony položky
ms.date: 01/02/2018
ms.prod: visual-studio-dev15
ms.topic: troubleshooting
helpviewer_keywords:
- templates [Visual Studio], troubleshooting
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: 4908716ce5f984aef6dbd3d482a26e1aeb94623d
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53890914"
---
# <a name="how-to-troubleshoot-templates"></a>Postupy: Řešení problémů se šablonami

Pokud šablonu se nepodaří načíst ve vývojovém prostředí, nalezení problému několika způsoby.

## <a name="validate-the-vstemplate-file"></a>Ověřit soubor vstemplate

Pokud *vstemplate* soubor v šabloně neodpovídající schématu pro šablony sady Visual Studio, šablony se nemůže nacházet v **nový projekt** dialogové okno.

### <a name="to-validate-the-vstemplate-file"></a>Chcete-li ověřit soubor vstemplate

1. Vyhledejte *ZIP* soubor, který obsahuje šablonu.

1. Extrahovat *ZIP* souboru.

1. Na **souboru** nabídku v sadě Visual Studio, zvolte **otevřít** > **souboru**.

1. Vyberte *vstemplate* soubor šablony a zvolte **otevřít**.

1. Ověřte, že se souborem XML sady *vstemplate* soubor používá schéma šablony. Další informace o *vstemplate* schématu, naleznete v tématu [odkaz na schéma šablon](../extensibility/visual-studio-template-schema-reference.md).

    > [!NOTE]
    > Jak získat podporu technologie IntelliSense při vytváření *vstemplate* přidejte `xmlns` atribut `VSTemplate` prvek a přiřaďte ho hodnotu http://schemas.microsoft.com/developer/vstemplate/2005.

1. Uložte a zavřete *vstemplate* souboru.

1. Vyberte soubory, které jsou součástí šablony, klikněte pravým tlačítkem a zvolte **odeslat** > **komprimovanou složku (ZIP)**. Do jsou komprimované soubory, které jste vybrali *ZIP* souboru.

1. Umístit novou *ZIP* souboru ve stejném adresáři jako původní *ZIP* souboru.

1. Odstranit extrahované soubory šablony a starou šablonu *ZIP* souboru.

## <a name="enable-diagnostic-logging"></a>Povolit protokolování diagnostiky

Můžete povolit protokolování diagnostiky pro zjišťování šablon podle postupu v [zjišťování Poradce při potížích šablony (rozšiřitelnost)](../extensibility/troubleshooting-template-discovery.md).

## <a name="see-also"></a>Viz také:

- [Řešení potíží s zjišťování šablony (rozšiřitelnost)](../extensibility/troubleshooting-template-discovery.md)
- [Přizpůsobení šablony](../ide/customizing-project-and-item-templates.md)
- [Vytváření šablon projektů a položek](../ide/creating-project-and-item-templates.md)
- [Odkaz na schéma šablon](../extensibility/visual-studio-template-schema-reference.md)