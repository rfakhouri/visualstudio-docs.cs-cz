---
title: Sccbeginbatch – funkce | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- SccBeginBatch
helpviewer_keywords:
- SccBeginBatch function
ms.assetid: 33968183-2e15-4e0d-955b-ca12212d1c25
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 6bb145358184117046e14b7b598ce6d4bb4586b0
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66333886"
---
# <a name="sccbeginbatch-function"></a>Sccbeginbatch – funkce
Tato funkce spustí batch posloupnost operací správy zdrojů. [Sccendbatch –](../extensibility/sccendbatch-function.md) bude volána k ukončení služby batch. Tyto dávek nemůže být vnořený.

## <a name="syntax"></a>Syntaxe

```cpp
SCCRTN SccBeginBatch(void);
```

### <a name="parameters"></a>Parametry
 Žádné

## <a name="return-value"></a>Návratová hodnota
 Modul plug-in implementaci ovládacího prvku zdroje této funkce má vracet instanci jednoho z následujících hodnot:

|Hodnota|Popis|
|-----------|-----------------|
|SCC_OK|Dávkové operace úspěšně začala.|
|SCC_E_UNKNOWNERROR|K nespecifikované chybě.|

## <a name="remarks"></a>Poznámky
 Zdrojový ovládací prvek dávky se používají ke spouštění stejné operace napříč více projektů nebo několika kontextech. Dávky je možné vyloučit redundantní jednotlivých projektů dialogových oknech uživatelským prostředím během dávkové operace. `SccBeginBatch` Funkce a [sccendbatch –](../extensibility/sccendbatch-function.md) slouží jako dvojice funkce označuje začátek a konec operace. Nemůže být vnořený. `SccBeginBatch` Nastaví příznak označující, že dávkové operace probíhá.

 Dávkové operace je v platnosti, by měl modul plug-in správy zdrojového kódu prezentovat maximálně jeden dialogové okno pro každou otázku uživateli a použít na všechny následné operace odpovědi z tohoto dialogového okna.

## <a name="see-also"></a>Viz také:
- [Funkce modulu plug-in API zdrojového ovládacího prvku](../extensibility/source-control-plug-in-api-functions.md)
- [SccEndBatch](../extensibility/sccendbatch-function.md)