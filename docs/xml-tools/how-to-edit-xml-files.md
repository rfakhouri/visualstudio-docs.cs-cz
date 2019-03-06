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
ms.openlocfilehash: e7da94f8fe07620a67e2df8876cf1d3adda443c5
ms.sourcegitcommit: 3ca33862c1cfc3ccb83de3e95f1e69e860ab143a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/06/2019
ms.locfileid: "57525450"
---
# <a name="how-to-edit-xml-files"></a>Postupy: Úprava souborů XML

XML editor je nový editor souborů XML. Můžete použít samostatný soubor XML nebo soubor přidružený k projektu sady Visual Studio. XML editor souvisí s následujícími příponami: *.config*, *DTD*, *.xml*, *XSD*, *.xdr*, *XSL*, *.xslt*, a *.vssettings*. XML editor je také přidružen jiný soubor typ, který nemá žádné konkrétní editor zaregistrovaný, a který obsahuje obsah XML nebo DTD.

> [!NOTE]
> XHTML dokumenty jsou zpracovány pomocí editoru jazyka HTML.

## <a name="to-edit-an-xml-file"></a>Chcete-li upravit soubor XML

1.  Poklikejte na soubor, který chcete upravit.

### <a name="to-add-a-new-xml-file-to-a-project"></a>Chcete-li přidat nový soubor XML do projektu

1.  Z **projektu** nabídce vyberte možnost **přidat novou položku**.

2.  Vyberte **soubor XML** z **šablony** podokně.

3.  Zadejte název souboru **název** pole a stiskněte klávesu **přidat**.

     Soubor XML je přidán do projektu a otevřené v editoru XML. Tento soubor obsahuje deklaraci XML výchozí `<?xml version="1.0" encoding="utf-8" ?>`.

## <a name="to-add-an-existing-xml-file-to-a-project"></a>Chcete-li přidat k existujícímu souboru XML do projektu

1.  Z **projektu** nabídce vyberte možnost **přidat existující položku**.

     **Přidat existující položku** zobrazí se dialogové okno.

2.  Vyberte soubor XML a stisknutím klávesy **přidat**.

## <a name="to-create-a-new-xml-or-xslt-file"></a>Chcete-li vytvořit nový soubor XML nebo XSLT

1.  Z **souboru** nabídce vyberte možnost **nový**.

     **Nový soubor** zobrazí se dialogové okno.

2.  Vyberte **soubor XML** a vytvořte nový soubor XML, nebo vyberte **soubor XSLT** k vytvoření nové šablony stylů XSLT.

3.  Klikněte na tlačítko **otevřít**.

## <a name="to-create-a-project-for-xml-files"></a>Vytvoření projektu pro soubory XML

1.  Z **souboru** nabídce vyberte možnost **nový**a pak vyberte **projektu**.

     Zobrazí se dialogové okno **Nový projekt**.

2.  Vyberte jazyk kódu podle vašeho výběru, vyberte **prázdný projekt**a klikněte na tlačítko **OK**.

3.  Přidáte soubory XML do projektu.

     XML editor najde schémata, které přidáte do tohoto projektu a používá pro ověření a funkce IntelliSense v XML, schématu nebo soubory XSLT, které upravíte tento projekt je otevřený.

## <a name="see-also"></a>Viz také:

- [XML editor](../xml-tools/xml-editor.md)
- [Vlastnosti dokumentu XML, okno Vlastnosti](../xml-tools/xml-document-properties-properties-window.md)
- [Postupy: Vytvoření schématu XML z dokumentu XML](../xml-tools/how-to-create-an-xml-schema-from-an-xml-document.md)