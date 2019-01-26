---
title: IDebugSymbolProviderDirect::GetMetaDataImport | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- GetMetaDataImport
- IDebugSymbolProviderDirect::GetMetaDataImport
ms.assetid: b51a492c-af00-4b08-93fb-6c19ee4916aa
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: c69a74e04e0084650e6e99a4afeb6395cffd4ca6
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54951518"
---
# <a name="idebugsymbolproviderdirectgetmetadataimport"></a>IDebugSymbolProviderDirect::GetMetaDataImport
Načte informace o import metadat.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT GetMetaDataImport (  
    GUID*      guid,  
    DWORD      appID,  
    IUnknown** ppImport  
);  
```  
  
```csharp  
int GetMetaDataImport (  
    Guid       guid,  
    uint       appID,  
    out object ppImport  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `guid`  
 [in] Jedinečný identifikátor pro modul.  
  
 `appID`  
 [in] Identifikátor pro doménu aplikace.  
  
 `ppImport`  
 [out] Vrátí objekt, který obsahuje metadata importovat informace.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [IDebugSymbolProviderDirect](../../../extensibility/debugger/reference/idebugsymbolproviderdirect.md)