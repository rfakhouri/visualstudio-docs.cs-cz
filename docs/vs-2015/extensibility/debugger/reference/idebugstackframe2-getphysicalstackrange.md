---
title: IDebugStackFrame2::GetPhysicalStackRange | Dokumentace Microsoftu
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
- IDebugStackFrame2::GetPhysicalStackRange
helpviewer_keywords:
- IDebugStackFrame2::GetPhysicalStackRange
ms.assetid: 2f6992e2-ac1c-433f-83b7-a7f83a4ce63d
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 8c48943ba68bf4090fd6d2b65b3ffba1f5018af2
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42669651"
---
# <a name="idebugstackframe2getphysicalstackrange"></a>IDebugStackFrame2::GetPhysicalStackRange
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [IDebugStackFrame2::GetPhysicalStackRange](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugstackframe2-getphysicalstackrange).  
  
Získá vyjádření závislé na počítači rozsahu fyzické adresy přidružený blok zásobníku.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
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
 [out] Vrátí nejnižší fyzické adresy přidružené k tento rámec zásobníku.  
  
 `paddrMax`  
 [out] Vrátí nejvyšší fyzické adresy přidružené k tento rámec zásobníku.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Informace o vrácený touto metodou používá správce ladění relace (SDM) řazení zásobníku.  
  
 Předpokládá se, že zásobník volání roste dolů, to znamená, že jsou přidány nové bloky zásobníku stále nižší adresy paměti. Za běhu architektury musíte zadat rozsahy adres fyzického zásobníku, které odpovídají tento předpoklad.  
  
## <a name="see-also"></a>Viz také  
 [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md)

