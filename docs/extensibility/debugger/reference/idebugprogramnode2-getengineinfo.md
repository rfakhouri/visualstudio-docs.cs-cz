---
title: IDebugProgramNode2::GetEngineInfo | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProgramNode2::GetEngineInfo
helpviewer_keywords:
- IDebugProgramNode2::GetEngineInfo
ms.assetid: 664e7fe5-9100-4b7d-9dc5-e5a4dd0d0451
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: c31d3a858af2886a27a51e22e131cb89b2234d6e
ms.sourcegitcommit: 50f0c3f2763a05de8482b3579026d9c76c0e226c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/09/2019
ms.locfileid: "65459066"
---
# <a name="idebugprogramnode2getengineinfo"></a>IDebugProgramNode2::GetEngineInfo
Získá název a identifikátor ladicího stroje (DE) spuštění programu.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetEngineInfo ( 
   BSTR* pbstrEngine,
   GUID* pguidEngine
);
```

```csharp
int GetEngineInfo(
   out string pbstrEngine,
   out Guid pguidEngine
);
```

## <a name="parameters"></a>Parametry
 `pbstrEngine`\

 [out] Vrátí název DE spuštění programu (C++-konkrétní: to může být ukazatel s hodnotou null, která udává, že volající není zúčastněnými názvu modulu).

 `pguidEngine`\

 [out] Vrátí globálně jedinečný identifikátor DE spuštění programu (C++-konkrétní: to může být ukazatel s hodnotou null, která udává, že volající nemá zájem o GUID modul).

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="see-also"></a>Viz také:
- [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md)