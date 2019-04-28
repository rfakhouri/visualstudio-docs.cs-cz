---
title: Sccendbatch – funkce | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- SccEndBatch
helpviewer_keywords:
- SccEndBatch function
ms.assetid: 100e7833-fe0a-45c0-9fca-3e61fd1165b7
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: e0662e4c4d1d71e2c9ae0e8f40ff21868d6b9a5d
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62433263"
---
# <a name="sccendbatch-function"></a>Sccendbatch – funkce
Tato funkce dojde k závěru dávku operací správy zdrojů. Tyto dávek nemůže být vnořený.

## <a name="syntax"></a>Syntaxe

```cpp
SCCRTN SccEndBatch(void);
```

## <a name="parameters"></a>Parametry
 Žádné

## <a name="return-value"></a>Návratová hodnota
 Modul plug-in implementaci ovládacího prvku zdroje této funkce má vracet instanci jednoho z následujících hodnot:

|Hodnota|Popis|
|-----------|-----------------|
|SCC_OK|Dávkové operace úspěšně uzavřené.|
|SCC_E_UNKNOWNERROR|K nespecifikované chybě.|

## <a name="remarks"></a>Poznámky
 Zdrojový ovládací prvek dávky se používají ke spouštění stejné operací správy zdrojů mezi více projekty nebo několika kontextech. Dávky je možné vyloučit redundantní dialogových oknech uživatelským prostředím během dávkové operace. [Sccbeginbatch –](../extensibility/sccbeginbatch-function.md) a `SccEndBatch` funkce se používají jako dvojice označuje začátek a konec operace. Nemůže být vnořený.

## <a name="see-also"></a>Viz také:
- [Funkce modulu plug-in API zdrojového ovládacího prvku](../extensibility/source-control-plug-in-api-functions.md)
- [SccBeginBatch](../extensibility/sccbeginbatch-function.md)