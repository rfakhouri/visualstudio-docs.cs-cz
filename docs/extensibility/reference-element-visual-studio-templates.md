---
title: Referenční Element (šablony sady Visual Studio) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
f1_keywords:
- http://schemas.microsoft.com/developer/vstemplate/2005#Reference
helpviewer_keywords:
- Reference element [Visual Studio templates]
- <Reference> element [Visual Studio templates]
ms.assetid: 852772ea-c324-42e9-8c8a-6d565414a109
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 9e0217360b2a8e9c6c8e723561aff383ed3226d1
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31136294"
---
# <a name="reference-element-visual-studio-templates"></a>Element odkazu (šablony sady Visual Studio)
Určuje odkaz na sestavení přidat, pokud položka byla přidána do projektu.  
  
 \<VSTemplate >  
 \<TemplateContent >  
 \<Odkazy na >  
 \<Referenční dokumentace >  
  
## <a name="syntax"></a>Syntaxe  
  
```  
<Reference>  
    <Assembly> ... </Assembly>  
</Reference>  
```  
  
## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující oddíly popisují atributy a podřízené a nadřazené elementy.  
  
### <a name="attributes"></a>Atributy  
 Žádné  
  
### <a name="child-elements"></a>Podřízené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[Assembly](../extensibility/assembly-element-visual-studio-templates.md)|Požadovaný element.<br /><br /> Určuje informace o sestavení, která šablona se používá k přidání odkazu z tohoto sestavení do projektů. Musí být jeden `Assembly` element v každé `Reference` elementu.|  
  
### <a name="parent-elements"></a>Nadřazené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[Odkazy](../extensibility/references-element-visual-studio-templates.md)|Skupiny odkazy na sestavení, které šablona se přidá do projektů.|  
  
## <a name="remarks"></a>Poznámky  
 `Reference` je požadovaný podřízený element `References`.  
  
 `Reference` a `References` elementy lze použít pouze v souborech .vstemplate, které mají `Type` hodnotu atributu `Item`.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje `TemplateContent` element šablony položky. Tato konfigurace XML přidá odkazy na sestavení System.dll a System.Data.dll.  
  
```  
<TemplateContent>  
    <References>  
        <Reference>  
            <Assembly>  
                System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089  
            </Assembly>  
        </Reference>  
        <Reference>  
            <Assembly>  
                System.Data, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089  
            </Assembly>  
        </Reference>  
    </References>  
    ...  
</TemplateContent>  
```  
  
## <a name="see-also"></a>Viz také  
 [Odkaz na schéma šablon sady Visual Studio](../extensibility/visual-studio-template-schema-reference.md)   
 [Vytváření šablon projektů a položek](../ide/creating-project-and-item-templates.md)