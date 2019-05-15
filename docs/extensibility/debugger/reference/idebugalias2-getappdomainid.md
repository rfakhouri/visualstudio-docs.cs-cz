---
title: IDebugAlias2::GetAppDomainId | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- GetAppDomainId
- IDebugAlias2::GetAppDomainId
ms.assetid: 23581aaa-5a53-4859-b264-eca49fc44bcd
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 17f6e487dee1b5ae490cfc2ab180eb872ed5b5d2
ms.sourcegitcommit: 77b4ca625674658d5c5766e684fa0e2a07cad4da
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/14/2019
ms.locfileid: "65615091"
---
# <a name="idebugalias2getappdomainid"></a>IDebugAlias2::GetAppDomainId
Načte identifikátor pro doménu aplikace.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetAppDomainId (
   ULONG32* pappDomainId
);
```

```csharp
int GetAppDomainId (
   out uint pappDomainId
);
```

## <a name="parameters"></a>Parametry
`pappDomainId`\
[out] Vrátí identifikátor domény aplikace.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Pokaždé, když se aplikace restartuje změny identifikátor domény aplikace a novou doménu aplikace se vytvoří.

## <a name="see-also"></a>Viz také:
- [IDebugAlias2](../../../extensibility/debugger/reference/idebugalias2.md)