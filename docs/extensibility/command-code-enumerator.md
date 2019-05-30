---
title: Enumerátor kódu příkazu | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- command code enumerator
- source control plug-ins, command code enumeration
ms.assetid: 5d2c360c-59e4-4da8-bcb4-dd07c7441e40
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: f4ec14c15bbd0aa6340e30e3156e714ba5f9e074
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66334970"
---
# <a name="command-code-enumerator"></a>Enumerátor kódu příkazu
Tento výčet je používán možnosti [sccgetcommandoptions –](../extensibility/sccgetcommandoptions-function.md) a [sccpopulatelist –](../extensibility/sccpopulatelist-function.md)označíte, příkazu, pro který jsou zadány možnosti.

## <a name="syntax"></a>Syntaxe

```
enum SCCCOMMAND {
   SCC_COMMAND_GET,
   SCC_COMMAND_CHECKOUT,
   SCC_COMMAND_CHECKIN,
   SCC_COMMAND_UNCHECKOUT,
   SCC_COMMAND_ADD,
   SCC_COMMAND_REMOVE,
   SCC_COMMAND_DIFF,
   SCC_COMMAND_HISTORY,
   SCC_COMMAND_RENAME,
   SCC_COMMAND_PROPERTIES,
   SCC_COMMAND_OPTIONS
};
```

## <a name="members"></a>Členové
Odpovídá SCC_COMMAND_GET [sccget –](../extensibility/sccget-function.md).

Odpovídá SCC_COMMAND_CHECKOUT [scccheckout –](../extensibility/scccheckout-function.md).

Odpovídá SCC_COMMAND_CHECKIN [scccheckin –](../extensibility/scccheckin-function.md).

Odpovídá SCC_COMMAND_UNCHECKOUT [sccuncheckout –](../extensibility/sccuncheckout-function.md).

Odpovídá SCC_COMMAND_ADD [sccadd –](../extensibility/sccadd-function.md).

Odpovídá SCC_COMMAND_REMOVE [sccremove –](../extensibility/sccremove-function.md).

Odpovídá SCC_COMMAND_DIFF [sccdiff –](../extensibility/sccdiff-function.md).

Odpovídá SCC_COMMAND_HISTORY [scchistory –](../extensibility/scchistory-function.md).

Odpovídá SCC_COMMAND_RENAME [sccrename –](../extensibility/sccrename-function.md).

Odpovídá SCC_COMMAND_PROPERTIES [sccproperties –](../extensibility/sccproperties-function.md).

Odpovídá SCC_COMMAND_OPTIONS [sccsetoption –](../extensibility/sccsetoption-function.md).

## <a name="see-also"></a>Viz také:
- [Ovládací prvek moduly plug-in zdrojového kódu](../extensibility/source-control-plug-ins.md)
- [SccGetCommandOptions](../extensibility/sccgetcommandoptions-function.md)
- [SccPopulateList](../extensibility/sccpopulatelist-function.md)
