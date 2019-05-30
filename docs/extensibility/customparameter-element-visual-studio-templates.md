---
title: CustomParameter – Element (šablony sady Visual Studio) | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/vstemplate/2005#CustomParameter
helpviewer_keywords:
- CustomParameters element [Visual Studio project templates]
ms.assetid: 743c4489-74ac-403a-bbaa-eed7d785a3ac
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: bbf76edec01cce52768f36dc534d50b580b64230
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66322266"
---
# <a name="customparameter-element-visual-studio-templates"></a>CustomParameter – element (šablony sady Visual Studio)
Obsahuje název vlastní parametr a hodnotu použijte, pokud projekt nebo položku je vytvořen z šablony.

## <a name="syntax"></a>Syntaxe

```
<CustomParameter Name="name" Value="value">
```

## <a name="attributes-and-elements"></a>Atributy a elementy
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.

### <a name="attributes"></a>Atributy

|Atribut|Popis|
|---------------|-----------------|
|`Name`|Povinný parametr. Název parametru Formát pro parametry je $*název*$.|
|`Value`|Povinný parametr. Nahrazující hodnotou parametru.|

### <a name="child-elements"></a>Podřízené prvky
 Žádné

### <a name="parent-elements"></a>Nadřazené prvky

|Prvek|Popis|
|-------------|-----------------|
|[CustomParameters –](../extensibility/customparameters-element-visual-studio-templates.md)|Skupiny vlastní parametry, které mají být předány do Průvodce vytvořením šablony, když Průvodce provede nahrazení parametru.|

## <a name="remarks"></a>Poznámky
 Pokud šablona obsahuje `CustomParameter` prvky, každá instance `Name` nahradí atribut `Value` atribut v vytvořené soubory projektu nebo položky.

## <a name="example"></a>Příklad
 Následující příklad ukazuje, jak použít několik vlastních parametrů v šabloně. Při vytvoření projektu nebo položky ze šablony s následující vlastní parametry všechny výskyty `$color1$` a `$color2$` v šabloně se nahradí soubory `Red` a `Blue`v uvedeném pořadí.

```
<CustomParameters>
    <CustomParameter Name="$color1$" Value="Red"/>
    <CustomParameter Name="$color2$" Value="Blue "/>
</CustomParameters>
```

## <a name="see-also"></a>Viz také:
- [CustomParameters – element (šablony sady Visual Studio)](../extensibility/customparameters-element-visual-studio-templates.md)
- [Parametry šablony](../ide/template-parameters.md)
- [Visual Studio odkaz na schéma šablon](../extensibility/visual-studio-template-schema-reference.md)