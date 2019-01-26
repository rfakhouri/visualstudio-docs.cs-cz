---
title: VSIX Language Pack Schema 2.0 – referenční informace | Dokumentace Microsoftu
ms.date: 10/26/2017
ms.topic: conceptual
helpviewer_keywords:
- language pack
- localize vsix
- localize package
- localize extension
ms.assetid: 2a2932bc-cdbe-4d32-91fa-a3e0474f9098
ms.author: dagriffe
author: dgriffen
manager: jillfra
ms.workload:
- dagriffe
ms.openlocfilehash: f145b1fe8c8209e9b86ec1546f7079ec4317144a
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54969519"
---
# <a name="vsix-language-pack-schema-20-reference"></a>VSIX language pack schema 2.0 – referenční informace

Schéma VSIX Language Pack obsahuje lokalizovaného instalačního pro balíčky VSIX. Verze 2.0 tato schématu podporuje další lokalizace elementů.

## <a name="language-pack-schema"></a>Schéma language pack

Kořenový element souboru language pack je `<PackageLanguagePackManifest>`, s atributem `Version`, což je verze formátu language pack. Tento článek popisuje, verze 2.0 pack formátu jazyka, který je určený v manifestu tak, že nastavíte `Version` atributu na hodnotu `Version="2.0.0"`. Kořenový element obsahuje přesně jednu podřízenou `<Metadata>` elementu.

### <a name="packagelanguagepackmanifest-element"></a>PackageLanguagePackManifest – element

V rámci `<PackageLanguagePackManifest>` element musí existovat následující element:

|Název|Popis|
|-----------|-----------------|
|`<Metadata>`| Obsahující element pro všechna metadata lokalizovaných balíčků

### <a name="metadata-element"></a>Metadata – element

V rámci `<Metadata>` prvek může mít následující prvky:

|Název|Popis|
|-----------|-----------------|
|`<DisplayName>`|Lokalizovaný název rozšíření k instalaci|
|`<Description>`|Lokalizovaný popis rozšíření k instalaci|
|`<License>`| Cesta k lokalizovanou verzi licenci rozšíření|
|`<MoreInfo>`| Odkaz na lokalizované informace o rozšíření|
|`<ReleaseNotes>`| Cesta nebo odkaz na lokalizované verzi zpráva k vydání verze|
|`<Icon>`| Cesta k lokalizovanou verzi ikonu rozšíření|

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

## <a name="see-also"></a>Viz také:

|Název|Popis|
|-----------|-----------------|
|[Lokalizace balíčků VSIX](../extensibility/localizing-vsix-packages.md)|Ukazuje, jak poskytnout podporu lokalizovaného instalačního balíčku VSIX.|
|[VSIX extension schema 2.0 – referenční informace](../extensibility/vsix-extension-schema-2-0-reference.md)|VSIX manifest popisuje obsah *VSIX* souboru nasazení. Nasazení souboru umožňuje nainstalovat rozšíření sady Visual Studio s použitím **rozšíření a aktualizace** dialogové okno.|
|[Vyhledání a používání rozšíření sady Visual Studio](../ide/finding-and-using-visual-studio-extensions.md)|Ukazuje způsob použití **rozšíření a aktualizace** dialogové okno instalace, odebrání, aktivovat a deaktivovat rozšíření.|