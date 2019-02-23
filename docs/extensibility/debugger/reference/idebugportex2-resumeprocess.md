---
title: IDebugPortEx2::ResumeProcess | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugPortEx2::ResumeProcess
helpviewer_keywords:
- IDebugPortEx2::ResumeProcess
ms.assetid: e80a6960-9456-4764-9320-e7b1bd57fe5d
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: c7549ffc7375611d22e0ced603104e6a05d964b6
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56708846"
---
# <a name="idebugportex2resumeprocess"></a>IDebugPortEx2::ResumeProcess
Pokračuje v provádění procesu.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT ResumeProcess( 
   IDebugProcess2* pPortProcess
);
```

```cpp
int ResumeProcess( 
   IDebugProcess2 pPortProcess
);
```

#### <a name="parameters"></a>Parametry
 `pPortProcess`

 [in] [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md) objekt reprezentující proces obnovení.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="see-also"></a>Viz také
- [IDebugPortEx2](../../../extensibility/debugger/reference/idebugportex2.md)
- [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)