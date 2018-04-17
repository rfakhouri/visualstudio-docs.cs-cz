---
title: ProjectItem – Element (šablony sady Visual Studio položky) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
f1_keywords:
- http://schemas.microsoft.com/developer/vstemplate/2005#ProjectItem
helpviewer_keywords:
- <ProjectItem> element [Visual Studio item templates]
- ProjectItem element [Visual Studio item templates]
ms.assetid: 9ed94112-0c38-49df-b728-0dd2d0d1eb47
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 886fc57258b4ccafaa4ab8d522fad632de455e17
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="projectitem-element-visual-studio-item-templates"></a>ProjectItem – element (šablony položek sady Visual Studio)
Určuje soubor, který je součástí šablony položky.  
  
> [!NOTE]
>  `ProjectItem` Element přijímá různé atributy v závislosti na tom, jestli je šablona pro projekt nebo položku. Toto téma vysvětluje `ProjectItem` element pro položku. Další informace o `ProjectItem` element pro šablony projektů, najdete v části [ProjectItem – Element (šablony projektů Visual Studio)](../extensibility/projectitem-element-visual-studio-project-templates.md).  
  
 \<VSTemplate >  
 \<TemplateContent >  
 \<ProjectItem – >  
  
## <a name="syntax"></a>Syntaxe  
  
```  
<ProjectItem  
    SubType="Form/Component/CustomControl/UserControl"  
    CustomTool="string"  
    ItemType="string"  
    ReplaceParameters="true/false"  
    TargetFileName="TargetFileName.ext">  
        FileName.ext  
</ProjectItem>  
```  
  
## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující oddíly popisují atributy a podřízené a nadřazené elementy.  
  
### <a name="attributes"></a>Atributy  
  
|Atribut|Popis|  
|---------------|-----------------|  
|`SubType`|Nepovinný atribut.<br /><br /> Určuje dílčí položky do šablony položek s více soubory. Tato hodnota se používá k určení editoru, [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] použije otevřete položku.|  
|`CustomTool`|Nepovinný atribut.<br /><br /> Nastaví CustomTool pro položku v souboru projektu.|  
|`ItemType`|Nepovinný atribut.<br /><br /> Nastaví typ položky pro položku v souboru projektu.|  
|`ReplaceParameters`|Nepovinný atribut.<br /><br /> Logická hodnota, která určuje, zda je položka hodnoty parametrů, které se musí nahradit při vytváření projektu ze šablony. Výchozí hodnota je `false`.|  
|`TargetFileName`|Nepovinný atribut.<br /><br /> Určuje název položky, který je vytvořený z šablony. Tento atribut je užitečné pro vytvoření název položky pomocí nahrazení parametru.|  
  
### <a name="child-elements"></a>Podřízené elementy  
 Žádné  
  
### <a name="parent-elements"></a>Nadřazené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[TemplateContent](../extensibility/templatecontent-element-visual-studio-templates.md)|Určuje obsah šablony.|  
  
## <a name="text-value"></a>Textová hodnota  
 Je vyžadována textová hodnota.  
  
 A `string` , která představuje název souboru v souboru ZIP šablony.  
  
## <a name="remarks"></a>Poznámky  
 `ProjectItem` je volitelné podřízeným `TemplateContent`.  
  
 `TargetFileName` Atribut slouží k přejmenování souborů s parametry. Například pokud soubor `MyFile.vb` existuje v kořenovém adresáři souboru ZIP šablony, ale chcete soubor s názvem podle názvu souboru zadaný uživatelem v **přidat novou položku** dialogové okno, použijte následující kód XML:  
  
```  
<ProjectItem TargetFileName="$fileinputname$.vb">MyFile.vb</ProjectItem>  
```  
  
 Při vytvoření nové položky z této šablony, názvu souboru bude vycházet uživatel zadaný v název **přidat novou položku** dialogové okno. To je užitečné v případě vytváření šablon položek s více soubory. Další informace najdete v tématu [postupy: vytváření šablon položek s více soubory](../ide/how-to-create-multi-file-item-templates.md) a [parametry šablony](../ide/template-parameters.md).  
  
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
 [Postupy: vytváření šablon položek s více soubory](../ide/how-to-create-multi-file-item-templates.md)   
 [Parametry šablony](../ide/template-parameters.md)