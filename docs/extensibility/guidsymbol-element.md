---
title: Guidsymbol – Element | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- VSCT XML schema elements, GuidSymbol
- GuidSymbol element (VSCT XML schema)
ms.assetid: 11fb3545-8974-4776-9a54-6b6e7739ae31
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: fe1d3b39e07862192082eb4950bd268dfcebd175
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62863023"
---
# <a name="guidsymbol-element"></a>Guidsymbol – element
`GuidSymbol` Prvek obsahuje GUID GUID:ID pár, který představuje nabídky, skupiny nebo příkaz. ID pochází z `IDSymbol` prvek `GuidSymbol` elementu. `GuidSymbol` Element má `name` atribut, který poskytuje popisný název pro identifikátor GUID, který je součástí `value` atribut.

## <a name="syntax"></a>Syntaxe

```xml
<GuidSymbol name="guidMyCommandSet" value="{xxxxxxxxxxxxx-xxxx-xxxx-xxxxxxxxxxxx}">
  <IDSymbol>... </IDSymbol>
  <IDSymbol>... </IDSymbol>
</GuidSymbol>
```

## <a name="attributes-and-elements"></a>Atributy a elementy
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.

### <a name="attributes"></a>Atributy

|Atribut|Popis|
|---------------|-----------------|
|name|Povinný parametr. Název symbolu identifikátor GUID.|
|value|Povinný parametr. Identifikátor GUID symbol identifikátor GUID.|

### <a name="child-elements"></a>Podřízené prvky

|Prvek|Popis|
|-------------|-----------------|
|[Idsymbol – element](../extensibility/idsymbol-element.md)|Obsahuje ID GUID:ID pár, který představuje nabídky, skupiny nebo příkaz.|

### <a name="parent-elements"></a>Nadřazené prvky

|Prvek|Popis|
|-------------|-----------------|
|[Symbols – element](../extensibility/symbols-element.md)|Skupiny `GuidSymbol` prvky *.vsct* souboru.|

## <a name="remarks"></a>Poznámky
 Obvykle *.vsct* soubor obsahuje tři `GuidSymbol` prvků v jeho `Symbols` části, z nich je pro balíček samotné, jeden pro sadu příkazů (kolekce nabídky, skupiny a příkazy, že balíček je k dispozici) a jeden pro rastrové obrázky, které poskytují ikony pro tlačítka a další vizuální komponenty. Každý `IDSymbol` element v danou `GuidSymbol` element musí mít jedinečný `value`. Ale `IDSymbol` prvky, které mají stejné hodnoty může existovat v balíčku tak dlouho, dokud mají jiné nadřazené položky.

## <a name="see-also"></a>Viz také:
- [Soubory tabulky (.vsct) příkaz pro Visual Studio](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)