---
title: Init – | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
ms.assetid: c55ddec8-9101-4673-979b-4109caca9146
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0e81b5ac1b49e9ab021a2436013b0db3dff9a5e0
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="init"></a>Init
Připraví komponenta diagnostiky grafiky k aktivně zachycení a zaznamenání grafických informací do souboru protokolu grafiky v aplikaci.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
void Init(  
  std::function<void (int len, wchar_t * pszBuffer)> vsgLogGetter  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `vsgLogGetter`  
 S entity – například funkce, – ukazatel na funkci, lambda nebo objekt funkce –, která má jako parametry Délka vyrovnávací paměti tvořený `wchar_t` a ukazatel na tento vyrovnávací paměti a vrátí `void`. Po vyvolání s entity Určuje název souboru, který se použije k zaznamenání grafických informací a zapíše ho do zadané vyrovnávací paměti před vrácením.  
  
## <a name="remarks"></a>Poznámky  
 `Init` Funkce je volána automaticky, když instance `VsgDbg` třída je vytvořený tak, že zadáte `bDefaultInit` parametr jeho konstruktoru jako `true`, jinak hodnota `Init` musí být explicitně volána před můžete zaznamenat aktivně a zaznamenání grafických informací.  
  
 Můžete dokončit a zavřete aktivní grafiky soubor protokolu voláním `UnInit`a pak zachytíte a zaznamenejte další grafických informací do nového souboru protokolu grafiky voláním `Init` znovu. To můžete opakovat tolikrát, kolikrát chcete vytvořit několik nezávislých grafiky soubory protokolů pomocí stejné `VsgDbg` instance.  
  
## <a name="see-also"></a>Viz také  
 [UnInit](init.md)