---
title: Sdkreference – Element (šablony sady Visual Studio) | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.technology: vs-ide-general
ms.topic: reference
ms.assetid: 72c8b352-0b7a-42b3-ba5d-2a2d1e90c34b
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: da11d9e01802bff8162b2767444c7a1d225200a0
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66338485"
---
# <a name="sdkreference-element-visual-studio-templates"></a>SDKReference – element (šablony sady Visual Studio)
Určuje, že šablonu položky používá odkaz na sadu SDK.

## <a name="syntax"></a>Syntaxe

```xml
<VSTemplate>
    <TemplateContent>
        <References>
            <Reference>
                <SDKReference>SDKname</SDKReference>
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
|[Referenční informace](../extensibility/reference-element-visual-studio-templates.md)|Určuje odkaz na sestavení přidat, pokud je položka přidána do projektu.|

## <a name="text-value"></a>Textová hodnota
 Je vyžadována textová hodnota.

## <a name="remarks"></a>Poznámky
 Tento text určuje odkazu sady SDK do projektu přidat při vytváření instance šablony položky.

```xml
<VSTemplate Version="3.0.0" xmlns="http://schemas.microsoft.com/developer/vstemplate/2005" Type="Item">
    <TemplateData> . . . </TemplateData>
    <TemplateContent>
        <References>
            <Reference>
                <SDKReference>Microsoft Visual C++ Runtime Package, Version=11.0.0.0</SDKReference>
...
```

## <a name="see-also"></a>Viz také
- [References – element (šablony sady Visual Studio)](../extensibility/references-element-visual-studio-templates.md)
- [Reference – element (šablony sady Visual Studio)](../extensibility/reference-element-visual-studio-templates.md)
- [Vytváření šablon projektů a položek](../ide/creating-project-and-item-templates.md)
- [Odkaz na schéma šablon sady Visual Studio](../extensibility/visual-studio-template-schema-reference.md)