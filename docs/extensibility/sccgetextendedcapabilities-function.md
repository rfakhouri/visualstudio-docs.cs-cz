---
title: Sccgetextendedcapabilities – funkce | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- SccGetExtendedCapabilities
helpviewer_keywords:
- SccGetExtendedCapabilities function
ms.assetid: 588c6a92-2147-4d8b-a357-96ca7da0a092
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: aa6a067a0b9e8358f503228dbc53e20586b84468
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66353669"
---
# <a name="sccgetextendedcapabilities-function"></a>Sccgetextendedcapabilities – funkce
Tato funkce vrací další funkce, podporuje modul plug-in správy zdrojového kódu.

## <a name="syntax"></a>Syntaxe

```cpp
SCCRTN SccGetExtendedCapabilities(
   LPVOID pContext,
   LONG lSccExCaps,
   LPBOOL pbSupported
);
```

### <a name="parameters"></a>Parametry
 pContext

[in] Ukazatel kontext modulu plug-in zdroje ovládacího prvku.

 lSccExCaps

[in] Příznak určující rozšířené možnosti pro kterou chcete otestovat (viz tabulka pro rozšířené funkce kódu [příznaky funkcí](../extensibility/capability-flags.md) příznaků je to možné).

 pbSupported

[out] Vrátí nenulovou (`TRUE`) Pokud zadaná funkce se podporuje; v opačném případě vrátí hodnotu 0 (`FALSE`).

## <a name="return-value"></a>Návratová hodnota
 Modul plug-in implementaci ovládacího prvku zdroje této funkce má vracet instanci jednoho z následujících hodnot:

|Value|Popis|
|-----------|-----------------|
|SCC_OK|Operace get funkce byla úspěšně dokončena.|
|SCC_E_UNKNOWNERROR<br /><br /> SCC_E_NONSPECIFICERROR|Došlo k neznámé nebo neurčené chybě.|

## <a name="remarks"></a>Poznámky
 Tato metoda je volána na vyžádání; To znamená, když funkce se musí otestovat, tato metoda je volána k určení, zda, která možnost je podporována. Je zadán pouze jeden příznak najednou.

## <a name="see-also"></a>Viz také:
- [Funkce modulu plug-in API zdrojového ovládacího prvku](../extensibility/source-control-plug-in-api-functions.md)
- [Kódy chyb](../extensibility/error-codes.md)
- [Příznaky funkcí](../extensibility/capability-flags.md)