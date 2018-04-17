---
title: Assembly – Element (šablony sady Visual Studio) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
f1_keywords:
- http://schemas.microsoft.com/developer/vstemplate/2005#Assembly
helpviewer_keywords:
- Assembly element [Visual Studio templates]
- <Assembly> element [Visual Studio templates]
ms.assetid: 9242f76a-1273-4b8a-8f26-6606f91829ef
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 97e6209fdf446d88ed79ef741c3584b2bc4f5602
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="assembly-element-visual-studio-templates"></a>Element sestavení (šablony sady Visual Studio)
Určuje informace o sestavení, která šablona se používá k přidání odkazu z tohoto sestavení do projektů.  
  
 \<VSTemplate >  
 \<TemplateContent >  
 \<Odkazy na >  
 \<Referenční dokumentace >  
 \<sestavení >  
  
## <a name="syntax"></a>Syntaxe  
  
```  
<Assembly> AssemblyName </Assembly>  
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
|[Referenční informace](../extensibility/reference-element-visual-studio-templates.md)|Určuje odkaz na sestavení přidat, pokud položka byla přidána do projektu.|  
  
## <a name="text-value"></a>Textová hodnota  
 Je vyžadována textová hodnota.  
  
 Tento text určuje sestavení se při vytvoření instance šablony položky přidat do projektu. Tento název sestavení musí být zadán v jednom z následujících způsobů:  
  
-   Jako název úplné sestavení. Příklad:  
  
    ```  
    <Assembly>  
        MyAssembly, Version=1.0.3300.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a, Custom = null.  
    </Assembly>  
    ```  
  
-   Jako jednoduchý text odkazu. Příklad:  
  
    ```  
    <Assembly> System </Assembly>  
    ```  
  
## <a name="remarks"></a>Poznámky  
 `Assembly` je požadovaný podřízený element `Reference`.  
  
 `Reference`, `References,` a `Assembly` elementy lze použít pouze v souborech .vstemplate, které mají `Type` hodnotu atributu `Item`.  
  
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