---
title: Referenční dokumentace schématu 2,0 pro jazykové sady VSIX | Microsoft Docs
ms.date: 10/26/2017
ms.topic: conceptual
helpviewer_keywords:
- language pack
- localize vsix
- localize package
- localize extension
ms.assetid: 2a2932bc-cdbe-4d32-91fa-a3e0474f9098
ms.author: zorio
author: zoeyr
manager: jillfra
ms.openlocfilehash: fe6d4bd9e82950d77925dda1560b5c204633d392
ms.sourcegitcommit: dae5dfd626277b58ebd7b21a75757f683f1eacc5
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/06/2019
ms.locfileid: "70739334"
---
# <a name="vsix-language-pack-schema-20-reference"></a>Referenční dokumentace schématu 2,0 pro jazykové sady VSIX

Schéma jazykové sady VSIX poskytuje lokalizované informace o instalaci balíčků VSIX. Verze 2,0 tohoto schématu podporuje další prvky lokalizace.

## <a name="language-pack-schema"></a>Schéma jazykové sady

Kořenový prvek souboru jazykové sady je `<PackageLanguagePackManifest>`, s `Version`atributem, který je verze formátu jazykové sady. Tento článek popisuje verzi 2,0 formátu jazykové sady, která je zadána v manifestu, nastavením `Version` atributu na hodnotu. `Version="2.0.0"` Kořenový element obsahuje přesně jeden podřízený `<Metadata>` element.

### <a name="packagelanguagepackmanifest-element"></a>Element PackageLanguagePackManifest

V rámci `<PackageLanguagePackManifest>` elementu musí existovat následující element:

|Název|Popis|
|-----------|-----------------|
|`<Metadata>`| Nadřazený element pro všechna lokalizovaná metadata balíčku

### <a name="metadata-element"></a>Element metadata

V rámci `<Metadata>` elementu můžete mít následující prvky:

|Název|Popis|
|-----------|-----------------|
|`<DisplayName>`|Lokalizovaný název rozšíření, které se má nainstalovat|
|`<Description>`|Lokalizovaný popis rozšíření, které se má nainstalovat|
|`<License>`| Cesta k lokalizované verzi licence rozšíření|
|`<MoreInfo>`| Odkaz na lokalizované informace o rozšíření|
|`<ReleaseNotes>`| Cesta nebo odkaz na lokalizovanou verzi poznámky k verzi|
|`<Icon>`| Cesta k lokalizované verzi ikony rozšíření|

### <a name="sample-manifest"></a>Vzorový manifest

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
|[Lokalizace balíčků VSIX](../extensibility/localizing-vsix-packages.md)|Ukazuje, jak poskytnout lokalizovanou podporu instalace balíčku VSIX.|
|[Referenční dokumentace schématu rozšíření VSIX 2,0](../extensibility/vsix-extension-schema-2-0-reference.md)|Manifest VSIX popisuje obsah souboru nasazení *. vsix* . Soubor nasazení umožňuje nainstalovat rozšíření sady Visual Studio pomocí dialogového okna **rozšíření a aktualizace** .|
|[Vyhledání a používání rozšíření sady Visual Studio](../ide/finding-and-using-visual-studio-extensions.md)|Ukazuje, jak použít dialogové okno **rozšíření a aktualizace** k instalaci, odebrání, aktivaci a deaktivaci rozšíření.|
