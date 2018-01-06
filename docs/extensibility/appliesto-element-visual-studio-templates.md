---
title: "AppliesTo – Element (šablony sady Visual Studio) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8fb1334b-d78c-405f-98b4-786e9f6b58d7
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 35e11a53b2b9b63a71aab2858151721cfdfd7f9c
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="appliesto-element-visual-studio-templates"></a>AppliesTo – element (šablony sady Visual Studio)
Určuje volitelný výraz, který musí odpovídat jedné nebo více možnostem (viz <xref:Microsoft.VisualStudio.Shell.Interop.VsProjectCapabilityExpressionMatcher>). Možnosti jsou vystavené typy projektů prostřednictvím hierarchie jako vlastnost <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID5>. Tímto způsobem může šablony sdílet více typů projektů, které mají společné příslušné schopnosti.  
  
 Tento element je volitelný. Soubor šablony může obsahovat maximálně jednu jeho instanci. Tento element pouze umožňuje určit, kterou šablonu položky lze případně použít, na základě schopností aktuálně vybraného aktivního projektu. Neumožňuje určit, že šablonu položky nelze použít. Pokud `AppliesTo` chybí nebo je výraz výslovný souhlas se službou úspěšně, pak `TemplateID` nebo `TemplateGroupID` se používá k zajištění šablonu použít jako u starších verzí produktu.  
  
 Dostupné ve verzi Visual Studio 2013 Update 2. Chcete-li správnou verzi, najdete v části [odkazování na sestavení poskytnuté ve Visual Studio 2013 SDK Update 2](http://msdn.microsoft.com/en-us/42b65c3e-e42b-4c39-98c8-bea285f25ffb).  
  
 \<VSTemplate >  
 \<TemplateData >  
 \<AppliesTo – >  
  
## <a name="syntax"></a>Syntaxe  
  
```  
<AppliesTo>Capability1</AppliesTo>   
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
|[TemplateData](../extensibility/templatedata-element-visual-studio-templates.md)|Určuje kategorii šablony.|  
  
## <a name="text-value"></a>Textová hodnota  
 Je vyžadována textová hodnota. Tento text určuje schopnosti projektu.  
  
 Platná syntaxe výrazu je definována takto:  
  
-   Výraz funkce, jako je například "(VisualC &#124; CSharp) + (Mstestu &#124; NUnit) ".  
  
-   "&#124;" je operátor OR.  
  
-   "A" a "+" znaky jsou obě a operátory.  
  
-   Znak "!" je operátor NOT.  
  
-   Závorky určují pořadí vyhodnocování.  
  
-   Hodnota null nebo prázdný výraz jsou vyhodnoceny jako shoda.  
  
-   Možnosti projektu může být jakémukoli znaku kromě těchto vyhrazené znaky: "" :;,+-*/\\! ~ &#124; & %$@^()={} <> []? \t\b\n\r  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje tři různé šablony. `Template1`buď pro všechny typy projektů jazyka C# nebo jakýkoli jiný typ projektu, který podporuje se vztahuje `WindowsAppContainer` schopností. `Template2`platí pro všechny projekty c jakéhokoli druhu. `Template3`platí pro projekty C#, které nejsou `WindowsAppContainer` projekty.  
  
```xml  
<!--  Template 1 -->  
<?xml version="1.0" encoding="utf-8"?>  
<VSTemplate Version="3.0.0" Type="Item" xmlns="http://schemas.microsoft.com/developer/vstemplate/2005" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://schemas.microsoft.com/developer/vstemplate/2005">  
    <TemplateData>  
        <AppliesTo>CSharp | WindowsAppContainer</AppliesTo>   
    </TemplateData>  
</VSTemplate>  
  
<!--  Template 2 -->  
<?xml version="1.0" encoding="utf-8"?>  
<VSTemplate Version="3.0.0" Type="Item" xmlns="http://schemas.microsoft.com/developer/vstemplate/2005" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://schemas.microsoft.com/developer/vstemplate/2005">  
    <TemplateData>  
        <AppliesTo>CSharp</AppliesTo>   
    </TemplateData>  
</VSTemplate>  
  
<!--  Template 1 -->  
<?xml version="1.0" encoding="utf-8"?>  
<VSTemplate Version="3.0.0" Type="Item" xmlns="http://schemas.microsoft.com/developer/vstemplate/2005" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://schemas.microsoft.com/developer/vstemplate/2005">  
    <TemplateData>  
        <AppliesTo>CSharp_Class + (!WindowsAppContainer)</AppliesTo>   
    </TemplateData>  
</VSTemplate>  
  
```  
  
## <a name="see-also"></a>Viz také  
 [Odkaz na schéma šablon sady Visual Studio](../extensibility/visual-studio-template-schema-reference.md)   
 [Vytváření šablon projektů a položek](../ide/creating-project-and-item-templates.md)