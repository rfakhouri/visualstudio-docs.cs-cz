---
title: IDebugSymbolProviderDirect::GetCurrentModulesInfo | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- IDebugSymbolProviderDirect::GetCurrentModulesInfo
- GetCurrentModulesInfo
ms.assetid: b3b45ed2-ea4e-4389-b78a-11fc9796a6c1
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: ddd56cc5a41bcdc2d362eb5d4157d0a8e9e92c49
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53860228"
---
# <a name="idebugsymbolproviderdirectgetcurrentmodulesinfo"></a>IDebugSymbolProviderDirect::GetCurrentModulesInfo
Načte informace o modulech ve skupině symbol.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT GetCurrentModulesInfo(  
   unsigned long * pCount,  
   GUID *          ppGuids,  
   DWORD *         pADIds,  
   DWORD *         pCurrentState,  
   IUnknown **     ppCDModItfs  
);  
```  
  
```csharp  
int GetCurrentModulesInfo(  
   uint       pCount,  
   Guid       ppGuids,  
   uint       pADIds,  
   uint       pCurrentState,  
   out object ppCDModItfs  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pCount`  
 [in] Počet modulů v `ppGuids` pole.  
  
 `ppGuids`  
 [in] Pole, které obsahuje jedinečné identifikátory pro moduly.  
  
 `pADIds`  
 [in] Identifikátory pro domény aplikace.  
  
 `pCurrentState`  
 [in] Aktuální stav skupiny symbol.  
  
 `ppCDModItfs`  
 [out] Vrátí objekt, který obsahuje moduly ve skupině symbol.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [IDebugSymbolProviderDirect](../../../extensibility/debugger/reference/idebugsymbolproviderdirect.md)