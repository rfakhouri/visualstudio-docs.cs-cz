---
title: Funkce IntelliSense Editor XML
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-xml-tools
ms.topic: conceptual
ms.assetid: 2b26f214-cc3a-46bf-b260-14eb8e599182
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 82d05e481d313a7ba9010fe253756d3f21c345e2
ms.sourcegitcommit: d1824ab926ebbc4a8057163e0edeaf35cec57433
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/24/2018
ms.locfileid: "34476843"
---
# <a name="xml-editor-intellisense-features"></a>Funkce editoru XML IntelliSense

Editor souborů XML poskytuje úplné funkce IntelliSense srovnatelná jiné editory jazyk zadaný v sadě Visual Studio. Tato část vysvětluje, jak můžete používat IntelliSense s jazyk definice schématu XML (XSD) a XSLT dokumenty.

## <a name="intellisense-in-an-xsd-document"></a>IntelliSense v dokument XSD
 Po schéma je přidružen dokumentu, můžete získat rozevíracího seznamu elementů očekávané vždy, když zadáte `"<"` nebo klikněte na tlačítko **zobrazit seznam členů k objektu** tlačítka na panelu nástrojů editoru XML. Informace o tom, jak přidružit schémat XML dokumentů najdete v tématu [ověření dokumentu XML](../xml-tools/xml-document-validation.md).

 Když zadáte místo z uvnitř úvodní značky, získáte také rozevíracího seznamu zobrazuje všechny atributy, které mohou být přidány do aktuálního elementu.

 Pokud zadáte `"="` pro hodnotu atributu nebo otevření nabídky pro hodnotu, můžete také získat seznamu možných hodnot pro tento atribut. Hodnoty jsou zadáváno, pouze pokud je schéma poskytuje výčtové hodnoty prostřednictvím `xsd:enumeration` omezující, nebo pokud je atribut `Boolean` typu. Seznam známých jazyk kódu technologie IntelliSense, jsou tu taky pro `xml:lang` nebo jakoukoli `simpleType` která je odvozena od `xsd:language`. Seznam IntelliSense známé `targetNamespace` poskytuje hodnoty pro deklarace oboru názvů.

 Seznam IntelliSense možné hodnoty jsou tu taky když zadáte `">"` zavřete úvodní značky, pokud se element nachází `simpleType`. Chování pro elementy je podobně jako u chování pro atributy, které jsou popsané v předchozím odstavci.

 Popisy tlačítek se zobrazí také v seznamy IntelliSense na základě `xsd:annotation` a `xsd:documentation` informace najdete v přidružené schéma.

## <a name="intellisense-in-an-xslt-document"></a>IntelliSense v dokument XSLT
 Po přidání atribut s názvem šablony nebo do dokumentu XSLT, můžete IntelliSense vložte následující:

-   Atribut nastavit názvy.

-   Režimy šablony.

-   Názvy šablon.

-   Názvy parametrů pro danou režim.

-   Názvy parametrů pro danou šablonu s názvem.

Další informace najdete v tématu [návod: použití IntelliSense XSLT](../xml-tools/walkthrough-using-xslt-intellisense.md) tématu.

## <a name="auto-completion"></a>Automatické dokončování
 Editor souborů XML také umožňuje úpravy XML jednodušší vyplněním požadované syntaxe jazyka XML pro vás. Pokud například zadáte následující počáteční značku:

 `<book>`

 Editor souborů XML vyplní koncová značka a umisťuje kurzor po počáteční značku. Tady je příklad toho ("&#124;" poznámky k pozice kurzoru):

 `<book>`&#124;`</book>`

 Vzhledem k tomu, že hodnoty atributu musí mít vždy uvozovky, budou v editoru XML uvozovky vyplní automaticky. Například zadejte následující příkaz:

 `<book title=`

 Editor souborů XML přidá uvozovky a umisťuje kurzoru mezi uvozovky:

 `<book title="`&#124;`"`

 Podobně editor souborů XML také vloží syntaxi XML automaticky za vás:

-   Konec zpracování instrukcí:  `?>`

-   Koncový blok CDATA: `]]>`

-   Konec komentář: `-->`

-   Konec souboru DTD protokolu deklarace: `>`

Editor souborů XML má také možnost Vložit obor názvů deklarace, pokud vyberete na obor názvů kvalifikovaný element nebo atribut z seznam technologie IntelliSense a obor názvů pro tento element nebo atribut není ještě v oboru.

Například, pokud jste vybrali `e:Book` element ze seznamu IntelliSense, kde předpona, která je vázána `http://books` obor názvů, který nebyl deklarován v dokumentu, editor souborů XML vloží deklaraci oboru názvů požadované pro vás. Toto je výsledný textu XML:

`<e:Book xmlns:e="http://books"`

## <a name="brace-matching"></a>Související závorky
 Nabízí XML editor tak, abyste získali okamžitou zpětnou vazbu na prvky, které jste právě zavřeli zvýraznění závorek. Můžete také použít klávesové zkratky (**Ctrl**+**]**) na přechod z jednoho závorek do odpovídajících složených závorek.

 Editor souborů XML k tomu pro následující položky:

-   Odpovídající počáteční a koncové značky.

-   Všechny dvojice "\<" nebo ">" lomené závorky.

-   Počáteční a koncové komentáře.

-   Začátek a konec pokynů pro zpracování.

-   Počáteční a koncové CDATA bloků.

-   Počáteční a koncové DTD deklarace.

-   Otvírání a zavírání uvozovky u atributů.

## <a name="modify-the-intellisense-options"></a>Změnit možnosti IntelliSense
 Ve výchozím nastavení jsou povoleny funkce IntelliSense a automatické dokončování. Ale toto můžete změnit úpravou vaše **nástroje** > **možnosti** nastavení.

 **Automaticky vložit** části **různé** stránky řídí následující chování:

|Název|Popis|
|----------|-----------------|
|Zavřít značky|Vloží zavřete značky pro nové prvky.|
|Atribut uvozovky|Vloží uvozovky u hodnot atributů, když zadáte nový název atributu.|
|Další kód|Dokončení komentáře, CDATA, DOCTYPE, pokyny pro zpracování a dalších deklarací značek.|

### <a name="to-change-the-auto-completion-behavior"></a>Chcete-li změnit nastavení automatického dokončování

1.  Vyberte **možnosti** z **nástroje** nabídky.

2.  Rozbalte položku **textového editoru**, rozbalte položku **XML**a vyberte **různé**.

3.  Provádění jakýchkoli změn **automatické vkládání** části a klikněte na tlačítko **OK**.

## <a name="see-also"></a>Viz také

- [XML editor](../xml-tools/xml-editor.md)
- [Používání atributu IntelliSense](../ide/using-intellisense.md)
- [Návod: Používání IntelliSense XSLT](../xml-tools/walkthrough-using-xslt-intellisense.md)