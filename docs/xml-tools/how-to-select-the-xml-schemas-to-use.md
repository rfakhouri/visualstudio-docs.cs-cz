---
title: 'Postupy: Výběr schémat XML pro použití'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-xml-tools
ms.topic: conceptual
ms.assetid: d6fda3ef-d465-4788-8514-2f2d528d658c
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d835a8592108b549a109f7bb7e128a8ae5b01611
ms.sourcegitcommit: 697162f54d3c4e30df702fd0289e447e211e3a85
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/25/2018
---
# <a name="how-to-select-the-xml-schemas-to-use"></a>Postupy: Výběr schémat XML používat

Nabízí XML Editor nachází v mezipaměti schématu *%InstallDir%\Xml\Schemas* adresáře. Mezipaměti schématu zahrnuje dobře známými schématy XML, které se používají pro ověřování dokumentu IntelliSense a XML.

**Schémata** vlastnost dokumentu se používá k vyberte jeden nebo více schématu XML schéma definition language (XSD). použít. Umožní vám vybrat schémata z mezipaměti schématu, nebo zadejte schéma, které se nenachází v mezipaměti.

Schémata zadáte se ukládají do skrytého souboru možnosti uživatele řešení (. *suo –*), spolu s všechny ostatní XML vlastností dokumentu. V důsledku toho nebude muset zadávat znovu tyto hodnoty při příštím otevření řešení.

> [!NOTE]
> Editor můžete ověřit pomocí vložené schéma nebo schéma. odkazuje `xsd:schemaLocation` atribut. Další informace najdete v tématu [ověření dokumentu XML](../xml-tools/xml-document-validation.md).

## <a name="to-select-an-xml-schema-from-the-schema-cache"></a>Chcete-li vybrat schématu XML z mezipaměti schématu

1.  Otevření souboru v editoru XML.

2.  V okně vlastností dokumentu klikněte na tlačítko **schémata** pole.

     **Schémat XML** se zobrazí dialogové okno. Dialogové okno obsahuje seznam všech schémata s. *xsd* rozšíření v mezipaměti schématu (včetně schémata v odkazuje *catalog.xml* soubor) a také žádné schéma, který se v aktuálním řešení, otevřete v sadě Visual Studio, odkazuje v `xsd:schemaLocation` atribut, nebo v odkazuje **schémata** vlastnost.

3.  Vyberte schémata k ověření pomocí jedné z následujících akcí:

    -   Vyberte schéma uvedené v **schémat XML** dialogové okno, klikněte na tlačítko **použití** sloupec a potom vyberte **toto schéma používají**.

     -nebo-

    -   Vyberte více schématy uvedené v **schémat XML** dialogové okno, klikněte pravým tlačítkem a vyberte **toto schéma používají**.

4.  Click **OK**.

     Seznam vybraných schémat zkopírují se **schémata** dokumentu vlastnost.

## <a name="to-add-an-xml-schema-to-the-schema-cache"></a>Přidání schématu XML do mezipaměti schématu

1.  V okně vlastností dokumentu klikněte na tlačítko **schémata** pole.

2.  Klikněte na tlačítko **přidat**.

     Tím se otevře **otevřete schématu XSD** dialogové okno.

3.  Procházet a vyberte schématech pro přidání do mezipaměti schématu.

4.  Klikněte na tlačítko **otevřete**.

     Schématech přidané do schématu mezipaměti a je **použití** hodnota sloupce je nastavena na **toto schéma používají**.

## <a name="to-delete-an-xml-schema-from-the-schema-cache"></a>Odstraňte z mezipaměti schématu schématu XML

1.  V okně vlastností dokumentu klikněte na tlačítko **schémata** pole.

2.  Vyberte schéma tak, aby odeberte a pak klikněte na tlačítko **odebrat**.

     Schéma se odebere z mezipaměti v paměti schématu, ale není odebrána ze systému souborů.

    > [!NOTE]
    > Pokud jste ještě odkaz na schéma prostřednictvím `schemaLocation` atribut, nebo odpovídající `targetNamespace` pak **odebrat** nebude fungovat v této situaci kvůli automatické přidružení. V takovém případě se doporučuje, aby označíte schéma jako **nepoužívejte vybrané schémata** v **použít** sloupce.

## <a name="see-also"></a>Viz také

- [Mezipaměti schématu](../xml-tools/schema-cache.md)
- [Dialogové okno schémat XML](../xml-tools/xml-schemas-dialog-box.md)
- [Editor XML](../xml-tools/xml-editor.md)