---
title: DONT_SAVE_VSGLOG_TO_TEMP | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: f27ab0e6-9575-4ca0-9901-37d3e5c3a2f5
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 501a054ddb1d3ab20a10f99bb30a0c3439004eb3
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62848691"
---
# <a name="dontsavevsglogtotemp"></a>DONT_SAVE_VSGLOG_TO_TEMP
Definuje jeho přítomnost, zda soubor protokolu grafiky je uložen do adresáře dočasných souborů uživatele.

## <a name="syntax"></a>Syntaxe

```C++
#define DONT_SAVE_VSGLOG_TO_TEMP
```

## <a name="value"></a>Hodnota
 Symbol preprocesoru, podle přítomnosti nebo nepřítomnosti Určuje, zda soubor protokolu grafiky je uložen do adresáře dočasných souborů uživatele. Pokud tento symbol je definován, je název souboru určené `VSG_DEFAULT_RUN_FILENAME` je relativní vzhledem k aktuální adresář zachycené aplikace nebo je absolutní cesta; v opačném případě se název souboru určené `VSG_DEFAULT_RUN_FILENAME` je relativní k adresáři dočasné soubory uživatele a nemůže být absolutní cesta.

## <a name="remarks"></a>Poznámky
 V závislosti na oprávnění uživatele nemusí být možné uložit do libovolného umístění souboru protokolu grafiky. Doporučujeme vám, že chcete uložit protokoly grafiky do adresáře dočasných souborů uživatele nebo jiného umístění známému dobrému, pokud si nejste jisti, zda umístění, na které byste zvolili, je možné zapisovat na uživatelem.

 Chcete-li zabránit souboru protokolu grafiky, neuloží se do adresáře s dočasnými soubory, musí být definován `DONT_SAVE_VSGLOG_TO_TEMP` teprve potom zahrňte `vsgcapture.h`.

## <a name="example"></a>Příklad
 Tento příklad ukazuje, jak uložit soubor protokolu grafiky na absolutní cestu, na hostitelském počítači.

```cpp
// Define DONT_SAVE_VSGLOG_TO_TEMP and VSG_DEFAULT_RUN_FILENAME before including vsgcapture.h
#define DONT_SAVE_VSGLOG_TO_TEMP
#define VSG_DEFAULT_RUN_FILENAME L"C:\\Graphics Diagnostics Captures\\default.vsglog"

#include <vsgcapture.h>
```

## <a name="see-also"></a>Viz také
- [VSG_DEFAULT_RUN_FILENAME](vsg-default-run-filename.md)
