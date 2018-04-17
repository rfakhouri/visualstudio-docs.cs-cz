---
title: Maxframeworkversion – Element (šablony sady Visual Studio) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- <MaxFrameworkVersion> Element (Visual Studio Templates)
- MaxFrameworkVersion Element (Visual Studio Templates)
ms.assetid: f732a9d3-fc29-405b-9298-01ea83fc58b8
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 4bc28fcc35a4a59852ef6864886acff4dc87ef60
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="maxframeworkversion-element-visual-studio-templates"></a>MaxFrameworkVersion – element (šablony sady Visual Studio)

Určuje maximální verze rozhraní .NET Framework, který je požadován pro šablonu. Určuje nejvyšší hodnotu, která je k dispozici v **cílová verze Framework** rozevírací z **nový projekt** dialogové okno. Aby uživatelé mohli vybrat framework verzi, musíte také zadat [RequiredFrameworkVersion](../extensibility/requiredframeworkversion-element-visual-studio-templates.md) jako minimální verze rozhraní .NET Framework pro šablonu.

> [!IMPORTANT]
> Od verze Visual Studio 2017 verze 15,6 operací, **cílová verze Framework** rozevírací již není filtr pro zobrazený šablony v **šablony** části **nový projekt** dialogové okno. Místo toho **cílová verze Framework** rozevírací funguje jako výběr framework pro vybranou šablonu.

 \<VSTemplate > \<TemplateData > \<maxframeworkversion – >

## <a name="syntax"></a>Syntaxe

```xml
<MaxFrameworkVersion> ... </MaxFrameworkVersion>
```

## <a name="attributes-and-elements"></a>Atributy a elementy
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.

### <a name="attributes"></a>Atributy
 Žádné

### <a name="child-elements"></a>Podřízené elementy
 Žádné

### <a name="parent-elements"></a>Nadřazené elementy

|Prvek|Popis|
|-------------|-----------------|
|[TemplateData](../extensibility/templatedata-element-visual-studio-templates.md)|Požadovaný element.<br /><br /> Rozděluje šablonu a definuje, jak se zobrazí ve buď **nový projekt** nebo **přidat novou položku** dialogové okno.|

## <a name="text-value"></a>Textová hodnota
 Je vyžadována textová hodnota.

 Text musí být nejvyšší číslo verze rozhraní .NET Framework, který je povolen šablonou.

## <a name="remarks"></a>Poznámky

`MaxFrameworkVersion` je volitelný element. `MaxFrameworkVersion` Element by tento parametr vynechán, pokud není nutné, aby omezit nechtěně podporovaný rozsah rozhraní .NET Framework verze šablony. Musí být také vynechána, pokud je rozhraní .NET Framework se nevztahuje na šabloně.

## <a name="example"></a>Příklad

Následující příklad ilustruje metadata pro standardní [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] šablona třídy.

```xml
<VSTemplate Type="Item" Version="3.0.0"
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">
    <TemplateData>
        <Name>MyClass</Name>
        <Description>My custom C# class template.</Description>
        <Icon>Icon.ico</Icon>
        <ProjectType>CSharp</ProjectType>
        <RequiredFrameworkVersion>3.0</RequiredFrameworkVersion>
        <MaxFrameworkVersion>4.7.1</MaxFrameworkVersion>
        <DefaultName>MyClass</DefaultName>
    </TemplateData>
    <TemplateContent>
        <ProjectItem>MyClass.cs</ProjectItem>
    </TemplateContent>
</VSTemplate>
```

V tomto příkladu, maximální verze rozhraní .NET Framework, vyžadované šablonou, reprezentována `MaxFrameworkVersion`, je 4.7.1. Projekt vytvořené pomocí této šablony můžete cílové verze rozhraní .NET Framework až 4.7.1.

## <a name="see-also"></a>Viz také

- [Odkaz na schéma šablon sady Visual Studio](../extensibility/visual-studio-template-schema-reference.md)
- [Vytváření šablon projektů a položek](../ide/creating-project-and-item-templates.md)
