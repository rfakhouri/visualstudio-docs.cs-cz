---
title: Defaultname – Element (šablony sady Visual Studio) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
f1_keywords:
- http://schemas.microsoft.com/developer/vstemplate/2005#DefaultName
helpviewer_keywords:
- DefaultName element [Visual Studio project templates]
ms.assetid: 0ff056c8-b9d2-4747-9308-92adf1811491
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: e67d8970859906e839abf89e85e38c24c2d88066
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="defaultname-element-visual-studio-templates"></a>DefaultName – element (šablony sady Visual Studio)
Určuje název, který bude generovat systému projektu sady Visual Studio pro projekt nebo položku při jeho vytvoření.  
  
 \<VSTemplate >  
 \<TemplateData >  
 \<Defaultname – >  
  
## <a name="syntax"></a>Syntaxe  
  
```  
<DefaultName>  
    Default Project Name  
</DefaultName>  
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
|[TemplateData](../extensibility/templatedata-element-visual-studio-templates.md)|Požadovaný element.<br /><br /> Rozděluje šablonu a definuje, jak se zobrazuje v buď **nový projekt** nebo **přidat novou položku** dialogové okno.|  
  
## <a name="text-value"></a>Textová hodnota  
 Je vyžadována textová hodnota.  
  
 Tento text určuje výchozí název projektu nebo položky.  
  
## <a name="remarks"></a>Poznámky  
 `DefaultName` je volitelný element.  
  
 Tento element pro projekty, určuje název adresáře, který ukládá projektu na disk. Pro položky Určuje název souboru zdrojového souboru.  
  
 Když vytvoříte projekt nebo položku, můžete upravit výchozí název pomocí **název** možnost, která je k dispozici buď z **nový projekt** dialogové okno nebo **přidat novou položku** Dialogové okno.  
  
 Pokud nechcete, aby systém projektu pro generování výchozí název pro projekt nebo položku, nastavte [providedefaultname –](../extensibility/providedefaultname-element-visual-studio-templates.md) element `False`.  
  
## <a name="example"></a>Příklad  
 Následující příklad ilustruje metadata pro šablony standardní položky pro [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] třídy.  
  
```  
<VSTemplate Type="Item" Version="3.0.0"  
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">  
    <TemplateData>  
        <Name>MyClass</Name>  
        <Description>My custom C# class.</Description>  
        <Icon>Icon.ico</Icon>  
        <ProjectType>CSharp</ProjectType>  
        <DefaultName>MyClass.cs</DefaultName>  
    </TemplateData>  
    <TemplateContent>  
        <ProjectItem ReplaceParameters="true">MyClass.cs</ProjectItem>  
    </TemplateContent>  
</VSTemplate>  
```  
  
## <a name="see-also"></a>Viz také  
 [Odkaz na schéma šablon sady Visual Studio](../extensibility/visual-studio-template-schema-reference.md)   
 [Vytváření šablon projektů a položek](../ide/creating-project-and-item-templates.md)