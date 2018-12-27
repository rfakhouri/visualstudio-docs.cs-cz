---
title: SortOrder – Element (šablony sady Visual Studio) | Dokumentace Microsoftu
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/vstemplate/2005#SortOrder
helpviewer_keywords:
- SortOrder element [Visual Studio Templates]
- <SortOrder> element [Visual Studio Templates]
ms.assetid: 151932c1-f08a-4f78-a8d0-bd2f32211a9c
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 2710c85caf2ff675a05236aac48d08412e794ca6
ms.sourcegitcommit: 35bebf794f528d73d82602e096fd97d7b8f82c25
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/18/2018
ms.locfileid: "53561340"
---
# <a name="sortorder-element-visual-studio-templates"></a>SortOrder – element (šablony sady Visual Studio)
Určuje hodnotu, která slouží k uspořádání šablony, mezi další šablony ve stejné kategorii, jak se zobrazí v buď **nový projekt** nebo **přidat novou položku** dialogové okno.  
  
 \<Vstemplate – >  
 \<TemplateData >  
 \<SortOrder – >  
  
## <a name="syntax"></a>Syntaxe  
  
```  
<SortOrder> ... </SortOrder>  
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
  
 `integer` , Která představuje hodnotu pořadí řazení.  
  
## <a name="remarks"></a>Poznámky  
 `SortOrder` je volitelný prvek. Výchozí hodnota je 100 a všechny hodnoty musí být násobky 10.  
  
 `SortOrder` Prvek je ignorován, uživatelem vytvořené šablony. Všechny šablony vytvořené uživatelem jsou seřazená podle abecedy.  
  
 Šablony, které mají nízké řazení seřazení hodnot se zobrazí buď **nový projekt** nebo **novou položku Přidat** dialogovému oknu před šablony, které mají vysokou řazení seřazení hodnot.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje metadata pro standardní [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] šablony třídy.  
  
```  
<VSTemplate Type="Item" Version="3.0.0"  
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">  
    <TemplateData>  
        <Name>MyClass</Name>  
        <Description>My custom C# class template.</Description>  
        <Icon>Icon.ico</Icon>  
        <ProjectType>CSharp</ProjectType>  
        <SortOrder>290</SortOrder>  
        <DefaultName>MyClass</DefaultName>  
    </TemplateData>  
    <TemplateContent>  
        <ProjectItem>MyClass.cs</ProjectItem>  
    </TemplateContent>  
</VSTemplate>  
```  
  
 V tomto příkladu `SortOrder` element je relativně vysoké. Je pravděpodobné, další [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] bude mít šablony položek `SortOrder` hodnotu nižší, než `290` a zobrazí se před tuto šablonu v **nová položka** dialogové okno.  
  
## <a name="see-also"></a>Viz také  
 [Odkaz na schéma šablon sady Visual Studio](../extensibility/visual-studio-template-schema-reference.md)   
 [Vytváření šablon projektů a položek](../ide/creating-project-and-item-templates.md)