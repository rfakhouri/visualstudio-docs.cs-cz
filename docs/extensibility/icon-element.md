---
title: Icon – Element | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- VSCT XML schema elements, Icon
- Icon element (VSCT XML schema)
ms.assetid: 73c58fe3-d53c-4f4e-b025-29567c6cbb7c
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: dd56391084788729c0f8439728f9afffd59da946
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66311244"
---
# <a name="icon-element"></a>Icon – element
Atribut guid ikonu značky je identifikátor guid definované rastrový obrázek. `id` Atribut vybere slotu v pruhu rastrového obrázku. Tento element je volitelný. Pokud tento prvek není zahrnuta hodnota **guidOfficeIcon:msotcidNoIcon** bude implicitní.

## <a name="syntax"></a>Syntaxe

```xml
<Icon guid="guidImages" id="bmpPic1" />
```

## <a name="attributes-and-elements"></a>Atributy a elementy
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.

### <a name="attributes"></a>Atributy

|Atribut|Popis|
|---------------|-----------------|
|identifikátor GUID|Povinný parametr. Identifikátor guid definované rastrový obrázek.|
|id|Povinný parametr. Vybere slotu v pruhu rastrového obrázku.|

### <a name="child-elements"></a>Podřízené prvky

|Prvek|Popis|
|-------------|-----------------|
|Žádné|Žádné|

### <a name="parent-elements"></a>Nadřazené prvky

|Prvek|Popis|
|-------------|-----------------|
|[Buttons – element](../extensibility/buttons-element.md)||

## <a name="see-also"></a>Viz také:
- [Soubory tabulky (.vsct) příkaz pro Visual Studio](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)