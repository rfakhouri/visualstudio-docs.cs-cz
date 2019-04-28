---
title: IDebugModuleLoadEvent2::GetModule | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugModuleLoadEvent2::GetModule
helpviewer_keywords:
- IDebugModuleLoadEvent2::GetModule
ms.assetid: c86482bb-9ce5-4e63-bbe0-969b50169424
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: b17636d5f346475018e27c72562807b44b39460c
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62872895"
---
# <a name="idebugmoduleloadevent2getmodule"></a>IDebugModuleLoadEvent2::GetModule
Získá modul, který je načten nebo byla uvolněna.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetModule( 
   IDebugModule2** pModule,
   BSTR*           pbstrDebugMessage,
   BOOL*           pbLoad
);
```

```csharp
int GetModule( 
   out IDebugModule2 pModule,
   ref string        pbstrDebugMessage,
   ref int           pbLoad
);
```

#### <a name="parameters"></a>Parametry
 `pModule`

 [out] Vrátí [IDebugModule2](../../../extensibility/debugger/reference/idebugmodule2.md) objekt, který představuje modul, který je načítání nebo uvolnění.

 `pbstrDebugMessage`

 [out v] Vrátí volitelnou zprávu s popisem této události. Pokud je tento parametr hodnotu null, je požadována žádná zpráva.

 `pbLoad`

 [out v] Nenulová (`TRUE`) Pokud modul je nula a načítání (`FALSE`) Pokud uvolnění modulu. Pokud je tento parametr hodnotu null, je požadována bez stavu.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="see-also"></a>Viz také
- [IDebugModuleLoadEvent2](../../../extensibility/debugger/reference/idebugmoduleloadevent2.md)
- [IDebugModule2](../../../extensibility/debugger/reference/idebugmodule2.md)