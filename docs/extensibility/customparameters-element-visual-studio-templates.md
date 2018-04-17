---
title: CustomParameters – Element (šablony sady Visual Studio) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
f1_keywords:
- http://schemas.microsoft.com/developer/vstemplate/2005#CustomParameters
helpviewer_keywords:
- CustomParameters element [Visual Studio project templates]
ms.assetid: cf3efc91-1532-4022-bbb8-a18658424fee
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 4c09d320b1a9185e79e36d54ff0363219d3dabc6
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="customparameters-element-visual-studio-templates"></a>CustomParameters – element (šablony sady Visual Studio)
Skupiny vlastní parametry, které mají být předány do Průvodce vytvořením šablony, pokud Průvodce provede nahrazení parametru.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
<CustomParameters>  
    <CustomParameter/>  
    <CustomParameter/>  
</CustomParameters>  
```  
  
## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.  
  
### <a name="attributes"></a>Atributy  
 Žádné  
  
### <a name="child-elements"></a>Podřízené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[CustomParameter](../extensibility/customparameter-element-visual-studio-templates.md)|Volitelný element.<br /><br /> Obsahuje název vlastní parametru a hodnota, která má použít při vytváření projektu nebo položky ze šablony. Může být nula nebo více `CustomParameter` elementů v `CustomParameters` elementu.|  
  
### <a name="parent-elements"></a>Nadřazené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[TemplateContent](../extensibility/templatecontent-element-visual-studio-templates.md)|Určuje obsah šablony.|  
  
## <a name="remarks"></a>Poznámky  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje, jak použít několik vlastní parametry v šabloně. Vytvoření projektu nebo položky ze šablony s následujícími parametry vlastní, všechny instance `$color1$` a `$color2$` v šabloně se nahradí soubory `Red` a `Blue`, v uvedeném pořadí.  
  
```  
<CustomParameters>  
    <CustomParameter Name="$color1$" Value="Red"/>  
    <CustomParameter Name="$color2$" Value="Blue "/>  
</CustomParameters>  
```  
  
## <a name="see-also"></a>Viz také  
 [CustomParameter – Element (šablony sady Visual Studio)](../extensibility/customparameter-element-visual-studio-templates.md)   
 [Parametry šablony](../ide/template-parameters.md)   
 [Odkaz na schéma šablon sady Visual Studio](../extensibility/visual-studio-template-schema-reference.md)