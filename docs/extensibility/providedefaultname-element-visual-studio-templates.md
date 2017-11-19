---
title: "Providedefaultname – Element (šablony sady Visual Studio) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: http://schemas.microsoft.com/developer/vstemplate/2005#ProvideDefaultName
helpviewer_keywords: ProvideDefaultName element [Visual Studio project templates]
ms.assetid: 7b0e7b20-fd6b-42e2-81d0-e5100cea0528
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 797382d770c9c6f0ac8b48ef5d7eb7652ff28f1b
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="providedefaultname-element-visual-studio-templates"></a>ProvideDefaultName – element (šablony sady Visual Studio)
Určuje, zda [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] systému projektu vygeneruje název výchozí šablony do **přidat novou položku** nebo **nový projekt** dialogové okno.  
  
 \<VSTemplate >  
 \<TemplateData >  
 \<Providedefaultname – >  
  
## <a name="syntax"></a>Syntaxe  
  
```  
<ProvideDefaultName> true/false </ProvideDefaultName>  
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
  
 Text musí být buď `true` nebo `false`, která určuje, zda se má vygenerovat výchozí název šablony do **přidat novou položku** nebo **nový projekt** dialogové okno.  
  
## <a name="remarks"></a>Poznámky  
 `ProvideDefaultName`je volitelný element. Výchozí hodnota je `true`.  
  
 Pokud `ProvideDefaultName` element je `false`, **název** políčka **přidat novou položku** a **nový projekt** dialogová okna obsahovat hodnotu `<Enter_name>`.  
  
 Použití [defaultname –](../extensibility/defaultname-element-visual-studio-templates.md) elementu, který chcete zadat výchozí název projektu nebo položku v **přidat novou položku** a **nový projekt** dialogová okna.  
  
## <a name="example"></a>Příklad  
 Následující příklad kódu nastaví `ProvideDefaultName` element `false`.  
  
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
  
## <a name="see-also"></a>Viz také  
 [Odkaz na schéma šablon sady Visual Studio](../extensibility/visual-studio-template-schema-reference.md)   
 [Vytváření šablon projektů a položek](../ide/creating-project-and-item-templates.md)