---
title: Mezipaměti schématu Editor XML
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-xml-tools
ms.topic: conceptual
ms.assetid: 35a7fcad-f3bf-4a96-9008-4306e7276223
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: cf3c41c16f904077f884bc6cffcdf0ba97233a1a
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/01/2018
ms.locfileid: "34572784"
---
# <a name="schema-cache"></a>Mezipaměti schématu

Nabízí XML Editor nachází v mezipaměti schématu *%InstallRoot%\Xml\Schemas* adresáře. Mezipaměti schématu je globální pro všechny uživatele ve vašem počítači a obsahuje standardní schémat XML, které se používají pro ověřování dokumentu IntelliSense a XML.

Editor souborů XML můžete také získat schémata umístěný v řešení, schémata zadaný v **schémata** pole dokumentu **vlastnosti** okno a schémata identifikovaný `xsi:schemaLocation` a `xsi:noNamespaceSchemaLocation`atributy.

Následující tabulka popisuje schémat, které jsou nainstalované pomocí editoru XML.

|Název souboru|Popis|
|--------------|-----------------|
|*CATALOG.xsd*|Schéma pro soubory katalogu schématu XML editor. Informace o katalogů schémat najdete níže.|
|*DotNetConfig.xsd*|Schéma pro soubory Web.Config "http://schemas.microsoft.com/.NETConfiguration/v2.0".|
|*MSBuild.xsd*|Schéma pro zpřístupnění souborů nástroje MSBuild, "http://schemas.microsoft.com/developer/msbuild/2003".|
|*MSDATA.xsd*|Schéma pro poznámky XSD přidal <xref:System.Data.DataSet> třída, "urn: schémata-microsoft-com: XML-msdata".|
|*msxsl.xsd*|Schéma pro rozšíření blok skriptu, Microsoft XSLT, urn: schémata-microsoft-com:xslt.|
|*SnippetFormat.xsd*|Schéma pro soubory XML fragment kódu. Příklady najdete v tématu *%InstallDir%\VC#\Expansions*.|
|*Soap1.1.xsd*|Schéma pro Simple Object Access Protocol (SOAP) 1.1, http://schemas.xmlsoap.org/soap/envelope/.|
|*Soap1.2.xsd*|Schéma pro Simple Object Access Protocol 1.2.|
|*SiteMapSchema.xsd*|Schéma pro soubor XML mapy webu ASP.NET, "http://schemas.microsoft.com/AspNet/SiteMap-File-1.0".|
|*WSDL.xsd*|Schéma pro Web Service Description Language http://schemas.xmlsoap.org/wsdl/.|
|*xenc.xsd*|Schéma XML – šifrování http://www.w3.org/2000/09/xmldsig#.|
|*XHTML.xsd*|Schéma pro XHTML http://www.w3.org/1999/xhtml.|
|*XLINK.xsd*|Schéma pro XLink1.0, http://www.w3.org/1999/xlink.|
|*XML.xsd*|XSD, popisující atributy XML: Space a XML: lang, http://www.w3.org/XML/1998/namespace.|
|*xmlsig.xsd*|Schéma XML – digitální podpisy, http://www.w3.org/2000/09/xmldsig#.|
|*xsdschema.xsd*|Schéma XSD, popisující http://www.w3.org/2001/XMLSchema.|
|*XSLT.xsd*|Schéma XML transformuje, http://www.w3.org/1999/XSL/Transform.|

## <a name="update-schemas-in-the-cache"></a>Aktualizovat schémata v mezipaměti
 Editor načte adresář mezipaměti schématu, když je načíst balíček editoru XML a sleduje změny při spuštění. Pokud schéma byly přidány, je automaticky načten do indexu v paměti známými schématy. Pokud schéma byla odebrána, automaticky se odebere z indexu v paměti. Pokud se schéma aktualizovalo, se automaticky zruší platnost mezipaměti v paměti Toto schéma.

> [!NOTE]
> Vzhledem k tomu, že adresář mezipaměti schématu globální do počítače, byste měli přidávat jenom zde schémat, které jsou standardní a užitečné všechny projektů sady Visual Studio, které mohou být vytvořeny ve vašem počítači.


 Editor souborů XML také podporuje libovolný počet schématu katalogu soubory v adresáři mezipaměti schématu. Katalogů schémat může ukazovat na jiné umístění pro schémat, které chcete, aby editoru seznámit. *Catalog.xsd* soubor definuje formát souboru katalogu a je zahrnutý v adresáři mezipaměti schématu. *Catalog.xml* soubor katalogu výchozí a obsahuje odkazy na další schémata v *InstallDir %*. Toto je vzorky *catalog.xml* souboru:

