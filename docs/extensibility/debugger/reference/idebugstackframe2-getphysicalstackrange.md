---
title: IDebugStackFrame2::GetPhysicalStackRange | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugStackFrame2::GetPhysicalStackRange
helpviewer_keywords:
- IDebugStackFrame2::GetPhysicalStackRange
ms.assetid: 2f6992e2-ac1c-433f-83b7-a7f83a4ce63d
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: be53b50bc21d81c60f7131e8ed437ecb2ac2f16c
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="idebugstackframe2getphysicalstackrange"></a>IDebugStackFrame2::GetPhysicalStackRange
Získá znázornění závislé na počítač rozsahu fyzické adresy přidružené k rámce zásobníku.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT GetPhysicalStackRange (   
   UINT64* paddrMin,  
   UINT64* paddrMax  
);  
```  
  
```csharp  
int GetPhysicalStackRange (   
   out ulong paddrMin,  
   out ulong paddrMax  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `paddrMin`  
 [out] Vrátí nejnižší fyzické adresy přidružené k této rámce zásobníku.  
  
 `paddrMax`  
 [out] Vrátí nejvyšší fyzické adresy přidružené k této rámce zásobníku.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Informace, tato metoda vrátí správcem ladicí relace (SDM) slouží k seřazení rámce zásobníku.  
  
 Předpokládá se, že zásobníku volání zvětšování dolů, který je, že stále nižší adresy paměti se přidají nové rámce zásobníku. Architektura běhu musíte zadat fyzické zásobníku rozsahy, které odpovídají této předpokladů.  
  
## <a name="see-also"></a>Viz také  
 [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md)