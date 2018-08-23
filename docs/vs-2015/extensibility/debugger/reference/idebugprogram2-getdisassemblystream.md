---
title: IDebugProgram2::GetDisassemblyStream | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugProgram2::GetDisassemblyStream
helpviewer_keywords:
- IDebugProgram2::GetDisassemblyStream
ms.assetid: beda0da5-267e-4bf3-96c4-b659d29e2254
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 35c18db634e814bb07a29d858218795fcfa0dbcc
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42668073"
---
# <a name="idebugprogram2getdisassemblystream"></a>IDebugProgram2::GetDisassemblyStream
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [IDebugProgram2::GetDisassemblyStream](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugprogram2-getdisassemblystream).  
  
Získá datový proud zpětný překlad pro tento program nebo součástí tohoto programu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT GetDisassemblyStream(   
   DISASSEMBLY_STREAM_SCOPE   dwScope,  
   IDebugCodeContext2*        pCodeContext,  
   IDebugDisassemblyStream2** ppDisassemblyStream  
);  
```  
  
```csharp  
int GetDisassemblyStream(   
   enum_DISASSEMBLY_STREAM_SCOPE  dwScope,  
   IDebugCodeContext2             pCodeContext,  
   out IDebugDisassemblyStream2   ppDisassemblyStream  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `dwScope`  
 [in] Určuje hodnotu z [DISASSEMBLY_STREAM_SCOPE](../../../extensibility/debugger/reference/disassembly-stream-scope.md) výčet, který definuje rozsah datového proudu zpětný překlad.  
  
 `pCodeContext`  
 [in] [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md) objekt, který reprezentuje pozice kde začít streamu zpětný překlad.  
  
 `ppDisassemblyStream`  
 [out] Vrátí [IDebugDisassemblyStream2](../../../extensibility/debugger/reference/idebugdisassemblystream2.md) objekt, který představuje datový proud zpětný překlad.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby. Vrátí `E_DISASM_NOTSUPPORTED` Pokud pro tuto konkrétní architekturu není podporován převod do strojového jazyka.  
  
## <a name="remarks"></a>Poznámky  
 Pokud `dwScopes` parametr má `DSS_HUGE` příznak [DISASSEMBLY_STREAM_SCOPE](../../../extensibility/debugger/reference/disassembly-stream-scope.md) nastavte výčet a pak zpětného překladu se očekává navrácení velkého počtu pokynů zpětný překlad, například pro celý soubor nebo modulu. Pokud `DSS_HUGE` není nastaven příznak a zpětný má být omezeny na malé oblast obvykle u jedné funkce.  
  
## <a name="see-also"></a>Viz také  
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)   
 [DISASSEMBLY_STREAM_SCOPE](../../../extensibility/debugger/reference/disassembly-stream-scope.md)   
 [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md)   
 [IDebugDisassemblyStream2](../../../extensibility/debugger/reference/idebugdisassemblystream2.md)

