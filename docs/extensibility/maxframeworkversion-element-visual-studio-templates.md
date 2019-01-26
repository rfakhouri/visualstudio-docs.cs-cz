---
title: Maxframeworkversion – Element (šablony sady Visual Studio) | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.technology: vs-ide-general
ms.topic: reference
helpviewer_keywords:
- <MaxFrameworkVersion> Element (Visual Studio Templates)
- MaxFrameworkVersion Element (Visual Studio Templates)
ms.assetid: f732a9d3-fc29-405b-9298-01ea83fc58b8
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 573fcbce3b395f7f351d57208998b0b63b175559
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55039147"
---
# <a name="maxframeworkversion-element-visual-studio-templates"></a>Maxframeworkversion – element (šablony sady Visual Studio)

Určuje maximální verzi rozhraní .NET Framework, který vyžaduje šablony. Určuje nejvyšší hodnotu, která je k dispozici v **cílovou verzi rozhraní Framework** rozevíracího seznamu z **nový projekt** dialogového okna. Aby uživatelé mohli vybrat verzi rozhraní framework, musíte zadat také [requiredframeworkversion –](../extensibility/requiredframeworkversion-element-visual-studio-templates.md) jako minimální verzi rozhraní .NET Framework pro šablonu.

> [!IMPORTANT]
> Od verze Visual Studio 2017 verze 15.6 a **cílovou verzi rozhraní Framework** rozevíracího seznamu už není filtr pro zobrazený šablony v **šablony** část **nový projekt** dialogového okna. Místo toho **cílovou verzi rozhraní Framework** rozevírací seznam funguje jako výběr framework pro vybranou šablonu.

 \<VSTemplate> \<TemplateData> \<MaxFrameworkVersion>

## <a name="syntax"></a>Syntaxe

```xml
<MaxFrameworkVersion> ... </MaxFrameworkVersion>
```

## <a name="attributes-and-elements"></a>Atributy a elementy
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.

### <a name="attributes"></a>Atributy
 Žádné

### <a name="child-elements"></a>Podřízené prvky
 Žádné

### <a name="parent-elements"></a>Nadřazené prvky

|Prvek|Popis|
|-------------|-----------------|
|[TemplateData](../extensibility/templatedata-element-visual-studio-templates.md)|Požadovaný element.<br /><br /> Rozděluje šablonu a definuje, jak se zobrazí buď **nový projekt** nebo **přidat novou položku** dialogové okno.|

## <a name="text-value"></a>Textová hodnota
 Je vyžadována textová hodnota.

 Text musí být nejvyšší číslo verze rozhraní .NET Framework, který je povolen pomocí šablony.

## <a name="remarks"></a>Poznámky

`MaxFrameworkVersion` je volitelný prvek. `MaxFrameworkVersion` Elementu musí vynechat, pokud to není nutné, aby nedocházelo k neúmyslně omezit rozsah z balíčků .NET Framework verze šablony. Musí být také vynechána, pokud rozhraní .NET Framework se nedá použít v šabloně.

## <a name="example"></a>Příklad

Následující příklad ukazuje metadata pro standardní [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] šablony třídy.

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

V tomto příkladu, maximální verze rozhraní .NET Framework, která je nutná šablonou, reprezentovaný `MaxFrameworkVersion`, je 4.7.1. Do projektu vytvořeného s touto šablonou můžete cílit na rozhraní .NET Framework verze až 4.7.1.

## <a name="see-also"></a>Viz také:

- [Visual Studio odkaz na schéma šablon](../extensibility/visual-studio-template-schema-reference.md)
- [Vytváření šablon projektů a položek](../ide/creating-project-and-item-templates.md)
