---
title: ButtonText – Element | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- ButtonText element (VSCT XML schema)
- VSCT XML schema elements, ButtonText
ms.assetid: 56aba884-0356-4894-ae4e-32d3938f6865
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 519ba206b334ef9c955245c152fb14663366472b
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56698830"
---
# <a name="buttontext-element"></a>ButtonText – element
Toto pole umožňuje zadat text, který se zobrazí v různých nabídkách. Ve výchozím nastavení `ButtonText` elementu se zobrazí v nabídce řadiče. `ButtonText` Prvek stane výchozí Pokud další textová pole jsou prázdné. `ButtonText` Element nemůže být prázdný, i když nejsou určeny další textová pole.

## <a name="syntax"></a>Syntaxe

```xml
<ButtonText>My Command</ButtonText>
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
|[Strings – element](../extensibility/strings-element.md)|Seskupí textové prvky, jako například `ButtonText` a `CommandName`.|

## <a name="text-value"></a>Textová hodnota
 Textová hodnota elementu `ButtonText` element obsahuje text, který se zobrazí u položek nabídky, kláves a jiných prvcích uživatelského rozhraní (UI), které mají viditelného textu.

## <a name="see-also"></a>Viz také:
- [Soubory tabulky (.vsct) příkaz pro Visual Studio](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)