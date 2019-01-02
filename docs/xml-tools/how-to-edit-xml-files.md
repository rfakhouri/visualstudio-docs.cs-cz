---
title: 'Postupy: Úpravy souborů XML'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: conceptual
ms.assetid: 07fa3ecf-6345-4d30-9d85-d5ef5b083319
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d5fc57c894c1e3a616062f01cc46103b4714fa35
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53849042"
---
# <a name="how-to-edit-xml-files"></a>Postupy: Úprava souborů XML

XML Editor je nový editor souborů XML. Můžete použít samostatný soubor XML nebo soubor přidružený k projektu sady Visual Studio. XML Editor souvisí s následujícími příponami: *.config*, *DTD*, *.xml*, *XSD*, *.xdr*, *XSL*, *.xslt*, a *.vssettings*. XML Editor je také přidružen jiný soubor typ, který nemá žádné konkrétní editor zaregistrovaný, a který obsahuje obsah XML nebo DTD.

> [!NOTE]
> XHTML dokumenty jsou zpracovány pomocí editoru jazyka HTML.

## <a name="to-edit-an-xml-file"></a>Chcete-li upravit soubor XML

1.  Poklikejte na soubor, který chcete upravit.

### <a name="to-add-a-new-xml-file-to-a-project"></a>Chcete-li přidat nový soubor XML do projektu

1.  Z **projektu** nabídce vyberte možnost **přidat novou položku**.

2.  Vyberte **soubor XML** z **šablony** podokně.

3.  Zadejte název souboru **název** pole a stiskněte klávesu **přidat**.

     Soubor XML je přidán do projektu a otevřít v editoru XML. Tento soubor obsahuje deklaraci XML výchozí `<?xml version="1.0" encoding="utf-8" ?>`.

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

     XML Editor najde schémata, které přidáte do tohoto projektu a používá pro ověření a funkce IntelliSense v XML, schématu nebo soubory XSLT, které upravíte tento projekt je otevřený.

## <a name="see-also"></a>Viz také:

- [Editor XML](../xml-tools/xml-editor.md)
- [Vlastnosti dokumentu XML, okno Vlastnosti](../xml-tools/xml-document-properties-properties-window.md)
- [Postupy: Vytvoření schématu XML z dokumentu XML](../xml-tools/how-to-create-an-xml-schema-from-an-xml-document.md)