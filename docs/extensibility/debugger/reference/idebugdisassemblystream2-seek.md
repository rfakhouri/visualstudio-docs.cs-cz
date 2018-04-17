---
title: IDebugDisassemblyStream2::Seek | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugDisassemblyStream2::Seek
helpviewer_keywords:
- IDebugDisassemblyStream2::Seek
ms.assetid: afec3008-b1e0-4803-ad24-195dbfb6497e
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 55a8c2c205627130e8dd6dd28f288b2d3dee9d2e
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="idebugdisassemblystream2seek"></a>IDebugDisassemblyStream2::Seek
Přesune čtení ukazatele v datovém proudu zpětný překlad zadaný počet pokyny relativně k zadané pozici.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT Seek(   
   SEEK_START          dwSeekStart,  
   IDebugCodeContext2* pCodeContext,  
   UINT64              uCodeLocationId,  
   INT64               iInstructions  
);  
```  
  
```csharp  
int Seek(   
   enum_SEEK_START    dwSeekStart,  
   IDebugCodeContext2 pCodeContext,  
   ulong              uCodeLocationId,  
   long               iInstructions  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `dwSeekStart`  
 [v] Hodnota z [SEEK_START](../../../extensibility/debugger/reference/seek-start.md) výčet, který určuje relativní pozici k zahájení procesu seek.  
  
 `pCodeContext`  
 [v] [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md) objekt reprezentující kontextu kód, který vyhledávací operaci je vzhledem k. Tento parametr se používá pouze v případě `dwSeekStart`  =  `SEEK_START_CODECONTEXT`, jinak hodnota tohoto parametru je ignorován a může mít hodnotu null.  
  
 `uCodeLocationId`  
 [v] Umístění identifikátor kód, který vyhledávací operaci je vzhledem k. Tento parametr je použit, pokud `dwSeekStart`  =  `SEEK_START_CODELOCID`, jinak hodnota tohoto parametru je ignorován a může být nastaven na hodnotu 0. Naleznete v části poznámky [GetCodeLocationId](../../../extensibility/debugger/reference/idebugdisassemblystream2-getcodelocationid.md) metoda popis identifikátor umístění kódu.  
  
 `iInstructions`  
 [v] Počet vzhledem ke pozici v zadané lokalitě `dwSeekStart`. Tato hodnota může být záporné zpětné přesunout.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`. Vrátí `S_FALSE` Pokud pozice hledání byl do bodu v seznamu dostupných pokynů. Jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Pokud hledání do polohy před začátkem v seznamu, čtení pozice je nastavena na první instrukce v seznamu. Pokud najdete byla na místo na konci seznamu, čtení pozice je nastavena na poslední instrukce v seznamu.  
  
## <a name="see-also"></a>Viz také  
 [IDebugDisassemblyStream2](../../../extensibility/debugger/reference/idebugdisassemblystream2.md)   
 [SEEK_START](../../../extensibility/debugger/reference/seek-start.md)   
 [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md)   
 [GetCodeLocationId](../../../extensibility/debugger/reference/idebugdisassemblystream2-getcodelocationid.md)