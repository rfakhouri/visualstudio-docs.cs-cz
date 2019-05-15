---
title: IDebugBinder3::GetExceptionObjectAndType | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugBinder3::GetExceptionObjectAndType
helpviewer_keywords:
- IDebugBinder3::GetExceptionObjectAndType method
ms.assetid: 2a313fe1-4ee1-4f01-af86-382d6c661a8f
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 22d048bb915146e6c966dd16ca3b2345b5d697ba
ms.sourcegitcommit: 77b4ca625674658d5c5766e684fa0e2a07cad4da
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/14/2019
ms.locfileid: "65614737"
---
# <a name="idebugbinder3getexceptionobjectandtype"></a>IDebugBinder3::GetExceptionObjectAndType
Tato metoda načte výjimky přidružené k objektu, pokud existuje.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetExceptionObjectAndType(
   IDebugObject** ppException,
   IDebugField**  ppField
);
```

```csharp
int GetExceptionObjectAndType(
   out IDebugObject ppException,
   out IDebugField  ppField
);
```

## <a name="parameters"></a>Parametry
`ppException`\
[out] Vrátí objekt představující výjimku.

`ppField`\
[out] Vrátí objekt představující konkrétní pole, které mohou způsobit výjimku (to může mít hodnotu null).

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

> [!NOTE]
> Pokud chcete ověřit, zda dojde k výjimce, zkontrolujte hodnoty vrácené `ppException`: Pokud je hodnota null, pak tento objekt přidružen žádná výjimka.

## <a name="see-also"></a>Viz také:
- [IDebugBinder3](../../../extensibility/debugger/reference/idebugbinder3.md)