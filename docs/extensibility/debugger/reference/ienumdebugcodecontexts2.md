---
title: IEnumDebugCodeContexts2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IEnumDebugCodeContexts2
helpviewer_keywords: IEnumDebugCodeContexts2
ms.assetid: 72915146-215f-4c99-a034-131b2b474e0e
caps.latest.revision: "13"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: cd6ead902a65a9f3e5e392b1b9dbeed135f326b4
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="ienumdebugcodecontexts2"></a>IEnumDebugCodeContexts2
Toto rozhraní zobrazí kontexty kódu přidružené ladicí relace nebo s konkrétní aplikaci nebo dokumentu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IEnumDebugCodeContexts2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Modul ladění (DE) implementuje toto rozhraní představující seznam kontexty kódu pro konkrétní textu pozice v programu, nebo seznam kontexty kód pro kontext konkrétního dokumentu.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Volání [EnumCodeContexts](../../../extensibility/debugger/reference/idebugprogram2-enumcodecontexts.md) k získání tohoto rozhraní představující seznam kontexty kódu pro zadaný text pozici v programu zdrojový dokument.  
  
 Volání [EnumCodeContexts](../../../extensibility/debugger/reference/idebugdocumentcontext2-enumcodecontexts.md) k získání tohoto rozhraní představující seznam všech kontextů kódu v konkrétní zdrojový dokument.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 Následující tabulka uvádí metody `IEnumDebugCodeContexts2`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[Next](../../../extensibility/debugger/reference/ienumdebugcodecontexts2-next.md)|Načte zadaný počet kontexty kódu v posloupnosti výčtu.|  
|[Přeskočit](../../../extensibility/debugger/reference/ienumdebugcodecontexts2-skip.md)|Přeskočí zadaný počet kontexty kódu v posloupnosti výčtu.|  
|[Resetování](../../../extensibility/debugger/reference/ienumdebugcodecontexts2-reset.md)|Návrat na začátek v sekvenci výčtu.|  
|[Klonování](../../../extensibility/debugger/reference/ienumdebugcodecontexts2-clone.md)|Vytvoří enumerátor, který obsahuje stav výčtu jako aktuální enumerátor.|  
|[GetCount –](../../../extensibility/debugger/reference/ienumdebugcodecontexts2-getcount.md)|Získá počet kontexty kódu v enumerátor.|  
  
## <a name="remarks"></a>Poznámky  
 Visual Studio volání [EnumCodeContexts](../../../extensibility/debugger/reference/idebugprogram2-enumcodecontexts.md) k naplnění seznamu kód kontextů uživatel může vybrat z při nastavení příkaz Další zobrazení nebo zpětný překlad pro zdrojový soubor. Více kontexty kód situace může nastat, například když je spuštěno více instancí šablony C++-style.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Základní rozhraní](../../../extensibility/debugger/reference/core-interfaces.md)   
 [EnumCodeContexts](../../../extensibility/debugger/reference/idebugprogram2-enumcodecontexts.md)   
 [EnumCodeContexts](../../../extensibility/debugger/reference/idebugdocumentcontext2-enumcodecontexts.md)