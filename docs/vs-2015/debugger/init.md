---
title: Init | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: c55ddec8-9101-4673-979b-4109caca9146
caps.latest.revision: 8
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: ea9f8a24d342668b3574c3798a32c58c124aca7b
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68185849"
---
# <a name="init"></a>Init
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Připraví součást diagnostiky grafiky k aktivně zachycení a zaznamenání grafických informací do souboru protokolu grafiky v aplikaci.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
void Init(  
  std::function<void (int len, wchar_t * pszBuffer)> vsgLogGetter  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `vsgLogGetter`  
 Volatelný entitu – například funkce, ukazatele na funkci, výrazu lambda nebo objektu funkce –, který přijímá jako parametry Délka vyrovnávací paměti skládá z `wchar_t` a ukazatel na této vyrovnávací paměti a vrátí `void`. Při vyvolání, volatelných entity Určuje název souboru, který se použije k zaznamenání grafických informací a zapisuje je do zadané vyrovnávací paměti před vrácením.  
  
## <a name="remarks"></a>Poznámky  
 `Init` Funkce je volána automaticky, když instance `VsgDbg` třídy je vytvořený tak, že zadáte `bDefaultInit` parametr konstruktoru jako `true`; v opačném případě `Init` musí být explicitně volána před můžete aktivně zachytit a zaznamenání grafických informací.  
  
 Můžete další změny a zavřete aktivní grafiky souboru protokolu voláním `UnInit`a pak zachytíte a zaznamenávat informace grafiky na nový soubor protokolu grafiky voláním `Init` znovu. To můžete opakovat tolikrát, kolikrát chcete vytvořit několik nezávislých grafiky soubory protokolů pomocí stejného `VsgDbg` instance.  
  
## <a name="see-also"></a>Viz také  
 [UnInit](../debugger/init.md)
