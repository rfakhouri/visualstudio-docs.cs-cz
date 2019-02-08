---
title: Řešení potíží s šablony projektu a načítání šablony položky
ms.date: 01/02/2018
ms.topic: troubleshooting
helpviewer_keywords:
- templates [Visual Studio], troubleshooting
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 2b3a94ab9a44776b0c6716b99f594ec0fd840938
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/08/2019
ms.locfileid: "55943412"
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