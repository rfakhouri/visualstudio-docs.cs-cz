---
title: IDebugAlias2::GetAppDomainId | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- GetAppDomainId
- IDebugAlias2::GetAppDomainId
ms.assetid: 23581aaa-5a53-4859-b264-eca49fc44bcd
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: b40d52c5eedf0defb845f1944acd166d48dca1ee
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66338164"
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