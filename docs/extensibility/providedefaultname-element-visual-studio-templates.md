---
title: Providedefaultname – Element (šablony sady Visual Studio) | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/vstemplate/2005#ProvideDefaultName
helpviewer_keywords:
- ProvideDefaultName element [Visual Studio project templates]
ms.assetid: 7b0e7b20-fd6b-42e2-81d0-e5100cea0528
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: a2a19d6a93b709128e8750b6cea82d067b77db98
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66335812"
---
# <a name="providedefaultname-element-visual-studio-templates"></a>Providedefaultname – element (šablony sady Visual Studio)
Určuje, zda [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] systém projektu bude generovat výchozí název šablony do **přidat novou položku** nebo **nový projekt** dialogové okno.

 \<Vstemplate – > \<TemplateData > \<providedefaultname – >

## <a name="syntax"></a>Syntaxe

```xml
<ProvideDefaultName> true/false </ProvideDefaultName>
```

## <a name="attributes-and-elements"></a>Atributy a elementy
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.

### <a name="attributes"></a>Atributy
 Žádné

### <a name="child-elements"></a>Podřízené elementy
 Žádné

### <a name="parent-elements"></a>Nadřazené prvky

|Prvek|Popis|
|-------------|-----------------|
|[TemplateData](../extensibility/templatedata-element-visual-studio-templates.md)|Požadovaný element.<br /><br /> Rozděluje šablonu a definuje, jak se zobrazuje **nový projekt** nebo **přidat novou položku** dialogové okno.|

## <a name="text-value"></a>Textová hodnota
 Je vyžadována textová hodnota.

 Text musí být buď `true` nebo `false`, označující, jestli se mají generovat výchozí název šablony do **přidat novou položku** nebo **nový projekt** dialogové okno.

## <a name="remarks"></a>Poznámky
 `ProvideDefaultName` je volitelný prvek. Výchozí hodnota je `true`.

 Pokud `ProvideDefaultName` element je `false`, **název** polí **přidat novou položku** a **nový projekt** dialogových oknech obsahovat hodnotu `<Enter_name>`.

 Použití [defaultname –](../extensibility/defaultname-element-visual-studio-templates.md) elementu, chcete-li určit výchozí název projektu nebo položky v **přidat novou položku** a **nový projekt** dialogových oknech. Při hodnotu `ProvideDefaultName` element je `true`, vynechání `DefaultName` – element pro projekty naplní dialogových oken s názvem šablony, tedy hodnota [název](../extensibility/name-element-visual-studio-templates.md) elementu.

## <a name="example"></a>Příklad
 Následující příklad kódu nastaví `ProvideDefaultName` elementu `false`.

```
<VSTemplate Type="Item" Version="3.0.0"
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">
    <TemplateData>
        <Name>MyClass</Name>
        <Description>My custom C# class.</Description>
        <Icon>Icon.ico</Icon>
        <ProjectType>CSharp</ProjectType>
        <ProvideDefaultName>false</ProvideDefaultName>
    </TemplateData>
    <TemplateContent>
        <ProjectItem>MyClass.cs</ProjectItem>
    </TemplateContent>
</VSTemplate>
```

## <a name="see-also"></a>Viz také:
- [Visual Studio odkaz na schéma šablon](../extensibility/visual-studio-template-schema-reference.md)
- [Vytváření šablon projektů a položek](../ide/creating-project-and-item-templates.md)
