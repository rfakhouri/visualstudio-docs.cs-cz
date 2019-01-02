---
title: 'Postupy: Generování fragmentu XML ze schématu XML'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: conceptual
ms.assetid: 2c128d2a-aaa6-4814-aa95-e07056afe338
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 31e1805a38d51315c4f0753f363334d1df37ece6
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53864715"
---
# <a name="how-to-generate-an-xml-snippet-from-an-xml-schema"></a>Postupy: Generování fragmentu XML ze schématu XML

XML Editor má schopnost generovat fragmentů XML ze schématu XML definice jazyk (XSD) schématu. Například při vytváření souboru XML, zatímco umístěný vedle názvu elementu, stisknutí klávesy **kartu** k naplnění element s daty XML generované informace o schématu pro daný element.

Tato funkce dostupná pouze na prvky. Také platí následující pravidla:

-   Element musí mít typ přidružené schéma; To znamená, že element musí být platná pro některé přidružené schéma. Typ schématu nemůže být abstraktní a typu musí obsahovat povinné atributy a/nebo požadované podřízené prvky.

-   Aktuální element v editoru musí být prázdný s žádné atributy. Například následující jsou všechny platné

    -   `<Account`

    -   `<Account>`

    -   `<Account></Account>`

-   Kurzor musí být umístěné bezprostředně napravo od názvu elementu.

Vygenerovaný fragment kódu obsahuje všechny povinné atributy a prvky. Pokud `minOccurs` je větší než jedna minimální požadovaný počet instancí tohoto prvku je zahrnuta v tomto fragmentu kódu až do maximálního počtu 100 instancí. Všechny pevné hodnoty nalezené v výsledek schématu v pevné hodnoty v tomto fragmentu kódu. `xsd:any` a `xsd:anyAttribute` prvky jsou ignorovány a mít za následek konstrukty žádný další fragment kódu.

Výchozí hodnoty jsou generovány a jsou uvedené jako upravitelné hodnoty. Pokud schéma určí výchozí hodnotu, tato výchozí hodnota se používá. Nicméně pokud schéma výchozí hodnota je prázdný řetězec, editoru generuje výchozí hodnoty následujícím způsobem:

-   Pokud typ schématu obsahuje všechny omezující vlastnosti výčtu přímo nebo nepřímo prostřednictvím žádné členy typu sjednocení, první Výčtový hodnotu nalezenou v modelu objektu schématu se používá jako výchozí.

-   Pokud je Atomický typ je typ schématu, editor získá Atomický typ a vloží název Atomický typ. Odvozené jednoduchý typ používá základní jednoduchého typu. Pro typ seznamu je Atomický typ `itemType`. Pro sjednocení, Atomický typ je Atomický typ prvního `memberType`.

## <a name="example"></a>Příklad

 Kroky v této části ukazují, jak funkci generované schématu XML fragmentu kódu v editoru XML.

> [!NOTE]
> Než zahájíte tyto postupy, uložte soubor schématu do místního počítače.

### <a name="to-create-a-new-xml-file-and-associate-it-with-an-xml-schema"></a>Vytvořte nový soubor XML a přidružte jej k schématu XML

1.  Na **souboru** nabídky, přejděte k **nový**a klikněte na tlačítko **souboru**.

2.  Vyberte **soubor XML** v **šablony** podokně a klepněte na **otevřít**.

     Nový soubor je otevřen v editoru. Tento soubor obsahuje deklaraci XML výchozí `<?xml version="1.0" encoding="utf-8">`.

3.  V okně Vlastnosti dokumentu, klikněte na tlačítko Procházet (**...** ) na **schémata** pole.

     **Schémata XSD** se zobrazí dialogové okno.

4.  Klikněte na **Přidat**.

     **Otevřít schéma XSD** se zobrazí dialogové okno.

5.  Vyberte soubor schématu a klikněte na tlačítko **otevřít**.

6.  Klikněte na **OK**.

     Schéma XML je teď přidružený k dokumentu XML.

### <a name="to-generate-an-xml-snippet"></a>Ke generování fragmentu XML

1.  Typ `<` podokna editoru.

2.  Seznam členů obsahuje položky, je to možné:

     **! –** a přidejte komentář.

     **! Typ dokumentu** přidat typ dokumentu.

     **?** Chcete-li přidat instrukce pro zpracování.

     **Kontakt** přidat kořenový element.

3.  Vyberte **kontakt** ze seznamu členů a stiskněte klávesu **Enter**.

     Editor přidá počáteční značce `<Contact` a umístí kurzor po názvu elementu.

4.  Stisknutím klávesy **kartu** generují data XML pro `Contact` element podle jeho informace o schématu.

## <a name="input"></a>Vstup

 Následující soubor schématu je používán návodu.

```xml
<?xml version="1.0" encoding="utf-8" ?>
<xs:schema elementFormDefault="qualified"
           xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:simpleType name="phoneType">
    <xs:restriction base="xs:string">
      <xs:enumeration value="Voice"/>
      <xs:enumeration value="Fax"/>
      <xs:enumeration value="Pager"/>
    </xs:restriction>
  </xs:simpleType>
  <xs:element name="Contact">
    <xs:complexType>
      <xs:sequence>
        <xs:element name="Name">
          <xs:simpleType>
            <xs:restriction base="xs:string"></xs:restriction>
          </xs:simpleType>
        </xs:element>
        <xs:element name="Title"
                    type="xs:string" />
        <xs:element name="Phone"
                    minOccurs="1"
                    maxOccurs="unbounded">
          <xs:complexType>
            <xs:sequence>
              <xs:element name="Number"
                          minOccurs="1">
                <xs:simpleType>
                  <xs:restriction base="xs:string"></xs:restriction>
                </xs:simpleType>
              </xs:element>
              <xs:element name="Type"
                          default="Voice"
                          minOccurs="1"
                          type="phoneType"/>
            </xs:sequence>
          </xs:complexType>
        </xs:element>
      </xs:sequence>
    </xs:complexType>
  </xs:element>
</xs:schema>
```

### <a name="output"></a>Výstup

 Tady je data XML, který je generován podle informací o schématu přidružené k `Contact` elementu. Položky označené jako `bold` určit upravitelná pole v tomto fragmentu kódu XML.

```xml
<Contact>
  <Name>name</Name>
  <Title>title</Title>
  <Phone>
    <Number>number</Number>
    <Type>Voice</Type>
  </Phone>
</Contact>
```

## <a name="see-also"></a>Viz také:

- [Fragmentů XML](../xml-tools/xml-snippets.md)
- [Postupy: Použití fragmentů XML](../xml-tools/how-to-use-xml-snippets.md)