---
title: IDebugProgramHost2::GetHostName | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProgramHost2::GetHostName
helpviewer_keywords:
- IDebugProgramHost2::GetHostName
ms.assetid: 48bbb089-e59a-471a-9965-24b42a8dabf3
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 45919c6c9fafceecca2cb53fa9c2c9f43b68e382
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56707416"
---
# <a name="idebugprogramhost2gethostname"></a>IDebugProgramHost2::GetHostName
Získá název, popisný název nebo název souboru hostitelského procesu tohoto programu.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetHostName( 
   DWORD dwType,
   BSTR* pbstrHostName
);
```

```csharp
int GetHostName( 
   uint dwType,
   out string pbstrHostName
);
```

#### <a name="parameters"></a>Parametry
 `dwType`

 [in] Hodnota z [GETHOSTNAME_TYPE](../../../extensibility/debugger/reference/gethostname-type.md) výčtu.

 `pbstrHostName`

 [out] Vrátí název požadovaného hostitelského procesu.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 V typické implementace této metody `dwType` parametr je ignorován a vrátí se popisný název hostitelského počítače. Další možnou implementaci je předat `dwType` parametr volání [gethostname –](../../../extensibility/debugger/reference/idebugprogramnode2-gethostname.md) metodu k získání názvu.

## <a name="see-also"></a>Viz také
- [IDebugProgramHost2](../../../extensibility/debugger/reference/idebugprogramhost2.md)
- [GetHostName](../../../extensibility/debugger/reference/idebugprogramnode2-gethostname.md)