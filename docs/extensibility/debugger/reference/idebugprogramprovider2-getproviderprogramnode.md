---
title: IDebugProgramProvider2::GetProviderProgramNode | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugProgramProvider2::GetProviderProgramNode
helpviewer_keywords: IDebugProgramProvider2::GetProviderProgramNode
ms.assetid: e62e8e83-acbb-4c52-aedf-ffbd4670db29
caps.latest.revision: "13"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 4ad5540d1f93e44b069cac4873880e9db9d96919
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="idebugprogramprovider2getproviderprogramnode"></a>IDebugProgramProvider2::GetProviderProgramNode
Načte uzlu program pro určitý program.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT GetProviderProgramNode(  
   PROVIDER_FLAGS       Flags,  
   IDebugDefaultPort2*  pPort,  
   AD_PROCESS_ID        processId,  
   REFGUID              guidEngine,  
   UINT64               programId,  
   IDebugProgramNode2** ppProgramNode  
);  
```  
  
```csharp  
int GetProviderProgramNode(  
   enum_PROVIDER_FLAGS    Flags,  
   IDebugDefaultPort2     pPort,  
   AD_PROCESS_ID          ProcessId,  
   ref Guid               guidEngine,  
   ulong                  programId,  
   out IDebugProgramNode2 ppProgramNode  
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
  
 `pPort`  
 [v] Port volající proces běží na.  
  
 `processId`  
 [v] [AD_PROCESS_ID](../../../extensibility/debugger/reference/ad-process-id.md) struktura, která uchovává ID procesu, který obsahuje program dotyčném.  
  
 `guidEngine`  
 [v] Identifikátor GUID modulu ladicí program připojený k (pokud existuje).  
  
 `programId`  
 [v] ID programu, pro které chcete získat uzlu programu.  
  
 `ppProgramNode`  
 [out] [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md) objektu, který představuje uzel pro požadovaný program.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [IDebugProgramProvider2](../../../extensibility/debugger/reference/idebugprogramprovider2.md)   
 [PROVIDER_FLAGS](../../../extensibility/debugger/reference/provider-flags.md)   
 [AD_PROCESS_ID](../../../extensibility/debugger/reference/ad-process-id.md)   
 [IDebugDefaultPort2](../../../extensibility/debugger/reference/idebugdefaultport2.md)   
 [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md)