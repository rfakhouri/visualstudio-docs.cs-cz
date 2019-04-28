---
title: Supportslanguagedropdown – Element (šablony sady Visual Studio) | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/vstemplate/2005#SupportsLanguageDropDown
helpviewer_keywords:
- SupportsLanguageDropDown element [Visual Studio Templates]
- <SupportsLanguageDropDown> element [Visual Studio Templates]
ms.assetid: 641197d5-f724-4c06-bc47-2e22dad3fbfb
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: f8f94036a20d6c1b6963b39aa3d2b13e17a6e256
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62799857"
---
# <a name="supportslanguagedropdown-element-visual-studio-templates"></a>SupportsLanguageDropDown – element (šablony sady Visual Studio)
Určuje, jestli je stejný jako pro řadu jazyků webové šablony položky a zda **jazyk** je zapnutá možnost **přidat novou položku** dialogové okno.

 \<Vstemplate – > \<TemplateData > \<supportslanguagedropdown – >

## <a name="syntax"></a>Syntaxe

```
<SupportsLanguageDropDown> true/false </SupportsLanguageDropDown>
```

## <a name="attributes-and-elements"></a>Atributy a elementy
 Následující oddíly popisují atributy a podřízené a nadřazené elementy.

### <a name="attributes"></a>Atributy
 Žádné

### <a name="child-elements"></a>Podřízené elementy
 Žádné

### <a name="parent-elements"></a>Nadřazené elementy

|Prvek|Popis|
|-------------|-----------------|
|[TemplateData](../extensibility/templatedata-element-visual-studio-templates.md)|Požadovaný element.<br /><br /> Rozděluje šablonu a definuje, jak se zobrazuje **nový projekt** nebo **přidat novou položku** dialogové okno.|

## <a name="text-value"></a>Textová hodnota
 Je vyžadována textová hodnota.

 Text musí být buď `true` nebo `false`, která udává, zda je či není **jazyk** možnost je k dispozici **přidat novou položku** dialogové okno.

## <a name="remarks"></a>Poznámky
 `SupportsLanguageDropDown` je volitelný prvek. Výchozí hodnota je `false`.

 `SupportsLanguageDropDown` Element je dostupná jenom pro webové šablony položek.

 Je nastavena na hodnotu pro tento element `true`, šablona položky je shodné pro všechny programovací jazyky a **jazyk** možnost je povolena **přidat novou položku** dialogové okno. Tato možnost umožní vám vybrat programovací jazyk nová položka, kterou chcete vytvořit ze šablony.

## <a name="example"></a>Příklad
 Následující příklad určuje zobrazíte **jazyk** rozevírací seznam možností.

```
<VSTemplate Version="3.0.0" Type="Project"
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">>
    <TemplateData>
        <Name>MyWebProjecStarterKit</Name>
        <Description>A simple Web template</Description>
        <Icon>icon.ico</Icon>
        <ProjectType>Web</ProjectType>
        <ProjectSubType>CSharp</ProjectSubType>
        <DefaultName>WebSite</DefaultName>
        <SupportsLanguageDropDown>true</SupportsLanguageDropDown>
    </TemplateData>
    <TemplateContent>
        <Project File="WebApplication.webproj">
            <ProjectItem>icon.ico</ProjectItem>
            <ProjectItem OpenInEditor="true">Default.aspx</ProjectItem>
            <ProjectItem>Default.aspx.cs</ProjectItem>
        </Project>
    </TemplateContent>
</VSTemplate>
```

## <a name="see-also"></a>Viz také
- [Odkaz na schéma šablon sady Visual Studio](../extensibility/visual-studio-template-schema-reference.md)
- [Vytváření šablon projektů a položek](../ide/creating-project-and-item-templates.md)