---
title: Lokalizace VSIX balíčky | Microsoft Docs
ms.custom: ''
ms.date: 10/26/2017
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- localize package
- localize extension
- localized deployment
ms.assetid: 10e80b13-b39e-466c-a7c8-774a862355af
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: d94e390374ca2eb77b4332b3a5c253acce69f051
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="localizing-vsix-packages"></a>Lokalizace balíčků VSIX

Vytvoření souboru Extension.vsixlangpack pro každý jazyk cíl a jejich uvádění ve správné složce, je možné lokalizovat balíčku VSIX. Po nainstalování lokalizované balíčku, zobrazí se společně s lokalizovaný popis lokalizovaný název rozšíření. Pokud zadáte lokalizované licenční soubor nebo adresa URL, která odkazuje na lokalizované informace, se také zobrazí.

Pokud obsah obsahuje vašeho balíčku VSIX VSPackage, který přidá příkazy nabídky nebo jiné uživatelského rozhraní, najdete v části [lokalizace příkazy nabídky](../extensibility/localizing-menu-commands.md) informace o lokalizaci nové prvky uživatelského rozhraní.

## <a name="directory-structure"></a>Struktura adresářů

 Pokud uživatel nainstaluje rozšíření, **rozšíření a aktualizace** kontroluje nejvyšší úrovni balíčku VSIX pro složku, jejíž název odpovídá národní prostředí sady Visual Studio cílového počítače. Pokud **rozšíření a aktualizace** najde-li .vsixlangpack souboru ve složce, nahrazuje lokalizované hodnoty v tomto souboru pro odpovídající hodnoty v souboru .vsixmanifest. Při instalaci rozšíření, zobrazí se tyto hodnoty. Následující příklad ukazuje strukturu adresáře balíčku VSIX lokalizovanou do Španělština (es-ES) a Francouzština (fr-FR).  

```text
.
├── MyExtension.dll
├── Extension.vsixmanifest
├── [Content_Types].xml
├── es-ES
│   └── Extension.vsixlangpack
└── fr-FR
    └── Extension.vsixlangpack
```

> [!NOTE]
> Šablony projektu VSIX podporované v [!INCLUDE[vsipsdk](../extensibility/includes/vsipsdk_md.md)] generování manifestu VSIX a pojmenujte ji source.extension.vsixmanifest. Když Visual Studio vytvoří projekt, zkopíruje obsah tohoto souboru do Extension.VsixManifest v balíčku VSIX.

## <a name="the-extensionvsixlangpack-file"></a>Soubor Extension.vsixlangpack

Soubor Extension.vsixlangpack odpovídá [VSIX Language Pack schématu 2.0](../extensibility/vsix-language-pack-schema-2-0-reference.md). Toto schéma `PackageLanguagePackManifest`, který je bezprostředně následované `Metadata` podřízený element. Metadata element může obsahovat až 6 podřízené elementy `DisplayName`, `Description`, `MoreInfo`, `License`, `ReleaseNotes`, a `Icon`. Tyto podřízené elementy odpovídají `DisplayName`, `Description`, `MoreInfo`, `License`, `ReleaseNotes`, a `Icon` podřízených elementů `Metadata` prvek Extension.vsixmanifest souboru.

Když vytvoříte soubor vsixlangpack, musíte nastavit `Include in Vsix` vlastnost `true`. Text lokalizovaného instalačního, jinak budou ignorovány.

### <a name="to-set-the-include-in-vsix-property"></a>Chcete-li nastavit zahrnout ve vlastnosti Vsix

1. V **Průzkumníku řešení**, klikněte pravým tlačítkem na soubor Extension.vsixlangpack a pak klikněte na tlačítko **vlastnosti**.

2.  V tabulce vlastností klikněte na tlačítko **zahrnout do Vsix**a jeho hodnotu nastavte `true`.

## <a name="example"></a>Příklad

### <a name="description"></a>Popis

Následující příklad ukazuje odpovídající části souboru Extension.vsixmanifest společně s odpovídající soubor Extension.vsixlangpack pro španělštinu. Pokud národní prostředí sady Visual Studio na cílovém počítači nastavená španělština, nahradí hodnoty z jazyková sada hodnoty z manifestu.

### <a name="code"></a>Kód

 [Extension.vsixmanifest]

```xml
<?xml version="1.0" encoding="utf-8"?>
<PackageManifest ...>
  <Metadata ...>
    <DisplayName>Family Tree</DisplayName>
    <Description>This extension places a custom treeview control in the toolbox that is optimized for handling family tree information.</Description>
    <MoreInfo>http://www.contoso.com/products/FamilyTree.htm</MoreInfo>
    <License>Eula.rtf</License>
    <ReleaseNotes>ReleaseNotes.rtf</ReleaseNotes>
    <Icon>Icon.png</Icon>
  </Metadata>
  <Installation .../>
  <Dependencies .../>
  <Prerequisites .../>
  <Assets .../>
</PackageManifest>
```

 [Extension.vsixlangpack]

```xml
<?xml version="1.0" encoding="utf-8"?>
<PackageLanguagePackManifest Version="2.0.0" xmlns="http://schemas.microsoft.com/developer/vsx-schema/2011">
  <Metadata>
    <DisplayName>Arbol de Familia</DisplayName>
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
|[VSIX LanguagePack schéma 2.0 – referenční informace](../extensibility/vsixlanguagepack-element-vsix-language-pack-schema.md)|Jazyková sada VSIX popisuje informace o lokalizaci VSIX souboru nasazení.|
|[Anatomie balíčku VSIX](../extensibility/anatomy-of-a-vsix-package.md)|Popisuje strukturu a obsah balíčku vsix.|
|[Lokalizace příkazů nabídky](../extensibility/localizing-menu-commands.md)|Ukazuje, jak k lokalizaci další prostředky textu v rozšíření.|