---
title: Requiredframeworkversion – Element (šablony sady Visual Studio) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- <RequiredFrameworkVersion> (Visual Studio Templates)
- RequiredFrameworkVersion (Visual Studio Templates)
ms.assetid: 08a4f609-51a5-4723-b89f-99277fb18871
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: adc1a138c50c0fe13962f6601449eb3498d90398
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="requiredframeworkversion-element-visual-studio-templates"></a>RequiredFrameworkVersion – element (šablony sady Visual Studio)

Určuje minimální verze rozhraní .NET Framework, který je požadován pro šablonu. Způsobuje, že **cílová verze Framework** rozevíracího seznamu, který se má zobrazit v **nový projekt** dialogové okno. `RequiredFrameworkVersion` Element také určuje nejnižší hodnotu, která je k dispozici v rozevírací nabídce.

> [!IMPORTANT]
> Od verze Visual Studio 2017 verze 15,6 operací, **cílová verze Framework** rozevírací již není filtr pro zobrazený šablony v **šablony** části **nový projekt** dialogové okno. Místo toho rozevíracího seznamu funguje jako výběr framework pro vybranou šablonu.

 \<VSTemplate > \<TemplateData > \<RequiredFrameworkVersion >

## <a name="syntax"></a>Syntaxe

```xml
<RequiredFrameworkVersion> .... </RequiredFrameworkVersion>
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

 Text musí být číslo minimální verze rozhraní .NET Framework, která je požadována pro šablonu.

## <a name="remarks"></a>Poznámky

`RequiredFrameworkVersion` je volitelný element. Použijte tento element pouze v případě, že šablona podporuje konkrétní minimální verzi (a novější verze, pokud existuje) rozhraní .NET Framework. Pokud zadáte `RequiredFrameworkVersion` elementu a šablony nepodporuje konkrétní minimální verze rozhraní .NET Framework **cílová verze Framework** rozevíracího seznamu se zobrazí, když se nedá použít.

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

V tomto příkladu, minimální verze rozhraní .NET Framework, vyžadované šablonou, reprezentována `RequiredFrameworkVersion`, je 3.0. Projekt vytvořené pomocí této šablony můžete cílové verze rozhraní .NET Framework 3.0 od.

## <a name="see-also"></a>Viz také

- [Odkaz na schéma šablon sady Visual Studio](../extensibility/visual-studio-template-schema-reference.md)
- [Vytváření šablon projektů a položek](../ide/creating-project-and-item-templates.md)
- [Cílení na konkrétní verzi rozhraní .NET Framework](../ide/targeting-a-specific-dotnet-framework-version.md)
