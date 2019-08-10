---
title: Listovat moduly – příkaz
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- debug.listmodules
helpviewer_keywords:
- Debug.ListModules command
- ListModules command
- list modules command
ms.assetid: 3cb73774-6ac0-43b2-b781-75ed47175bfd
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 89be89bb3befa6f6ab9e67f6e98ae4d7b1b94e64
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/09/2019
ms.locfileid: "68926207"
---
# <a name="list-modules-command"></a>Listovat moduly – příkaz
Seznam modulů pro aktuální proces.

## <a name="syntax"></a>Syntaxe

```
Debug.ListModules [/Address:yes|no] [/Name:yes|no] [/Order:yes|no]
[/Path:yes|no] [/Process:yes|no] [/SymbolFile:yes|no]
[/SymbolStatus:yes|no] [/Timestamp:yes|no] [/Version:yes|no]
```

#### <a name="parameters"></a>Parametry
Adresáře`yes|no`

Volitelné. Určuje, zda se mají zobrazovat adresy paměti modulů. Výchozí hodnota je `yes`.

Název`yes|no`

Volitelné. Určuje, zda se mají zobrazovat názvy modulů. Výchozí hodnota je `yes`.

Za`yes|no`

Volitelné. Určuje, zda se má zobrazovat pořadí modulů. Výchozí hodnota je `no`.

Dílčí`yes|no`

Volitelné. Určuje, zda se mají zobrazovat cesty modulů. Výchozí hodnota je `yes`.

Přihlášení`yes|no`

Volitelné. Určuje, zda se mají zobrazit procesy modulů. Výchozí hodnota je `no`.

SymbolFile`yes|no`

Volitelné. Určuje, zda se mají zobrazovat soubory symbolů modulů. Výchozí hodnota je `no`.

SymbolStatus`yes|no`

Volitelné. Určuje, zda se mají zobrazovat stavy symbolů modulů. Výchozí hodnota je `yes`.

Časové razítko`yes|no`

Volitelné. Určuje, zda se mají zobrazovat časová razítka modulů. Výchozí hodnota je `no`.

Znění`yes|no`

Volitelné. Určuje, zda se mají zobrazovat verze modulů. Výchozí hodnota je `no`.

## <a name="example"></a>Příklad
V tomto příkladu jsou uvedeny názvy modulů, adresy a časová razítka pro aktuální proces.

```
Debug.ListModules /Address:yes /Name:yes /Order:no /Path:no /Process:no /SymbolFile:no /SymbolStatus:no /Timestamp:yes /Version:no
```

## <a name="see-also"></a>Viz také

- [Příkazy sady Visual Studio](../../ide/reference/visual-studio-commands.md)
- [Příkazové okno](../../ide/reference/command-window.md)
- [Postupy: Použití okna Moduly](../../debugger/how-to-use-the-modules-window.md)