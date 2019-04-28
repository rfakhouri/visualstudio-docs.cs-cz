---
title: IDebugProgramNode2 | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProgramNode2
helpviewer_keywords:
- IDebugProgramNode2 interface
ms.assetid: 80e511d8-9b40-4a85-aa5d-952fa5ee6ae7
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 51f49ca90837cf80c22856ae2e8f89a98da43d86
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62869960"
---
# <a name="idebugprogramnode2"></a>IDebugProgramNode2
Toto rozhraní představuje program, který lze ladit.

## <a name="syntax"></a>Syntaxe

```
IDebugProgramNode2 : IUnknown
```

## <a name="notes-for-implementers"></a>Poznámky pro implementátory
 Ladicí stroj (DE) nebo jiného dodavatele port. Tento vlastní port implementuje toto rozhraní k reprezentaci program, který lze ladit. Toto rozhraní je implementováno obvykle na stejný objekt, který implementuje [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) rozhraní. Toto rozhraní je zaregistrován [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] voláním [PublishProgramNode](../../../extensibility/debugger/reference/idebugprogrampublisher2-publishprogramnode.md).

## <a name="notes-for-callers"></a>Poznámky pro volající
 Volání [GetProviderProgramNode](../../../extensibility/debugger/reference/idebugprogramprovider2-getproviderprogramnode.md) vrátit toto rozhraní. Poskytovatel port. Tento vlastní port obdrží toto rozhraní přímo pomocí volání [AddProgramNode](../../../extensibility/debugger/reference/idebugportnotify2-addprogramnode.md). Zavedenými obdrží toto rozhraní přímo pomocí volání [připojit](../../../extensibility/debugger/reference/idebugengine2-attach.md).

## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí
 V následující tabulce jsou uvedeny metody objektu `IDebugProgramNode2`.

|Metoda|Popis|
|------------|-----------------|
|[GetProgramName](../../../extensibility/debugger/reference/idebugprogramnode2-getprogramname.md)|Získá název programu.|
|[GetHostName](../../../extensibility/debugger/reference/idebugprogramnode2-gethostname.md)|Získá název procesu, který je hostitelem programu.|
|[GetHostPid](../../../extensibility/debugger/reference/idebugprogramnode2-gethostpid.md)|Získá identifikátor procesu systému pro proces, který je hostitelem programu.|
|[GetHostMachineName_V7](../../../extensibility/debugger/reference/idebugprogramnode2-gethostmachinename-v7.md)|ZASTARALÉ. NEPOUŽÍVEJTE.|
|[Attach_V7](../../../extensibility/debugger/reference/idebugprogramnode2-attach-v7.md)|ZASTARALÉ. NEPOUŽÍVEJTE. Zobrazit [IDebugProgramNodeAttach2](../../../extensibility/debugger/reference/idebugprogramnodeattach2.md) rozhraní alternativní způsob.|
|[GetEngineInfo](../../../extensibility/debugger/reference/idebugprogramnode2-getengineinfo.md)|Získá název a identifikátor DE spuštěním tohoto programu.|
|[DetachDebugger_V7](../../../extensibility/debugger/reference/idebugprogramnode2-detachdebugger-v7.md)|ZASTARALÉ. NEPOUŽÍVEJTE.|

## <a name="remarks"></a>Poznámky
 Správce ladění relace (SDM) obvykle volá [GetProviderProgramNode](../../../extensibility/debugger/reference/idebugprogramprovider2-getproviderprogramnode.md) získat toto rozhraní.

## <a name="requirements"></a>Požadavky
 Záhlaví: Msdbg.h

 Obor názvů: Microsoft.VisualStudio.Debugger.Interop

 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také
- [Základní rozhraní](../../../extensibility/debugger/reference/core-interfaces.md)
- [IDebugProgramNodeAttach2](../../../extensibility/debugger/reference/idebugprogramnodeattach2.md)
- [AddProgramNode](../../../extensibility/debugger/reference/idebugportnotify2-addprogramnode.md)
- [RemoveProgramNode](../../../extensibility/debugger/reference/idebugportnotify2-removeprogramnode.md)
- [Attach](../../../extensibility/debugger/reference/idebugengine2-attach.md)
- [GetProviderProgramNode](../../../extensibility/debugger/reference/idebugprogramprovider2-getproviderprogramnode.md)
- [PublishProgramNode](../../../extensibility/debugger/reference/idebugprogrampublisher2-publishprogramnode.md)