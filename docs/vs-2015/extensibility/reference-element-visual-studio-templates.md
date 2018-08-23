---
title: Odkazovat na Element (šablony sady Visual Studio) | Dokumentace Microsoftu
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
- http://schemas.microsoft.com/developer/vstemplate/2005#Reference
helpviewer_keywords:
- Reference element [Visual Studio templates]
- <Reference> element [Visual Studio templates]
ms.assetid: 852772ea-c324-42e9-8c8a-6d565414a109
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 2fdd9b1a4b7703bbd0c4c0a5a8302e8a101b9559
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42628724"
---
# <a name="reference-element-visual-studio-templates"></a>Element odkazu (šablony sady Visual Studio)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [Reference – Element (šablony sady Visual Studio)](https://docs.microsoft.com/visualstudio/extensibility/reference-element-visual-studio-templates).  
  
Určuje odkaz na sestavení přidat, pokud je položka přidána do projektu.  
  
 \<Vstemplate – >  
 \<TemplateContent – >  
 \<Odkazy >  
 \<Odkaz >  
  
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
|[Assembly](../extensibility/assembly-element-visual-studio-templates.md)|Požadovaný element.<br /><br /> Určuje informace o sestavení, který používá šablonu přidáte odkaz na toto sestavení do projektů. Musí obsahovat jeden `Assembly` element v každé `Reference` elementu.|  
  
### <a name="parent-elements"></a>Nadřazené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[Odkazy](../extensibility/references-element-visual-studio-templates.md)|Seskupuje odkazy na sestavení, které šablona přidá do projektů.|  
  
## <a name="remarks"></a>Poznámky  
 `Reference` je vyžadovaný podřízený prvek `References`.  
  
 `Reference` a `References` prvky lze použít pouze v souborech .vstemplate, které mají `Type` hodnotu atributu `Item`.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje, `TemplateContent` elementu šablony položky. Tato konfigurace XML přidá odkazy na sestavení System.dll a System.Data.dll.  
  
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

