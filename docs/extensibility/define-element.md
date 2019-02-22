---
title: Definování elementu | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- VSCT XML schema elements, Define
- Define element (VSCT XML schema)
ms.assetid: 5aee74e3-de41-4dc6-9618-93e158af56dd
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: ccb14705b4d799e1f7fa6de4728ee8f7fc7b3fb4
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56706636"
---
# <a name="define-element"></a>Define – element
Definuje symbol dvojice název a hodnotu. Tento symbol lze vyhodnotit podmíněné atributy. Další informace najdete v tématu [podmíněné atributy](../extensibility/vsct-xml-schema-conditional-attributes.md). Viz také [Symbols – element](../extensibility/symbols-element.md).

## <a name="syntax"></a>Syntaxe

```
<Define name="Mode" value="Standard" />
```

## <a name="attributes-and-elements"></a>Atributy a elementy
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.

### <a name="attributes"></a>Atributy

|Atribut|Popis|
|---------------|-----------------|
|name|Povinný parametr. Název symbolu:<br /><br /> name="Mode"|
|value|Povinný parametr. Hodnota symbolu:<br /><br /> value="Standard"|
|Podmínka|Volitelné. Další informace najdete v tématu [podmíněné atributy](../extensibility/vsct-xml-schema-conditional-attributes.md).|

### <a name="child-elements"></a>Podřízené prvky
 Žádné

### <a name="parent-elements"></a>Nadřazené prvky

|Prvek|Popis|
|-------------|-----------------|
|[Commandtable – element](../extensibility/commandtable-element.md)|Definuje všechny prvky, které představují příkazy, které poskytuje VSPackage integrovaného vývojového prostředí (IDE). Například položky nabídky, nabídky, panely nástrojů a pole se seznamem.|

## <a name="example"></a>Příklad

```
<Define name="DEMO_UI"/>
<Define name="MODE" value="Standard"/>
```

## <a name="see-also"></a>Viz také:
- [Soubory tabulky (.vsct) příkaz pro Visual Studio](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)