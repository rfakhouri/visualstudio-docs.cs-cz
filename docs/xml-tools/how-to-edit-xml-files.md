---
title: 'Postupy: Úpravy souborů XML'
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 07fa3ecf-6345-4d30-9d85-d5ef5b083319
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: b25eebad9efc70e4fda45131e232983e81961625
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62840366"
---
# <a name="how-to-edit-xml-files"></a>Postupy: Úpravy souborů XML

XML editor je nový editor souborů XML. Můžete použít samostatný soubor XML nebo soubor přidružený k projektu sady Visual Studio. XML editor souvisí s následujícími příponami: *.config*, *DTD*, *.xml*, *XSD*, *.xdr*, *XSL*, *.xslt*, a *.vssettings*. XML editor je také přidružen jiný soubor typ, který nemá žádné konkrétní editor zaregistrovaný, a který obsahuje obsah XML nebo DTD.

> [!NOTE]
> XHTML dokumenty jsou zpracovány pomocí editoru jazyka HTML.

Chcete-li upravit soubor XML, poklikejte na soubor, který chcete upravit.

## <a name="add-a-new-xml-file-to-a-project"></a>Přidejte nový soubor XML do projektu

1. Z **projektu** nabídce vyberte možnost **přidat novou položku**.

2. Vyberte **soubor XML** z **šablony** podokně.

3. Zadejte název souboru **název** pole a stiskněte klávesu **přidat**.

   Soubor XML přidán do projektu a otevře v editoru XML. Tento soubor obsahuje deklaraci XML výchozí `<?xml version="1.0" encoding="utf-8" ?>`.

## <a name="add-an-existing-xml-file-to-a-project"></a>Přidání stávajícího souboru XML do projektu

1. Z **projektu** nabídce vyberte možnost **přidat existující položku**.

   **Přidat existující položku** zobrazí se dialogové okno.

2. Vyberte soubor XML a stisknutím klávesy **přidat**.

## <a name="create-a-new-xml-or-xslt-file"></a>Vytvořte nový soubor XML nebo XSLT

1. Z **souboru** nabídce vyberte možnost **nový**.

   **Nový soubor** zobrazí se dialogové okno.

2. Vyberte **soubor XML** a vytvořte nový soubor XML, nebo vyberte **soubor XSLT** k vytvoření nové šablony stylů XSLT.

3. Klikněte na tlačítko **otevřít**.

## <a name="create-an-empty-project-for-xml-files"></a>Vytvořit prázdný projekt pro soubory XML

::: moniker range="vs-2017"

1. Z **souboru** nabídce vyberte možnost **nový** > **projektu**.

   Zobrazí se dialogové okno **Nový projekt**.

2. Vyberte jazyk kódu podle vašeho výběru, vyberte **prázdný projekt**.

3. Klikněte na **OK**.

::: moniker-end

::: moniker range=">=vs-2019"

1. Z **souboru** nabídce vyberte možnost **nový** > **projektu**.

2. Zadejte **prázdný projekt** do vyhledávacího pole šablony, vyberte **prázdný projekt (.NET Framework)** šablonu a pak klikněte na tlačítko **Další**.

3. Klikněte na možnost **Vytvořit**.

::: moniker-end

4. Přidáte soubory XML do projektu.

   XML editor najde schémata, které přidáte do tohoto projektu a používá pro ověření a funkce IntelliSense v XML, schématu nebo soubory XSLT, které upravíte tento projekt je otevřený.

## <a name="see-also"></a>Viz také:

- [XML editor](../xml-tools/xml-editor.md)
- [Vlastnosti dokumentu XML, okno Vlastnosti](../xml-tools/xml-document-properties-properties-window.md)
- [Postupy: Vytvoření schématu XML z dokumentu XML](../xml-tools/how-to-create-an-xml-schema-from-an-xml-document.md)