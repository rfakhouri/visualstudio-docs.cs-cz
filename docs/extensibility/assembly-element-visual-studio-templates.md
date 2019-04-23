---
title: Assembly – Element (šablony sady Visual Studio) | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/vstemplate/2005#Assembly
helpviewer_keywords:
- Assembly element [Visual Studio templates]
- <Assembly> element [Visual Studio templates]
ms.assetid: 9242f76a-1273-4b8a-8f26-6606f91829ef
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 5caa0804ae4d90a23ae59195d2e610653437babe
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60079341"
---
# <a name="assembly-element-visual-studio-templates"></a>Assembly – element (šablony sady Visual Studio)
Určuje informace o sestavení, který používá šablonu přidáte odkaz na toto sestavení do projektů.

 \<Vstemplate – > \<TemplateContent > \<odkazy > \<odkaz > \<sestavení >

## <a name="syntax"></a>Syntaxe

```
<Assembly> AssemblyName </Assembly>
```

## <a name="attributes-and-elements"></a>Atributy a elementy
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.

### <a name="attributes"></a>Atributy
 Žádné

### <a name="child-elements"></a>Podřízené prvky
 Žádné

### <a name="parent-elements"></a>Nadřazené prvky

|Prvek|Popis|
|-------------|-----------------|
|[Referenční informace](../extensibility/reference-element-visual-studio-templates.md)|Určuje odkaz na sestavení přidat, pokud je položka přidána do projektu.|

## <a name="text-value"></a>Textová hodnota
 Je vyžadována textová hodnota.

 Tento text určuje sestavení, které chcete přidat do projektu při vytváření instance šablony položky. Tento název sestavení musí být zadán v jednom z následujících způsobů:

- Jako název úplné sestavení. Příklad:

    ```
    <Assembly>
        MyAssembly, Version=1.0.3300.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a, Custom = null.
    </Assembly>
    ```

- Jako jednoduchý text odkazu. Příklad:

    ```
    <Assembly> System </Assembly>
    ```

## <a name="remarks"></a>Poznámky
 `Assembly` je vyžadovaný podřízený prvek `Reference`.

 `Reference`, `References,` a `Assembly` prvky lze použít pouze v *.vstemplate* soubory, které mají `Type` hodnotu atributu `Item`.

## <a name="example"></a>Příklad
 Následující příklad ukazuje, `TemplateContent` elementu šablony položky. Přidá odkazy na tato konfigurace XML *System.dll* a *System.Data.dll* sestavení.

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

## <a name="see-also"></a>Viz také:
- [Visual Studio odkaz na schéma šablon](../extensibility/visual-studio-template-schema-reference.md)
- [Vytváření šablon projektů a položek](../ide/creating-project-and-item-templates.md)