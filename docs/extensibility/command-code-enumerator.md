---
title: Enumerátor kódu příkazu | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- command code enumerator
- source control plug-ins, command code enumeration
ms.assetid: 5d2c360c-59e4-4da8-bcb4-dd07c7441e40
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 97b856b0c22631b3e4f9b8860f9aaba728e6944d
ms.sourcegitcommit: 752f03977f45169585e407ef719450dbe219b7fc
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/15/2019
ms.locfileid: "56315487"
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
SCC_COMMAND_GET  
Odpovídá [sccget –](../extensibility/sccget-function.md).

SCC_COMMAND_CHECKOUT  
Odpovídá [scccheckout –](../extensibility/scccheckout-function.md).

SCC_COMMAND_CHECKIN  
Odpovídá [scccheckin –](../extensibility/scccheckin-function.md).

SCC_COMMAND_UNCHECKOUT  
Odpovídá [sccuncheckout –](../extensibility/sccuncheckout-function.md).

SCC_COMMAND_ADD  
Odpovídá [sccadd –](../extensibility/sccadd-function.md).

SCC_COMMAND_REMOVE  
Odpovídá [sccremove –](../extensibility/sccremove-function.md).

SCC_COMMAND_DIFF  
Odpovídá [sccdiff –](../extensibility/sccdiff-function.md).

SCC_COMMAND_HISTORY  
Odpovídá [scchistory –](../extensibility/scchistory-function.md).

SCC_COMMAND_RENAME  
Odpovídá [sccrename –](../extensibility/sccrename-function.md).

SCC_COMMAND_PROPERTIES  
Odpovídá [sccproperties –](../extensibility/sccproperties-function.md).

SCC_COMMAND_OPTIONS  
Odpovídá [sccsetoption –](../extensibility/sccsetoption-function.md).

## <a name="see-also"></a>Viz také:
[Ovládací prvek moduly plug-in zdrojového kódu](../extensibility/source-control-plug-ins.md)  
[SccGetCommandOptions](../extensibility/sccgetcommandoptions-function.md)  
[SccPopulateList](../extensibility/sccpopulatelist-function.md)
