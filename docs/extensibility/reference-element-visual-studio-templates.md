---
title: Odkazovat na Element (šablony sady Visual Studio) | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/vstemplate/2005#Reference
helpviewer_keywords:
- Reference element [Visual Studio templates]
- <Reference> element [Visual Studio templates]
ms.assetid: 852772ea-c324-42e9-8c8a-6d565414a109
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 46c9cbde1186a0dd764c3075ef1566eb1fd5ea07
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66334391"
---
# <a name="reference-element-visual-studio-templates"></a>Reference – element (šablony sady Visual Studio)
Určuje odkaz na sestavení přidat, pokud je položka přidána do projektu.

 \<Vstemplate – > \<TemplateContent > \<odkazy > \<odkaz >

## <a name="syntax"></a>Syntaxe

```xml
<Reference>
    <Assembly> ... </Assembly>
</Reference>
```

## <a name="attributes-and-elements"></a>Atributy a elementy
 Následující oddíly popisují atributy a podřízené a nadřazené elementy.

### <a name="attributes"></a>Atributy
 Žádné

### <a name="child-elements"></a>Podřízené prvky

|Prvek|Popis|
|-------------|-----------------|
|[Assembly](../extensibility/assembly-element-visual-studio-templates.md)|Požadovaný element.<br /><br /> Určuje informace o sestavení, který používá šablonu přidáte odkaz na toto sestavení do projektů. Musí obsahovat jeden `Assembly` element v každé `Reference` elementu.|

### <a name="parent-elements"></a>Nadřazené prvky

|Prvek|Popis|
|-------------|-----------------|
|[Odkazy](../extensibility/references-element-visual-studio-templates.md)|Seskupuje odkazy na sestavení, které šablona přidá do projektů.|

## <a name="remarks"></a>Poznámky
 `Reference` je vyžadovaný podřízený prvek `References`.

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
