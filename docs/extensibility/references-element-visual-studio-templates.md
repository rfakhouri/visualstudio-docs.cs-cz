---
title: Odkazuje na Element (šablony sady Visual Studio) | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/vstemplate/2005#References
helpviewer_keywords:
- <References> element [Visual Studio Templates]
- References element [Visual Studio Templates]
ms.assetid: 1969146d-46bf-422d-8d46-0e9493925003
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 3ae0ee308af1502a7c07766e790b79e51f692a96
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62433406"
---
# <a name="references-element-visual-studio-templates"></a>References – element (šablony sady Visual Studio)
Seskupuje odkazy na sestavení, které šablona přidá do projektů.

 \<Vstemplate – > \<TemplateContent > \<odkazy >

## <a name="syntax"></a>Syntaxe

```xml
<References>
    <Reference>... </Reference>
    <Reference>... </Reference>
    ...
</References>
```

## <a name="attributes-and-elements"></a>Atributy a elementy
 Následující oddíly popisují atributy a podřízené a nadřazené elementy.

### <a name="attributes"></a>Atributy
 Žádné

### <a name="child-elements"></a>Podřízené prvky

|Prvek|Popis|
|-------------|-----------------|
|[Referenční informace](../extensibility/reference-element-visual-studio-templates.md)|Požadovaný element.<br /><br /> Určuje odkaz na sestavení přidat, pokud je položka přidána do projektu. Musí být jeden nebo více `Reference` prvky `References` elementu.|

### <a name="parent-elements"></a>Nadřazené prvky

|Prvek|Popis|
|-------------|-----------------|
|[TemplateContent](../extensibility/templatecontent-element-visual-studio-templates.md)|Určuje obsah značek šablony.|

## <a name="remarks"></a>Poznámky
 `References` je volitelný podřízený prvek `TemplateContent`.

 `Reference` a `References` prvky lze použít pouze v *.vstemplate* soubory, které mají `Type` hodnotu atributu `Item`.

## <a name="example"></a>Příklad
 Následující příklad ukazuje, `TemplateContent` elementu šablony položky. Přidá odkazy na tato konfigurace XML *System.dll* a *System.Data.dll* sestavení.

```xml
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

## <a name="see-also"></a>Viz také:
- [Visual Studio odkaz na schéma šablon](../extensibility/visual-studio-template-schema-reference.md)
- [Vytváření šablon projektů a položek](../ide/creating-project-and-item-templates.md)