```xml
<SchemaCatalog xmlns="http://schemas.microsoft.com/xsd/catalog">
  <Schema href="%InstallDir%/help/schemas/Favorites.xsd" targetNamespace="urn:Favorites-Schema"/>
  <Schema href="%InstallDir%/help/schemas/Links.xsd" targetNamespace="urn:Links-Schema"/>
  <Schema href="%InstallDir%/help/schemas/MyHelp.xsd" targetNamespace="urn:VSHelp-Schema"/>
</SchemaCatalog>
```

 `href` Atribut může být jakékoli cesty nebo http adresa URL souboru odkazující na schéma. Cesta k souboru může být relativní vzhledem k dokumentu katalogu. Následující proměnné, oddělená %%, jsou rozpoznány pomocí editoru a rozbalí se v cestě:

-   InstallDir

-   Systém

-   ProgramFiles

-   Programy

-   CommonProgramFiles

-   ApplicationData

-   CommonApplicationData

-   LCID

Může zahrnovat dokumentu katalogu `Catalog` element, který odkazuje na jiné katalogů. Můžete použít `Catalog` element tak, aby odkazoval centrální katalog sdíleny váš tým nebo společnosti nebo online katalogu sdílet s obchodními partnery. `href` Atribut je soubor cestu nebo http adresa URL pro jiné katalogů. Tady je příklad `Catalog` element:

```xml
<Catalog href="file://c:/xcbl/xcblCatalog.xml"/>
```

 Katalog můžete také ovládat, jak schémata jsou spojené s dokumenty XML pomocí speciální `Association` elementu. Tento element přidruží schémat, které mají s konkrétní příponou, které mohou být užitečné, protože Editor souborů XML neprovádí žádné automatické přidružení schémat, které nemají žádné cílový obor názvů `targetNamespace` atribut. V následujícím příkladu `Association` element přidruží schéma dotNetConfig všechny soubory, které mají příponu souboru "konfigurace":

```xml
<Association extension="config" schema="%InstallDir%/xml/schemas/dotNetConfig.xsd"/>
```

## <a name="localized-schemas"></a>Lokalizované schémata
 V mnoha případech *catalog.xml* soubor neobsahuje položky pro lokalizované schémat. Můžete přidat další položky k *catalog.xml* soubor, který přejděte do adresáře lokalizované schématu.

 V následujícím příkladu a nové `Schema` byl vytvořen element, který používá proměnnou % LCID % tak, aby odkazoval na lokalizované schéma.

```xml
<Schema href="%InstallRoot%/Common7/IDE/Policy/Schemas/%LCID%/TDLSchema.xsd"
  targetNamespace="http://www.microsoft.com/schema/EnterpriseTemplates/TDLSchema"/>
```

## <a name="change-the-location-of-the-schema-cache"></a>Změna umístění mezipaměti schématu

Můžete přizpůsobit umístění mezipaměti schématu pomocí **různé** stránka Možnosti. Pokud máte adresáře Oblíbené schémat, lze nakonfigurovat editoru místo toho použít tyto schémat.

> [!NOTE]
> Tato změna ovlivňuje pouze aktuální uživatel Visual Studio.

### <a name="to-change-the-schema-cache-location"></a>Chcete-li změnit umístění mezipaměti schématu

1.  Z **nástroje** nabídce vyberte možnost **možnosti**.

2.  Rozbalte položku **textového editoru**, rozbalte položku **XML**a potom klikněte na **různé**.

3.  Klikněte **Procházet** na tlačítko **schémata** pole.

4.  Vyberte složku pro ukládání do mezipaměti schématu a klikněte na tlačítko **OK**.

### <a name="to-add-another-directory-of-common-schemas"></a>Chcete-li přidat jiného adresáře běžné schémat.

1.  Upravit *catalog.xml* soubor v adresáři mezipaměti schématu XML editor.

2.  Přidejte nový `<Catalog href="..."/>` element, který odkazuje na adresář, další schémat.

3.  Uložte provedené změny.

     Katalog je automaticky znovu.

## <a name="see-also"></a>Viz také:

- [Editor XML](../xml-tools/xml-editor.md)