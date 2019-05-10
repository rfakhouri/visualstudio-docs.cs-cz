---
title: IDebugThread2::EnumFrameInfo | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugThread2::EnumFrameInfo
helpviewer_keywords:
- IDebugThread2::EnumFrameInfo
ms.assetid: 17914a71-10ea-4b6f-8982-e364f87dca53
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 466d50f81fe73e0d67e01142568d20cd757ebeea
ms.sourcegitcommit: 6196d0b7fdcb08ba6d28a8151ad36b8d1139f2cc
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/07/2019
ms.locfileid: "65225985"
---
# <a name="idebugthread2enumframeinfo"></a>IDebugThread2::EnumFrameInfo
Načte seznam rámce zásobníku pro toto vlákno.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT EnumFrameInfo ( 
   FRAMEINFO_FLAGS        dwFieldSpec,
   UINT                   nRadix,
   IEnumDebugFrameInfo2** ppEnum
);
```

```csharp
int EnumFrameInfo ( 
   enum_FRAMEINFO_FLAGS     dwFieldSpec,
   uint                     nRadix,
   out IEnumDebugFrameInfo2 ppEnum
);
```

## <a name="parameters"></a>Parametry
 `dwFieldSpec`\

 [in] Kombinace příznaků z [FRAMEINFO_FLAGS](../../../extensibility/debugger/reference/frameinfo-flags.md) výčet, který určuje, jaké pole [FRAMEINFO](../../../extensibility/debugger/reference/frameinfo.md) struktury mají doplnit. Zadejte `FIF_FUNCNAME_FORMAT` příznak pro formátování názvu funkce do jednoho řetězce.

 `nRadix`\

 [in] Základ číselné soustavy použitých ve formátování číselných údajů v enumerátor.

 `ppEnum`\

 [out] Vrátí [IEnumDebugFrameInfo2](../../../extensibility/debugger/reference/ienumdebugframeinfo2.md) objekt, který obsahuje seznam [FRAMEINFO](../../../extensibility/debugger/reference/frameinfo.md) struktury popisující rámce zásobníku.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Vlákna snímků jsou uvedené v pořadí, s aktuální rámec nejprve vytvořit výčet a nejstarší rámce uvedené poslední.

## <a name="see-also"></a>Viz také:
- [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)
- [FRAMEINFO_FLAGS](../../../extensibility/debugger/reference/frameinfo-flags.md)
- [IEnumDebugFrameInfo2](../../../extensibility/debugger/reference/ienumdebugframeinfo2.md)
- [FRAMEINFO](../../../extensibility/debugger/reference/frameinfo.md)