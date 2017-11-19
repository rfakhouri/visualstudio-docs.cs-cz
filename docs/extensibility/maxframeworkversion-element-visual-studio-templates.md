---
title: "Maxframeworkversion – Element (šablony sady Visual Studio) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- <MaxFrameworkVersion> Element (Visual Studio Templates)
- MaxFrameworkVersion Element (Visual Studio Templates)
ms.assetid: f732a9d3-fc29-405b-9298-01ea83fc58b8
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: da1b30274254c5c1dd81ad20dd64e8749672f96e
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="maxframeworkversion-element-visual-studio-templates"></a>MaxFrameworkVersion – element (šablony sady Visual Studio)
Určuje maximální verze rozhraní .NET Framework, který je požadován pro šablonu. Určuje, jestli se v zobrazí šablony **šablony** části **přidat nový projekt** dialogové okno, na základě hodnoty, který je vybraný v **cílová verze Framework** pole **přidat nový projekt** dialogové okno.  
  
 \<VSTemplate >  
 \<Maxframeworkversion – >  
  
## <a name="syntax"></a>Syntaxe  
  
```  
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
 `MaxFrameworkVersion`je volitelný element. Element v `TemplateData` souboru .vstemplate funguje jako filtr pro **šablony** části **přidat nový projekt** dialogové okno. Pouze šablony, jejichž požadavky na rozhraní .NET Framework jsou menší než `MaxFrameworkVersion` element hodnoty se zobrazí, na základě hodnoty, který je vybraný v **cílová verze Framework** pole **přidat nový projekt**dialogové okno. `MaxFrameworkVersion` Element by tento parametr vynechán, pokud není nutné, aby nechtěně způsobit šablony v případě, že se používají s novější verze rozhraní .NET Framework.  
  
## <a name="example"></a>Příklad  
 Následující příklad ilustruje metadata pro standardní [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] šablona třídy.  
  
```  
<VSTemplate Type="Item" Version="3.0.0"  
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">  
    <TemplateData>  
        <Name>MyClass</Name>  
        <Description>My custom C# class template.</Description>  
        <Icon>Icon.ico</Icon>  
        <ProjectType>CSharp</ProjectType>  
        <MaxFrameworkVersion>3.5</MaxFrameworkVersion>  
        <DefaultName>MyClass</DefaultName>  
    </TemplateData>  
    <TemplateContent>  
        <ProjectItem>MyClass.cs</ProjectItem>  
    </TemplateContent>  
</VSTemplate>  
```  
  
 V tomto příkladu, maximální verze rozhraní .NET Framework, vyžadované šablonou, reprezentována `MaxFrameworkVersion`, je 3.5. Výše uvedené šablony se zobrazí, pouze když zvolíte 3.0 nebo 3.5 v **cílová verze Framework** pole **přidat nový projekt** dialogové okno.  
  
## <a name="see-also"></a>Viz také  
 [Odkaz na schéma šablon sady Visual Studio](../extensibility/visual-studio-template-schema-reference.md)   
 [Vytváření šablon projektů a položek](../ide/creating-project-and-item-templates.md)