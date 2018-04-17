---
title: VSIX Language Pack schéma 2.0 – referenční informace | Microsoft Docs
ms.custom: ''
ms.date: 10/26/2017
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- language pack
- localize vsix
- localize package
- localize extension
ms.assetid: 2a2932bc-cdbe-4d32-91fa-a3e0474f9098
ms.author: dagriffe
author: dgriffen
manager: douge
ms.workload:
- dagriffe
ms.openlocfilehash: 571f90f31014dcc4d5686483bfc037e458f4a31e
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="vsix-language-pack-schema-20-reference"></a>VSIX Language Pack schéma 2.0 – referenční informace

Schéma VSIX jazyková sada obsahuje lokalizované instalace informace o VSIX balíčky. Verze 2.0 toto schéma podporuje další lokalizace elementů.

## <a name="language-pack-schema"></a>Schéma Language Pack

Kořenový element souboru language pack `<PackageLanguagePackManifest>`, s atributem `Version`, což je verzi formátu language pack. Toto téma popisuje verze 2.0 language pack formátu, který je určený v manifestu nastavení `Version` atributu na hodnotu `Version="2.0.0"`. Kořenový element obsahuje přesně jednu podřízenou `<Metadata>` elementu.

### <a name="packagelangaugepackmanifest-element"></a>PackageLangaugePackManifest Element

V rámci `<PackageLanguagePackManifest>` elementu následující element musí být:
|Název|Popis|
|-----------|-----------------|
|`<Metadata>`| Element obsahující pro všechna metadata lokalizované balíčku

### <a name="metadata-element"></a>Metadata – Element

V rámci `<Metadata>` element může mít následující prvky:
|Název|Popis|
|-----------|-----------------|
|`<DisplayName>`|Lokalizovaný název rozšíření k instalaci|
|`<Description>`|Lokalizovaný popis rozšíření k instalaci|
|`<License>`| Cesta k lokalizovanou verzi rozšíření licence|
|`<MoreInfo>`| Odkaz na lokalizované informace o rozšíření|
|`<ReleaseNotes>`| Cesta nebo odkaz na lokalizované verzi poznámky k verzi|
|`<Icon>`| Cesta k lokalizované verzi ikonu rozšíření|

### <a name="sample-manifest"></a>Ukázka manifestu

```xml
<?xml version="1.0" encoding="utf-8"?>
<PackageLanguagePackManifest Version="2.0.0" xmlns="http://schemas.microsoft.com/developer/vsx-schema/2011">
  <Metadata>
    <DisplayName>Arbol de Familia</LocalizedName>
    <Description> Esta extensión pone control personalizado en la caja de herramientas por manejar información de familia.</Description>
    <MoreInfo> http://www.contoso.com/products/es/ArbolDeFamilia.htm</MoreInfo>
    <License>Eula.rtf</License>
    <ReleaseNotes>ReleaseNotes.rtf</ReleaseNotes>
    <Icon>Icon.png</Icon>
  </Metadata>
</PackageLanguagePackManifest>
```

## <a name="see-also"></a>Viz také

|Název|Popis|
|-----------|-----------------|
|[Lokalizace balíčků VSIX](../extensibility/localizing-vsix-packages.md)|Ukazuje, jak k podpoře lokalizovaného instalačního balíčku VSIX.|
|[VSIX Extension Schema 2.0 – referenční informace](../extensibility/vsix-extension-schema-2-0-reference.md)|VSIX manifest popisuje obsah soubor nasazení VSIX, který umožňuje rozšíření sady Visual Studio k instalaci pomocí **rozšíření a aktualizace** dialogové okno.|
|[Hledání a používání rozšíření sady Visual Studio](../ide/finding-and-using-visual-studio-extensions.md)|Ukazuje, jak používat **rozšíření a aktualizace** dialogové okno k instalaci, odebrání, aktivovat a deaktivovat rozšíření.|