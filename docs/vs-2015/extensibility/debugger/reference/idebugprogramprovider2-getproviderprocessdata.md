---
title: IDebugProgramProvider2::GetProviderProcessData | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugProgramProvider2::GetProviderProcessData
helpviewer_keywords:
- IDebugProgramProvider2::GetProviderProcessData
ms.assetid: 90cf7b7f-53d2-487e-b793-94501a6e24dd
caps.latest.revision: 13
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: a50faf4531a098dde544adcffe535ed26e9c5cd8
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68148518"
---
# <a name="idebugprogramprovider2getproviderprocessdata"></a>IDebugProgramProvider2::GetProviderProcessData
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Načte seznam spuštěných aplikací z určeného procesu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT GetProviderProcessData(  
   PROVIDER_FLAGS         Flags,  
   IDebugDefaultPort2*    pPort,  
   AD_PROCESS_ID          processId,  
   CONST_GUID_ARRAY       EngineFilter,  
   PROVIDER_PROCESS_DATA* pProcess  
);  
```  
  
```csharp  
int GetProviderProcessData(  
   enum_PROVIDER_FLAGS     Flags,  
   IDebugDefaultPort2      pPort,  
   AD_PROCESS_ID           ProcessId,  
   CONST_GUID_ARRAY        EngineFilter,  
   PROVIDER_PROCESS_DATA[] pProcess  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `Flags`  
 [in] Kombinace příznaků z [PROVIDER_FLAGS](../../../extensibility/debugger/reference/provider-flags.md) výčtu. Následující příznaky jsou typické pro toto volání:  
  
|Příznak|Popis|  
|----------|-----------------|  
|`PFLAG_REMOTE_PORT`|Volající běží na vzdáleném počítači.|  
|`PFLAG_DEBUGGEE`|Volající je momentálně laděna (Další informace o zařazování bude vrácen pro každý uzel).|  
|`PFLAG_ATTACHED_TO_DEBUGGEE`|Volající, byl připojený k ale není spuštěn pomocí ladicího programu.|  
|`PFLAG_GET_PROGRAM_NODES`|Volající žádá seznam program uzlů, které se mají vrátit.|  
  
 `pPort`  
 [in] Port volající proces běží na.  
  
 `processId`  
 [in] [AD_PROCESS_ID](../../../extensibility/debugger/reference/ad-process-id.md) struktura obsahující dotyčný ID procesu, který obsahuje program.  
  
 `EngineFilter`  
 [in] Pole identifikátorů GUID pro ladicí stroj přiřazené pro ladění tohoto procesu (ty se používají k filtrování sady, které jsou vráceny ve skutečnosti na základě co podporují zadané moduly; Pokud nejsou zadány žádné moduly, a vrátí se všechny programy).  
  
 `pProcess`  
 [out] A [PROVIDER_PROCESS_DATA](../../../extensibility/debugger/reference/provider-process-data.md) struktura, která se vyplní požadované informace.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda je obvykle volána postup získání seznamu sad programy spuštěné v tomto procesu. Vrácené informace se seznam [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md) objekty.  
  
## <a name="see-also"></a>Viz také  
 [IDebugProgramProvider2](../../../extensibility/debugger/reference/idebugprogramprovider2.md)   
 [IDebugDefaultPort2](../../../extensibility/debugger/reference/idebugdefaultport2.md)   
 [AD_PROCESS_ID](../../../extensibility/debugger/reference/ad-process-id.md)   
 [CONST_GUID_ARRAY](../../../extensibility/debugger/reference/const-guid-array.md)   
 [PROVIDER_FLAGS](../../../extensibility/debugger/reference/provider-flags.md)   
 [PROVIDER_PROCESS_DATA](../../../extensibility/debugger/reference/provider-process-data.md)   
 [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md)
