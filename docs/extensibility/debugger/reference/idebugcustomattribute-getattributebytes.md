---
title: IDebugCustomAttribute::GetAttributeBytes | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugCustomAttribute::GetAttributeBytes
helpviewer_keywords:
- IDebugCustomAttribute::GetAttributeBytes
ms.assetid: cf34583b-6530-4dcc-89f8-eb27e4e8d594
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 551261414db9fab97f3e8c2a8fdbe518143d79c5
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66315185"
---
# <a name="idebugcustomattributegetattributebytes"></a>IDebugCustomAttribute::GetAttributeBytes
Získá informace o atributu jako objekt blob bajtů.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetAttributeBytes( 
   BYTE*  ppBlob,
   DWORD* pdwLen
);
```

```csharp
int GetAttributeBytes(
   ref byte[] ppBlob,
   ref uint   pdwLen
);
```

## <a name="parameters"></a>Parametry
`ppBlob`\
[out v] Pole, které se vyplní atribut bajtů.

`pdwLen`\
[out v] Určuje maximální počet bajtů, které mají vracet v `ppBlob` pole a vrátí počet bajtů zapsaný ve skutečnosti na pole.

## <a name="return-value"></a>Návratová hodnota
 V případě úspěchu vrátí hodnotu S_OK; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Nastavte `ppBlob` atributy parametr na hodnotu null, vrátí počet bajtů, které jsou k dispozici. Potom přidělit pole a předejte toto pole v pro `ppBlob` parametru.

 Atribut bajtů představují nezpracovaná data vlastního atributu.

## <a name="see-also"></a>Viz také:
- [IDebugCustomAttribute](../../../extensibility/debugger/reference/idebugcustomattribute.md)