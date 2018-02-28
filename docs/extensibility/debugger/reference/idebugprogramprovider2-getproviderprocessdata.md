---
title: IDebugProgramProvider2::GetProviderProcessData | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugProgramProvider2::GetProviderProcessData
helpviewer_keywords:
- IDebugProgramProvider2::GetProviderProcessData
ms.assetid: 90cf7b7f-53d2-487e-b793-94501a6e24dd
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: e94e0606256eda3fb8cdcade90979342d078e125
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idebugprogramprovider2getproviderprocessdata"></a>IDebugProgramProvider2::GetProviderProcessData
Načte seznam spuštěných programy z zadaný procesu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT GetProviderProcessData(  
   PROVIDER_FLAGS         Flags,  
   IDebugDefaultPort2*    pPort,  
   AD_PROCESS_ID          processId,  
   CONST_GUID_ARRAY       EngineFilter,  
   PROVIDER_PROCESS_DATA* pProcess  
);  
```  
  
```csharp  
int GetProviderProcessData(  
   enum_PROVIDER_FLAGS     Flags,  
   IDebugDefaultPort2      pPort,  
   AD_PROCESS_ID           ProcessId,  
   CONST_GUID_ARRAY        EngineFilter,  
   PROVIDER_PROCESS_DATA[] pProcess  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `Flags`  
 [v] Kombinace příznaků z [PROVIDER_FLAGS](../../../extensibility/debugger/reference/provider-flags.md) výčtu. Následující příznaky jsou typické pro toto volání:  
  
|Příznak|Popis|  
|----------|-----------------|  
|`PFLAG_REMOTE_PORT`|Volající běží na vzdáleném počítači.|  
|`PFLAG_DEBUGGEE`|Volající je právě laděn (Další informace o zařazování bude vrácen pro každý uzel).|  
|`PFLAG_ATTACHED_TO_DEBUGGEE`|Volající byl připojen k ale není spuštěn ladicí program.|  
|`PFLAG_GET_PROGRAM_NODES`|Volající se žádostí o seznam uzlů program má být vrácen.|  
  
 `pPort`  
 [v] Port volající proces běží na.  
  
 `processId`  
 [v] [AD_PROCESS_ID](../../../extensibility/debugger/reference/ad-process-id.md) struktura, která uchovává ID procesu, který obsahuje program dotyčném.  
  
 `EngineFilter`  
 [v] Pole identifikátory GUID pro ladění moduly přiřazené k ladění tento proces (ty se používají k filtrování programy, které jsou vráceny ve skutečnosti na základě co zadaný stroje podporují; Pokud nejsou zadány žádné moduly, pak budou vráceny všechny programy).  
  
 `pProcess`  
 [out] A [PROVIDER_PROCESS_DATA](../../../extensibility/debugger/reference/provider-process-data.md) struktura, která obsahuje požadované informace.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda je volána normálně postup získání seznamu programům spuštěným v tomto procesu. Vrácené informace je seznam [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md) objekty.  
  
## <a name="see-also"></a>Viz také  
 [IDebugProgramProvider2](../../../extensibility/debugger/reference/idebugprogramprovider2.md)   
 [IDebugDefaultPort2](../../../extensibility/debugger/reference/idebugdefaultport2.md)   
 [AD_PROCESS_ID](../../../extensibility/debugger/reference/ad-process-id.md)   
 [CONST_GUID_ARRAY](../../../extensibility/debugger/reference/const-guid-array.md)   
 [PROVIDER_FLAGS](../../../extensibility/debugger/reference/provider-flags.md)   
 [PROVIDER_PROCESS_DATA](../../../extensibility/debugger/reference/provider-process-data.md)   
 [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md)