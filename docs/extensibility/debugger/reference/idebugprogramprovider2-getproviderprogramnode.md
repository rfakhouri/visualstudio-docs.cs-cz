---
title: IDebugProgramProvider2::GetProviderProgramNode | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProgramProvider2::GetProviderProgramNode
helpviewer_keywords:
- IDebugProgramProvider2::GetProviderProgramNode
ms.assetid: e62e8e83-acbb-4c52-aedf-ffbd4670db29
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 641a3420dac230a62e7a6ba509547ba85efee372
ms.sourcegitcommit: 19ec963ed6d585719cb83ba677434ea6580e0d1f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/24/2019
ms.locfileid: "66203755"
---
# <a name="idebugprogramprovider2getproviderprogramnode"></a>IDebugProgramProvider2::GetProviderProgramNode
Načte uzel program pro konkrétní aplikaci.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetProviderProgramNode(
   PROVIDER_FLAGS       Flags,
   IDebugDefaultPort2*  pPort,
   AD_PROCESS_ID        processId,
   REFGUID              guidEngine,
   UINT64               programId,
   IDebugProgramNode2** ppProgramNode
);
```

```csharp
int GetProviderProgramNode(
   enum_PROVIDER_FLAGS    Flags,
   IDebugDefaultPort2     pPort,
   AD_PROCESS_ID          ProcessId,
   ref Guid               guidEngine,
   ulong                  programId,
   out IDebugProgramNode2 ppProgramNode
);
```

## <a name="parameters"></a>Parametry
`Flags`\
[in] Kombinace příznaků z [PROVIDER_FLAGS](../../../extensibility/debugger/reference/provider-flags.md) výčtu. Následující příznaky jsou typické pro toto volání:

|Příznak|Popis|
|----------|-----------------|
|`PFLAG_REMOTE_PORT`|Volající běží na vzdáleném počítači.|
|`PFLAG_DEBUGGEE`|Volající je momentálně laděna (Další informace o zařazování bude vrácen pro každý uzel).|
|`PFLAG_ATTACHED_TO_DEBUGGEE`|Volající, byl připojený k ale není spuštěn pomocí ladicího programu.|

`pPort`\
[in] Port volající proces běží na.

`processId`\
[in] [AD_PROCESS_ID](../../../extensibility/debugger/reference/ad-process-id.md) struktura obsahující dotyčný ID procesu, který obsahuje program.

`guidEngine`\
[in] Identifikátor GUID ladicího stroje, který program je připojen k (pokud existuje).

`programId`\
[in] ID aplikace, pro které chcete získat uzel programu.

`ppProgramNode`\
[out] [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md) objekt představující uzel pro požadovaný program.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="see-also"></a>Viz také:
- [IDebugProgramProvider2](../../../extensibility/debugger/reference/idebugprogramprovider2.md)
- [PROVIDER_FLAGS](../../../extensibility/debugger/reference/provider-flags.md)
- [AD_PROCESS_ID](../../../extensibility/debugger/reference/ad-process-id.md)
- [IDebugDefaultPort2](../../../extensibility/debugger/reference/idebugdefaultport2.md)
- [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md)