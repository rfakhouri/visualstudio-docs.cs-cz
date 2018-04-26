---
title: 'Postupy: úpravy souborů XML'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-xml-tools
ms.topic: conceptual
ms.assetid: 07fa3ecf-6345-4d30-9d85-d5ef5b083319
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e35baa6d6d7c5cba696ab7b5e0bb57dd722b5d7b
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-edit-xml-files"></a>Postupy: úpravy souborů XML

Editor souborů XML je nové editor souborů XML. Lze použít v samostatném souboru XML nebo na soubor přidružený k projektu sady Visual Studio. Editor souborů XML je přidružen následující přípony souborů: .config, DTD, XML, XSD, .xdr, XSL, XSLT a .vssettings. Editor souborů XML je taky přiřazený další soubor jakéhokoli typu, nemá žádné konkrétní editor registrován a který obsahuje XML DTD obsahu.

> [!NOTE]
> XHTML dokumenty jsou zpracovávány HTML Editor.

## <a name="to-edit-an-xml-file"></a>Chcete-li upravit soubor XML

1.  Poklikejte na soubor, který chcete upravit.

### <a name="to-add-a-new-xml-file-to-a-project"></a>Chcete-li přidat nový soubor XML do projektu

1.  Z **projektu** nabídce vyberte možnost **přidat novou položku**.

2.  Vyberte **souboru XML** z **šablony** podokně.

3.  Zadejte název souboru **název** pole a stiskněte klávesu **přidat**.

     Soubor XML do projektu a je otevřen v editoru XML. Tento soubor obsahuje deklaraci XML výchozí `<?xml version="1.0" encoding="utf-8" ?>`.

## <a name="to-add-an-existing-xml-file-to-a-project"></a>Chcete-li přidat existující soubor XML do projektu

1.  Z **projektu** nabídce vyberte možnost **přidat existující položku**.

     **Přidat existující položku** zobrazí se dialogové okno.

2.  Vyberte soubor XML a stiskněte klávesu **přidat**.

## <a name="to-create-a-new-xml-or-xslt-file"></a>Chcete-li vytvořit nový soubor XML nebo XSLT

1.  Z **soubor** nabídce vyberte možnost **nový**.

     **Nový soubor** zobrazí se dialogové okno.

2.  Vyberte **souboru XML** vytvořte nový soubor XML; nebo vyberte **soubor XSLT** k vytvoření nové šablony stylů XSLT.

3.  Klikněte na tlačítko **otevřete**.

## <a name="to-create-a-project-for-xml-files"></a>Vytvoření projektu pro soubory XML

1.  Z **soubor** nabídce vyberte možnost **nový**a potom vyberte **projektu**.

     **Nový projekt** zobrazí se dialogové okno.

2.  Vyberte jazyk kódu podle vaší volby, vyberte **prázdný projekt**a klikněte na tlačítko **OK**.

3.  Přidáte soubory XML do projektu.

     Editor souborů XML vyhledá schémat, které přidáte do projektu a použije je pro ověřování a IntelliSense v libovolném XML, schéma nebo XSLT soubory, které můžete upravit tento projekt je otevřen.

## <a name="see-also"></a>Viz také

- [Editor XML](../xml-tools/xml-editor.md)
- [Vlastnosti dokumentu XML, okno Vlastnosti](../xml-tools/xml-document-properties-properties-window.md)
- [Postupy: Vytvoření schématu XML z dokumentu XML](../xml-tools/how-to-create-an-xml-schema-from-an-xml-document.md)