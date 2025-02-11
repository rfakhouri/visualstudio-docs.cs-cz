---
title: CustomParameters – Element (šablony sady Visual Studio) | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/vstemplate/2005#CustomParameters
helpviewer_keywords:
- CustomParameters element [Visual Studio project templates]
ms.assetid: cf3efc91-1532-4022-bbb8-a18658424fee
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 8089e84f5414798fdf6a4707e8bde65e4df5e0a2
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66350209"
---
# <a name="customparameters-element-visual-studio-templates"></a>CustomParameters – element (šablony sady Visual Studio)
Skupiny vlastní parametry, které mají být předány do Průvodce vytvořením šablony, když Průvodce provede nahrazení parametru.

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

### <a name="child-elements"></a>Podřízené prvky

|Prvek|Popis|
|-------------|-----------------|
|[CustomParameter –](../extensibility/customparameter-element-visual-studio-templates.md)|Volitelný element.<br /><br /> Obsahuje název vlastní parametr a hodnotu použijte, pokud projekt nebo položku je vytvořen z šablony. Může být nula nebo více `CustomParameter` prvky `CustomParameters` elementu.|

### <a name="parent-elements"></a>Nadřazené prvky

|Prvek|Popis|
|-------------|-----------------|
|[TemplateContent](../extensibility/templatecontent-element-visual-studio-templates.md)|Určuje obsah značek šablony.|

## <a name="remarks"></a>Poznámky

## <a name="example"></a>Příklad
 Následující příklad ukazuje, jak použít několik vlastních parametrů v šabloně. Při vytvoření projektu nebo položky ze šablony s následující vlastní parametry všechny výskyty `$color1$` a `$color2$` v šabloně se nahradí soubory `Red` a `Blue`v uvedeném pořadí.

```
<CustomParameters>
    <CustomParameter Name="$color1$" Value="Red"/>
    <CustomParameter Name="$color2$" Value="Blue "/>
</CustomParameters>
```

## <a name="see-also"></a>Viz také:
- [CustomParameter – element (šablony sady Visual Studio)](../extensibility/customparameter-element-visual-studio-templates.md)
- [Parametry šablony](../ide/template-parameters.md)
- [Visual Studio odkaz na schéma šablon](../extensibility/visual-studio-template-schema-reference.md)