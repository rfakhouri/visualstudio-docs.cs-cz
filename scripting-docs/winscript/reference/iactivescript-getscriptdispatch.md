---
title: IActiveScript::GetScriptDispatch | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScript.GetScriptDispatch
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScript_GetScriptDispatch
ms.assetid: 2092ccd4-1f4c-493a-b5b7-077a70ce95ca
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c329a4dbf42461369441b86f6d9ba18992916366
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/18/2019
ms.locfileid: "58144742"
---
# <a name="iactivescriptgetscriptdispatch"></a>IActiveScript::GetScriptDispatch
Načte `IDispatch` rozhraní pro metody a vlastnosti přidružené k aktuálně spuštěného skriptu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT GetScriptDispatch(  
    LPCOLESTR pstrItemName  // address of item name  
    IDispatch **ppdisp      // receives IDispatch pointer  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pstrItemName`  
 [in] Adresa vyrovnávací paměti, který obsahuje název položky, pro který volající potřebuje objekt přidružený odeslání. Pokud je tento parametr `NULL`, odeslání objekt obsahuje členy všechny globální metody a vlastnosti definované ve skriptu. Prostřednictvím `IDispatch` rozhraní a přidružených `ITypeInfo` rozhraní, můžete hostitele vyvolání metody skriptů nebo zobrazení a úpravám proměnných skriptu.  
  
 `ppdisp`  
 [out] Adresa proměnné, která přijímá ukazatel na objekt přidružený ke skriptu globální metody a vlastnosti. Pokud skriptovací modul nepodporuje takový objekt `NULL` je vrácena.  
  
## <a name="return-value"></a>Návratová hodnota  
 Vrátí jednu z následujících hodnot:  
  
|Návratová hodnota|Význam|  
|------------------|-------------|  
|`S_OK`|Úspěch.|  
|`E_INVALIDARG`|Argument byl neplatný.|  
|`E_POINTER`|Byl zadán neplatný ukazatel.|  
|`E_UNEXPECTED`|Volání nebylo očekáváno (například skriptovací stroj má ještě nebyly načteny nebo inicializován).|  
|`S_FALSE`|Skriptovací modul nepodporuje odesílání objektu. `ppdisp` parametr je nastaven na hodnotu NULL.|  
  
## <a name="remarks"></a>Poznámky  
 Protože metody a vlastnosti lze přidat pomocí volání [IActiveScriptParse –](../../winscript/reference/iactivescriptparse.md) rozhraní, `IDispatch` rozhraní vrácený touto metodou dynamicky podporují nové metody a vlastnosti. Podobně platí `IDispatch::GetTypeInfo` metoda by měla vrátit nové, jedinečné `ITypeInfo` rozhraní po přidání metody a vlastnosti. Pamatujte však, že nesmí změnit jazykové moduly `IDispatch` rozhraní způsobem, který je nekompatibilní s žádným předchozí `ITypeInfo` vrácené rozhraní. To znamená, například, že hodnoty dispID bude nikdy znovu použita.  
  
## <a name="see-also"></a>Viz také  
 [IActiveScript](../../winscript/reference/iactivescript.md)