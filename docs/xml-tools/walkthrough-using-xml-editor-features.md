---
title: 'Průvodce: Používání funkcí editoru XML'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: conceptual
ms.assetid: ea8dc357-2e66-455a-aec2-7ccaccfc9adf
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 524b96fea7fedba248c04f384445ee3a03a3595b
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53902003"
---
# <a name="walkthrough-use-xml-editor-features"></a>Průvodce: Použití funkce editoru XML

Kroky v tomto názorném postupu ukazují, jak vytvořit nový dokument XML. Průvodce také používá některé funkce v editoru XML, které jí umožňují velmi cennou pomůckou pro vytváření XML.

> [!NOTE]
> Před zahájením návodu, uložte *hireDate.xsd* souboru (uvedené níže v tomto tématu) do místního počítače.

## <a name="to-create-a-new-xml-file-and-associate-it-with-an-xml-schema"></a>Vytvořte nový soubor XML a přidružte jej k schématu XML

1.  Na **souboru** nabídky, přejděte k **nový**a klikněte na tlačítko **souboru**.

2.  Vyberte **soubor XML** v **šablony** podokně a klepněte na **otevřít**.

     Nový soubor je otevřen v editoru. Tento soubor obsahuje deklaraci XML výchozí `<?xml version="1.0" encoding="utf-8">`.

3.  V okně Vlastnosti dokumentu, klikněte na tlačítko Procházet (**...** ) na **schémata** pole.

     **Schémata XSD** se zobrazí dialogové okno.

4.  Klikněte na **Přidat**.

     **Otevřít schéma XSD** se zobrazí dialogové okno.

5.  Vyberte *hireDate.xsd* souboru a klikněte na tlačítko **otevřít**.

6.  Klikněte na **OK**.

     Schéma XML je teď přidružený k dokumentu XML. Schématu XML se používá k ověření dokumentu. Také se používá technologii IntelliSense k naplnění seznamu členů platné prvky.

## <a name="to-add-data"></a>Chcete-li přidat data

1.  Typ `<` podokna editoru.

     Seznam členů obsahuje položky, je to možné:

    -   **! –** a přidejte komentář.

    -   **! Typ dokumentu** přidat typ dokumentu.

    -   **?** Chcete-li přidat instrukce pro zpracování.

    -   **Zaměstnanec** přidat kořenový element.

2.  Vyberte **<!--** přidat uzel komentáře a stiskněte klávesu **Enter**.

     Editor vloží koncová značka komentáře a umístí kurzor mezi počáteční a koncové značky pro komentáře.

3.  Zadejte **soubor Test XML**.

4.  Na nový řádek, zadejte `<`a vyberte **zaměstnance** ze seznamu členů.

     Editor přidá na začátek elementu XML `<employee`. V tomto okamžiku můžete přidat atributy pro element nebo můžete zavřít počáteční značce zadáním `>`.

5.  Typ `>` zavřete značky.

6.  Editor přidá koncová značka. Koncová značka se přidá s podtržení vlnovkou udávající chybu ověřování. **Popisek** zobrazí zprávu: **Element 'zaměstnance' má neúplný obsah. Byl očekáván 'ID'**.

7.  Typ `<` a vyberte **ID** ze seznamu členů. Zadejte `>`.

     Přidá XML element editor `<ID></ID>`a umístí kurzor po ID počáteční značka.

8.  Typ **abc**.

     **Abc** text obsahuje podtržení vlnovkou. **Popisek** zobrazí zprávu: **Element 'ID' má neplatnou hodnotu vzhledem k jeho datovému typu**.

9. Klikněte pravým tlačítkem na ID elementu a vyberte **přejít k definici**.

     Otevře se editor *hireDate.xsd* souboru v novém okně dokumentu a umístí kurzor na definici schématu element ID.

10. Vraťte se do souboru XML a nahraďte **abc** text s **123**.

     Podtržení vlnovkou a **popisek** jsou vymazány pod hodnotou element ID. **Popisek** pro zaměstnance koncové značky nyní zobrazí zprávu: **Element 'zaměstnance' má neúplný obsah. Byl očekáván "datum přijetí"**.

11. Umístěte kurzor po ID koncovou značku, zadejte v `<`vyberte **datum přijetí** seznam členů a pak zadejte `>`.

     Přidá XML element editor `<hire-date></hire-date>`a umístí kurzor po datum přijetí počáteční značka.

12. Zadejte **2003-01-10** pro hodnotu Datum přijetí.

## <a name="to-format-the-xml-document"></a>Formát dokumentu XML

- Vyberte **formátovat dokument** tlačítko na panelu nástrojů editoru XML.

    Dokument XML je přeformátovali.

## <a name="to-save-the-xml-document"></a>Uložení dokumentu XML

1.  Z **souboru** nabídce vyberte možnost **uložit jako**.

     **Uložit soubor jako** se zobrazí dialogové okno. Výchozí název souboru je *"XMLFile1"*.

2.  Zadejte název souboru a umístění dokumentu XML a klikněte na tlačítko **Uložit**.

## <a name="hiredatexsd-file"></a>soubor hireDate.xsd
 Následující soubor schématu je používán návodu.

```xml
<?xml version="1.0"?>
<xs:schema attributeFormDefault="unqualified"
     elementFormDefault="qualified" targetNamespace="urn:empl-hire"
     xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:element name="employee">
    <xs:complexType>
      <xs:sequence>
        <xs:element name="ID" type="xs:unsignedShort" />
        <xs:element name="hire-date" type="xs:date" />
      </xs:sequence>
    </xs:complexType>
  </xs:element>
</xs:schema>
```

## <a name="see-also"></a>Viz také:

- [Editor XML](../xml-tools/xml-editor.md)