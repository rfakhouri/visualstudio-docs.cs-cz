---
title: Appbreakflags – výčet | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- APPBREAKFLAGS
apilocation:
- scrobj.dll
helpviewer_keywords:
- APPBREAKFLAGS constants
ms.assetid: ea8ed80f-2ddb-4800-bb3b-52b76ba6c7a0
caps.latest.revision: 9
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0862e6fc670be6cd3d3ca9fbf67f453aa0772a90
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63009768"
---
# <a name="appbreakflags-enumeration"></a>APPBREAKFLAGS – výčet
Udávají aktuální stav ladění pro aplikace a vlákna.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
enum enum_APPBREAKFLAGS{APPBREAKFLAG_DEBUGGER_BLOCK= 0x00000001,APPBREAKFLAG_DEBUGGER_HALT= 0x00000002,APPBREAKFLAG_STEP= 0x00010000,APPBREAKFLAG_NESTED= 0x00020000,APPBREAKFLAG_STEPTYPE_SOURCE= 0x00000000,APPBREAKFLAG_STEPTYPE_BYTECODE= 0x00100000,APPBREAKFLAG_STEPTYPE_MACHINE= 0x00200000,APPBREAKFLAG_STEPTYPE_MASK= 0x00F00000,APPBREAKFLAG_IN_BREAKPOINT= 0x80000000};  
```  
  
## <a name="members"></a>Členové  
  
|Člen|Value|Popis|  
|------------|-----------|-----------------|  
|APPBREAKFLAG_DEBUGGER_BLOCK|0x00000001|Modul jazyka by mělo dojít okamžitě na všech vláknech s BREAKREASON_DEBUGGER_BLOCK.|  
|APPBREAKFLAG_DEBUGGER_HALT|0x00000002|Jazyk modul by měl s BREAKREASON_DEBUGGER_HALT okamžité přerušení.|  
|APPBREAKFLAG_STEP|0x00010000|Jazyk modul by měl v krokování vlákno s BREAKREASON_STEP okamžité přerušení.|  
|APPBREAKFLAG_NESTED|0x00020000|Aplikace je ve vnořených spuštění na zarážce.|  
|APPBREAKFLAG_STEPTYPE_SOURCE|0x00000000|Ladicí program se krokování na úrovni zdroje.|  
|APPBREAKFLAG_STEPTYPE_BYTECODE|0x00100000|Ladicí program se krokování na úrovni kódu bajtů.|  
|APPBREAKFLAG_STEPTYPE_MACHINE|0x00200000|Ladicí program se krokování na úrovni počítače.|  
|APPBREAKFLAG_STEPTYPE_MASK|0x00F00000|Maska pro které budou zohledňovat si typy kroku.|  
|APPBREAKFLAG_IN_BREAKPOINT|0x80000000|Probíhá zarážku.|  
  
## <a name="remarks"></a>Poznámky  
 Některé příznaky určit, že jazyk moduly by mělo dojít při nejbližší příležitosti, při nastavení další příznaky určení režimu krokování ladicího programu.  
  
## <a name="see-also"></a>Viz také  
 [Konstanty ladicího programu aktivních skriptů, výčty a struktury](../../winscript/reference/active-script-debugger-constants-enumerations-and-structures.md)   
 [BREAKREASON – výčet](../../winscript/reference/breakreason-enumeration.md)