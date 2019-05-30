---
title: Enumerátor kódu stavu souboru | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- named constants, SccStatus enumerator
- source control plug-ins, file status enumeration
- SccStatus enumerator
- file status code enumerator
ms.assetid: 5c37876b-c83c-4ca1-837b-57cd465a879a
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 94bd9ff93872139fc056c4c8bb7a59191616919e
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66342688"
---
# <a name="file-status-code-enumerator"></a>Enumerátor kódu stavu souboru
`SccStatus` Obsahuje čítače výčtu s názvem konstantní hodnoty, které určují stav souboru v systému správy zdrojového kódu. Tento výčet je používán [sccqueryinfo –](../extensibility/sccqueryinfo-function.md) a `POPLISTFUNC` funkce zpětného volání (viz [POPLISTFUNC](../extensibility/poplistfunc.md) podrobnosti).

## <a name="syntax"></a>Syntaxe

```
enum SccStatus {
   SCC_STATUS_INVALID          = -1L,
   SCC_STATUS_NOTCONTROLLED    = 0x0000L,
   SCC_STATUS_CONTROLLED       = 0x0001L,
   SCC_STATUS_CHECKEDOUT       = 0x0002L,
   SCC_STATUS_OUTOTHER         = 0x0004L,
   SCC_STATUS_OUTEXCLUSIVE     = 0x0008L,
   SCC_STATUS_OUTMULTIPLE      = 0x0010L,
   SCC_STATUS_OUTOFDATE        = 0x0020L,
   SCC_STATUS_DELETED          = 0x0040L,
   SCC_STATUS_LOCKED           = 0x0080L,
   SCC_STATUS_MERGED           = 0x0100L,
   SCC_STATUS_SHARED           = 0x0200L,
   SCC_STATUS_PINNED           = 0x0400L,
   SCC_STATUS_MODIFIED         = 0x0800L,
   SCC_STATUS_OUTBYUSER        = 0x1000L
   SCC_STATUS_NOMERGE          = 0x2000L
   SCC_STATUS_RESERVED_1       = 0x4000L
   SCC_STATUS_RESERVED_2       = 0x8000L
};
```

## <a name="members"></a>Členové
 Nebylo možné získat stav SCC_STATUS_INVALID; Nespoléhejte na to.

 SCC_STATUS_NOTCONTROLLED soubor není pod správou zdrojových kódů.

 SCC_STATUS_CONTROLLED soubor podléhá správě zdrojového kódu.

 SCC_STATUS_CHECKEDOUT kontroluje navýšení kapacity o aktuálního uživatele na místním disku.

 Soubor SCC_STATUS_OUTOTHER je rezervována jiným uživatelem.

 SCC_STATUS_OUTEXCLUSIVE soubor je exkluzivně zaregistrován.

 Soubor SCC_STATUS_OUTMULTIPLE je rezervován více než jeden uživatel.

 SCC_STATUS_OUTOFDATE soubor není nejnovější.

 SCC_STATUS_DELETED soubor byl odstraněn z projektu.

 SCC_STATUS_LOCKED soubor je uzamčen; žádné další verze povolené.

 Soubor SCC_STATUS_MERGED byla sloučit, ale dosud opraveno/ověření.

 SCC_STATUS_SHARED souborů se sdílí mezi projekty.

 Sdílení souboru SCC_STATUS_PINNED explicitní verzi.

 SCC_STATUS_MODIFIED soubor se upravil/nefunkční/došlo k porušení.

 Soubor SCC_STATUS_OUTBYUSER je rezervována aktuálního uživatele.

 Soubor SCC_STATUS_NOMERGE nikdy sloučením s a před GET nemusí být uložen.

 SCC_STATUS_RESERVED_1 vyhrazený pro interní použití.

 SCC_STATUS_RESERVED_2 vyhrazený pro interní použití.

## <a name="see-also"></a>Viz také:
- [Ovládací prvek moduly plug-in zdrojového kódu](../extensibility/source-control-plug-ins.md)
- [SccQueryInfo](../extensibility/sccqueryinfo-function.md)
- [POPLISTFUNC](../extensibility/poplistfunc.md)