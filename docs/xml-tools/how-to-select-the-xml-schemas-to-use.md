---
title: 'Postupy: Výběr schémat XML pro použití'
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: d6fda3ef-d465-4788-8514-2f2d528d658c
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 41f830214b20df24587cf902e6b180e8a43a8cd3
ms.sourcegitcommit: 3ca33862c1cfc3ccb83de3e95f1e69e860ab143a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/06/2019
ms.locfileid: "57526669"
---
# <a name="how-to-select-the-xml-schemas-to-use"></a>Postupy: Výběr schémat XML pro použití

XML editor poskytuje nachází v mezipaměti schématu *%VSInstallDir%\xml\Schemas* adresáře. Mezipaměti schématu obsahuje dobře známými schématy XML, které slouží k ověření dokumentu technologie IntelliSense a XML.

Použití **schémata** vlastnost výběr jeden nebo více XML schématu definice jazyk (XSD) schématu dokumentu. Můžete vybrat schémata z mezipaměti schémat nebo jinde.

Schémata zadáte se ukládají do souboru řešení (skryté) uživatelské možnosti (. *suo*), společně s další XML vlastnosti dokumentu. V důsledku toho není nutné znovu zadat tyto hodnoty při příštím otevření řešení.

> [!NOTE]
> V editoru můžete ověřit pomocí vložené schéma nebo schéma. odkazuje `xsd:schemaLocation` atribut. Další informace najdete v tématu [ověření dokumentu XML](../xml-tools/xml-document-validation.md).

## <a name="to-select-an-xml-schema-from-the-schema-cache"></a>Chcete-li vybrat schématu XML z mezipaměti schémat

1. Otevření souboru v editoru XML.

2. V okně Vlastnosti dokumentu, klikněte na tlačítko v **schémata** pole. Pokud tlačítko Procházet (...) se zobrazí, klikněte na něj.

   ![Vlastnost schémat pro soubor XML](media/properties-schemas.png)

   [Dialogové okno schémata XML](xml-schemas-dialog-box.md) otevře. Dialogové okno obsahuje všechna schémata pomocí. *xsd* rozšíření v mezipaměti schématu (včetně schémata odkazuje *catalog.xml* souboru) a také jakékoli schéma, které se v aktuálním řešení, otevřete v sadě Visual Studio, odkazuje v `xsd:schemaLocation` atribut, nebo odkazuje **schémata** vlastnost.

3. Výběr schémat pro účely ověření pomocí jedné z následujících akcí:

   - Vyberte schéma uvedené v **schémat XML** dialogového okna, klikněte na tlačítko **použití** sloupec a pak vyberte **použít tohle schéma**.

     -nebo-

   - Výběr více schémat, které jsou uvedeny v **schémat XML** dialogového okna a pak klikněte pravým tlačítkem a vyberte **použít tohle schéma**.

4. Zvolte **OK**.

   Seznam vybraná schémata zkopírována zpět **schémata** vlastnost dokumentu.

## <a name="to-add-an-xml-schema-to-the-schema-cache"></a>Přidat do mezipaměti schématu schématu XML

1. V okně Vlastnosti dokumentu, klepněte na tlačítko **schémata** pole.

2. Klikněte na **Přidat**.

   **Otevřít schéma XSD** otevře se dialogové okno.

3. Vyhledejte a vyberte schémata pro přidání do mezipaměti schématu.

4. Klikněte na tlačítko **otevřít**.

   Schémata jsou přidány do mezipaměti schématu a **použití** nastavena na hodnotu sloupce **použít tohle schéma**.

## <a name="to-delete-an-xml-schema-from-the-schema-cache"></a>Chcete-li odstranit schématu XML z mezipaměti schémat

1. V okně Vlastnosti dokumentu, klepněte na tlačítko **schémata** pole.

2. Vyberte schéma odebrat a potom klikněte na **odebrat**.

   Schéma se odebere z mezipaměti schémat v paměti, ale neodebere se ze systému souborů.

   > [!NOTE]
   > Pokud stále máte odkaz na schéma prostřednictvím `schemaLocation` atribut nebo odpovídající `targetNamespace` pak **odebrat** nebude fungovat v této situaci kvůli automatické přidružení. V tomto případě se doporučuje, abyste označili schématu jako **nepoužívat vybraná schémata** v **použít** sloupce.

## <a name="see-also"></a>Viz také:

- [Mezipaměti schémat](../xml-tools/schema-cache.md)
- [Dialogové okno schémata XML](../xml-tools/xml-schemas-dialog-box.md)
- [XML editor](../xml-tools/xml-editor.md)