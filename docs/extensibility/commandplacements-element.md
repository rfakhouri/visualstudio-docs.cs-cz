---
title: Commandplacements – Element | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- CommandPlacements
helpviewer_keywords:
- CommandPlacements element (VSCT XML schema)
- VSCT XML schema elements, CommandPlacements
ms.assetid: 78a5724a-3b9f-4c78-9c0d-8faa3924f81c
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: bb22359c936caacef81f4c9b81993a46d47ccc0b
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66341886"
---
# <a name="commandplacements-element"></a>Commandplacements – element
Commandplacements – element seskupí commandplacement – elementy a ostatní commandplacements – seskupení.

 Commandplacements – element je volitelné. Pokud v nějakém sekundárním umístění musí obsahovat žádné příkazy, skupiny nebo nabídky, není potřeba zahrnovat v této části vašeho *.vsct* souboru.

## <a name="syntax"></a>Syntaxe

```xml
<CommandPlacements>
  <CommandPlacement>... </CommandPlacement>
  <CommandPlacement>... </CommandPlacement>
</CommandPlacements>
```

## <a name="attributes-and-elements"></a>Atributy a elementy
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.

### <a name="attributes"></a>Atributy

|Atribut|Popis|
|---------------|-----------------|
|Podmínka|Volitelné. Zobrazit [podmíněné atributy](../extensibility/vsct-xml-schema-conditional-attributes.md).|

### <a name="child-elements"></a>Podřízené prvky

|Prvek|Popis|
|-------------|-----------------|
|Commandplacements –|Seskupí commandplacement – elementy a ostatní commandplacements – seskupení.|
|[Commandplacement – element](../extensibility/commandplacement-element.md)|Umožňuje tlačítka, skupiny a nabídek, které mají být zahrnuty do více než jedné skupině nebo v nabídce.|

### <a name="parent-elements"></a>Nadřazené prvky

|Prvek|Popis|
|-------------|-----------------|
|[Commandtable – element](../extensibility/commandtable-element.md)|Definuje všechny prvky, které představují příkazy.|

## <a name="example"></a>Příklad

```xml
<CommandPlacements>
  <CommandPlacement guid="guidWidgetPackage" id="cmdidInsertOptions"
    priority="0x0300">
    <Parent guid="cmdGuidWidgetCommands" id="menuIDEditWidget"/>
  </CommandPlacement>
</CommandPlacements>
```

## <a name="see-also"></a>Viz také:
- [Commandplacement – element](../extensibility/commandplacement-element.md)
- [Soubory tabulky (.vsct) příkaz pro Visual Studio](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)