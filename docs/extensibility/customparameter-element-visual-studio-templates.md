---
title: CustomParameter – Element (šablony sady Visual Studio) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
f1_keywords:
- http://schemas.microsoft.com/developer/vstemplate/2005#CustomParameter
helpviewer_keywords:
- CustomParameters element [Visual Studio project templates]
ms.assetid: 743c4489-74ac-403a-bbaa-eed7d785a3ac
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 154586701386f5f8f56c128920e12ca3147deb6b
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31100566"
---
# <a name="customparameter-element-visual-studio-templates"></a>CustomParameter – element (šablony sady Visual Studio)
Obsahuje název vlastní parametru a hodnota, která má použít při vytváření projektu nebo položky ze šablony.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
<CustomParameter Name="name" Value="value">  
```  
  
## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.  
  
### <a name="attributes"></a>Atributy  
  
|Atribut|Popis|  
|---------------|-----------------|  
|`Name`|Požadováno. Název parametru Formát parametrů je $*název*$.|  
|`Value`|Požadováno. Nahrazující hodnota pro parametr.|  
  
### <a name="child-elements"></a>Podřízené elementy  
 Žádné  
  
### <a name="parent-elements"></a>Nadřazené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[CustomParameters](../extensibility/customparameters-element-visual-studio-templates.md)|Skupiny vlastní parametry, které mají být předány do Průvodce vytvořením šablony, pokud Průvodce provede nahrazení parametru.|  
  
## <a name="remarks"></a>Poznámky  
 Když šablonu obsahuje `CustomParameter` elementy, každá instance `Name` atribut je nahrazena `Value` atribut v souborech vytvořený projekt nebo položku.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje, jak použít několik vlastní parametry v šabloně. Vytvoření projektu nebo položky ze šablony s následujícími parametry vlastní, všechny instance `$color1$` a `$color2$` v šabloně se nahradí soubory `Red` a `Blue`, v uvedeném pořadí.  
  
```  
<CustomParameters>  
    <CustomParameter Name="$color1$" Value="Red"/>  
    <CustomParameter Name="$color2$" Value="Blue "/>  
</CustomParameters>  
```  
  
## <a name="see-also"></a>Viz také  
 [CustomParameters – Element (šablony sady Visual Studio)](../extensibility/customparameters-element-visual-studio-templates.md)   
 [Parametry šablony](../ide/template-parameters.md)   
 [Odkaz na schéma šablon sady Visual Studio](../extensibility/visual-studio-template-schema-reference.md)