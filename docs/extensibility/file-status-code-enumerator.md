---
title: Soubor enumerátor kód stavu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- named constants, SccStatus enumerator
- source control plug-ins, file status enumeration
- SccStatus enumerator
- file status code enumerator
ms.assetid: 5c37876b-c83c-4ca1-837b-57cd465a879a
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: b3415440c80fcaa88edbecee924a118f82a9dd99
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="file-status-code-enumerator"></a>Enumerátor kód stavu souboru
`SccStatus` Enumerátor obsahuje pojmenované konstantní hodnoty, které určují stav souboru v systému správy zdrojů. Tento výčet je používán [SccQueryInfo](../extensibility/sccqueryinfo-function.md) a `POPLISTFUNC` funkce zpětného volání (viz [POPLISTFUNC](../extensibility/poplistfunc.md) podrobnosti).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
enum SccStatus {  
   SCC_STATUS_INVALID          = -1L,  
   SCC_STATUS_NOTCONTROLLED    = 0x0000L,  
   SCC_STATUS_CONTROLLED       = 0x0001L,  
   SCC_STATUS_CHECKEDOUT       = 0x0002L,  
   SCC_STATUS_OUTOTHER         = 0x0004L,  
   SCC_STATUS_OUTEXCLUSIVE     = 0x0008L,  
   SCC_STATUS_OUTMULTIPLE      = 0x0010L,  
   SCC_STATUS_OUTOFDATE        = 0x0020L,  
   SCC_STATUS_DELETED          = 0x0040L,  
   SCC_STATUS_LOCKED           = 0x0080L,  
   SCC_STATUS_MERGED           = 0x0100L,  
   SCC_STATUS_SHARED           = 0x0200L,  
   SCC_STATUS_PINNED           = 0x0400L,  
   SCC_STATUS_MODIFIED         = 0x0800L,  
   SCC_STATUS_OUTBYUSER        = 0x1000L  
   SCC_STATUS_NOMERGE          = 0x2000L  
   SCC_STATUS_RESERVED_1       = 0x4000L  
   SCC_STATUS_RESERVED_2       = 0x8000L  
};  
```  
  
## <a name="members"></a>Členové  
 SCC_STATUS_INVALID  
 Nepodařilo se získat stav; Nespoléhejte na něm.  
  
 SCC_STATUS_NOTCONTROLLED  
 Soubor není ve správě zdrojového kódu.  
  
 SCC_STATUS_CONTROLLED  
 Soubor je ve správě zdrojového kódu.  
  
 SCC_STATUS_CHECKEDOUT  
 Rezervovaný aktuální uživatel na místním disku.  
  
 SCC_STATUS_OUTOTHER  
 Soubor je rezervovaný jiným uživatelem.  
  
 SCC_STATUS_OUTEXCLUSIVE  
 Soubor je výhradně rezervovaný.  
  
 SCC_STATUS_OUTMULTIPLE  
 Soubor je rezervovaný více než jeden uživatel.  
  
 SCC_STATUS_OUTOFDATE  
 Soubor není nejnovější.  
  
 SCC_STATUS_DELETED  
 Soubor byl odstraněn z projektu.  
  
 SCC_STATUS_LOCKED  
 Soubor je uzamčený; žádné další verze povoleny.  
  
 SCC_STATUS_MERGED  
 Soubor byla sloučit, ale ještě nebyla pevné nebo ověření.  
  
 SCC_STATUS_SHARED  
 Soubor je sdílený mezi projekty.  
  
 SCC_STATUS_PINNED  
 Sdílení souboru na explicitní verzi.  
  
 SCC_STATUS_MODIFIED  
 Soubor byl změněn nebo poškozený nebo došlo k porušení.  
  
 SCC_STATUS_OUTBYUSER  
 Soubor je rezervovaný aktuálního uživatele.  
  
 SCC_STATUS_NOMERGE  
 Soubor může být nikdy sloučit s a nemusí být uložen před GET.  
  
 SCC_STATUS_RESERVED_1  
 Vyhrazeno pro interní použití.  
  
 SCC_STATUS_RESERVED_2  
 Vyhrazeno pro interní použití.  
  
## <a name="see-also"></a>Viz také  
 [Moduly plug-in programu zdroj ovládacího prvku](../extensibility/source-control-plug-ins.md)   
 [SccQueryInfo](../extensibility/sccqueryinfo-function.md)   
 [POPLISTFUNC](../extensibility/poplistfunc.md)