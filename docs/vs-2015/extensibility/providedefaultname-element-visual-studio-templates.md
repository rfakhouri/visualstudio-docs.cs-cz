---
title: Providedefaultname – Element (šablony sady Visual Studio) | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/developer/vstemplate/2005#ProvideDefaultName
helpviewer_keywords:
- ProvideDefaultName element [Visual Studio project templates]
ms.assetid: 7b0e7b20-fd6b-42e2-81d0-e5100cea0528
caps.latest.revision: 13
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 0c97fdb245ba1ff066e19bcd32616649b47b9425
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42628218"
---
# <a name="providedefaultname-element-visual-studio-templates"></a>ProvideDefaultName – element (šablony sady Visual Studio)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [providedefaultname – Element (šablony sady Visual Studio)](https://docs.microsoft.com/visualstudio/extensibility/providedefaultname-element-visual-studio-templates).  
  
Určuje, zda [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] systém projektu bude generovat výchozí název šablony do **přidat novou položku** nebo **nový projekt** dialogové okno.  
  
 \<Vstemplate – >  
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
|[TemplateData –](../extensibility/templatedata-element-visual-studio-templates.md)|Požadovaný element.<br /><br /> Rozděluje šablonu a definuje, jak se zobrazuje **nový projekt** nebo **přidat novou položku** dialogové okno.|  
  
## <a name="text-value"></a>Textová hodnota  
 Je vyžadována textová hodnota.  
  
 Text musí být buď `true` nebo `false`, označující, jestli se mají generovat výchozí název šablony do **přidat novou položku** nebo **nový projekt** dialogové okno.  
  
## <a name="remarks"></a>Poznámky  
 `ProvideDefaultName` je volitelný prvek. Výchozí hodnota je `true`.  
  
 Pokud `ProvideDefaultName` element je `false`, **název** polí **přidat novou položku** a **nový projekt** dialogových oknech obsahovat hodnotu `<Enter_name>`.  
  
 Použití [defaultname –](../extensibility/defaultname-element-visual-studio-templates.md) elementu, chcete-li určit výchozí název projektu nebo položky v **přidat novou položku** a **nový projekt** dialogových oknech.  
  
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
  
## <a name="see-also"></a>Viz také  
 [Odkaz na schéma šablon sady Visual Studio](../extensibility/visual-studio-template-schema-reference.md)   
 [Vytváření šablon projektů a položek](../ide/creating-project-and-item-templates.md)

