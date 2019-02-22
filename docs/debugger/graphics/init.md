---
title: Init | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: c55ddec8-9101-4673-979b-4109caca9146
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 7a2bd17b91f7a18adce1153634cb9fc55902720b
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56680903"
---
# <a name="init"></a>Init
Připraví součást diagnostiky grafiky k aktivně zachycení a zaznamenání grafických informací do souboru protokolu grafiky v aplikaci.

## <a name="syntax"></a>Syntaxe

```C++
void Init(
  std::function<void (int len, wchar_t * pszBuffer)> vsgLogGetter
);
```

#### <a name="parameters"></a>Parametry
 `vsgLogGetter` Volatelný entitu – například funkce, ukazatele na funkci, výrazu lambda nebo objektu funkce –, který přijímá jako parametry Délka vyrovnávací paměti skládá z `wchar_t` a ukazatel na této vyrovnávací paměti a vrátí `void`. Při vyvolání, volatelných entity Určuje název souboru, který se použije k zaznamenání grafických informací a zapisuje je do zadané vyrovnávací paměti před vrácením.

## <a name="remarks"></a>Poznámky
 `Init` Funkce je volána automaticky, když instance `VsgDbg` třídy je vytvořený tak, že zadáte `bDefaultInit` parametr konstruktoru jako `true`; v opačném případě `Init` musí být explicitně volána před můžete aktivně zachytit a zaznamenání grafických informací.

 Můžete další změny a zavřete aktivní grafiky souboru protokolu voláním `UnInit`a pak zachytíte a zaznamenávat informace grafiky na nový soubor protokolu grafiky voláním `Init` znovu. To můžete opakovat tolikrát, kolikrát chcete vytvořit několik nezávislých grafiky soubory protokolů pomocí stejného `VsgDbg` instance.

## <a name="see-also"></a>Viz také
- [UnInit](init.md)