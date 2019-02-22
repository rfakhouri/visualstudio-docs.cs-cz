---
title: Idiadatasource::loaddataforexe – | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaDataSource::loadDataForExe method
ms.assetid: d94a1068-f53f-44b5-b6fb-00dec361a7f2
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 4f95e8a9321ff7ae518e72496289f8ad0c7b4682
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56609641"
---
# <a name="idiadatasourceloaddataforexe"></a>IDiaDataSource::loadDataForExe
Otevře a připraví data ladění přidružené k souboru.exe/.dll.

## <a name="syntax"></a>Syntaxe

```C++
HRESULT loadDataForExe (
   LPCOLESTR executable,
   LPCOLESTR searchPath,
   IUnknown* pCallback
);
```

#### <a name="parameters"></a>Parametry
spustitelný soubor

[in] Cesta k souboru .exe nebo .dll.

searchPath

[in] Alternativní cesty pro vyhledávání dat ladění.

pCallback

[in] `IUnknown` Rozhraní pro objekt, který podporuje ladění rozhraní zpětného volání, například [idialoadcallback –](../../debugger/debug-interface-access/idialoadcallback.md), [idialoadcallback2 –](../../debugger/debug-interface-access/idialoadcallback2.md), [idiareadexeatoffsetcallback –](../../debugger/debug-interface-access/idiareadexeatoffsetcallback.md), nebo [idiareadexeatrvacallback –](../../debugger/debug-interface-access/idiareadexeatrvacallback.md) rozhraní.

## <a name="return-value"></a>Návratová hodnota
Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby. V následující tabulce jsou uvedeny některé možné chybové kódy pro tuto metodu.

|Hodnota|Popis|
|-----------|-----------------|
|E_PDB_NOT_FOUND|Nepovedlo se otevřít soubor nebo soubor má neplatný formát.|
|E_PDB_FORMAT|Došlo k pokusu o přístup k souboru se zastaralý formát.|
|E_PDB_INVALID_SIG|Podpis neodpovídá.|
|E_PDB_INVALID_AGE|Stáří neodpovídá.|
|E_INVALIDARG|Neplatný parametr.|
|E_UNEXPECTED, JE-|Zdroj dat je už připraven.|

## <a name="remarks"></a>Poznámky
Ladění záhlaví souboru.exe/.dll názvy umístění dat přidružená ladění.

Tato metoda načte záhlaví ladění a pak vyhledá a připraví data ladění. Probíhá hledání může volitelně hlášené a řídit pomocí zpětných volání. Například [idialoadcallback::notifydebugdir –](../../debugger/debug-interface-access/idialoadcallback-notifydebugdir.md) při vyvolání `IDiaDataSource::loadDataForExe` metoda vyhledá a zpracuje adresář ladění.

[Idiareadexeatoffsetcallback –](../../debugger/debug-interface-access/idiareadexeatoffsetcallback.md) a [idiareadexeatrvacallback –](../../debugger/debug-interface-access/idiareadexeatrvacallback.md) rozhraní umožňují klientské aplikaci poskytují alternativní metody pro čtení dat ze spustitelného souboru souboru, když soubor Nelze přistupovat přímo pomocí standardních souborových vstupně-výstupních operací.

Chcete-li načíst soubor PDB bez ověřování, použijte [idiadatasource::loaddatafrompdb –](../../debugger/debug-interface-access/idiadatasource-loaddatafrompdb.md) metody.

Chcete-li ověřit soubor typu .pdb podle konkrétních kritérií, použijte [idiadatasource::loadandvalidatedatafrompdb –](../../debugger/debug-interface-access/idiadatasource-loadandvalidatedatafrompdb.md) metody.

Chcete-li načíst soubor PDB přímo z paměti, použijte [idiadatasource::loaddatafromistream –](../../debugger/debug-interface-access/idiadatasource-loaddatafromistream.md) metody.

## <a name="example"></a>Příklad

```C++
class MyCallBack: public IDiaLoadCallback
{
...
};
MyCallBack callback;
...
HRESULT hr = pSource->loadDataForExe( L"myprog.exe", L".\debug", (IUnknown*)&callback);
if (FAILED(hr))
{
    // Report error
}
```

## <a name="see-also"></a>Viz také
- [IDiaDataSource](../../debugger/debug-interface-access/idiadatasource.md)
- [IDiaLoadCallback](../../debugger/debug-interface-access/idialoadcallback.md)
- [IDiaLoadCallback2](../../debugger/debug-interface-access/idialoadcallback2.md)
- [IDiaLoadCallback::NotifyDebugDir](../../debugger/debug-interface-access/idialoadcallback-notifydebugdir.md)
- [IDiaReadExeAtOffsetCallback](../../debugger/debug-interface-access/idiareadexeatoffsetcallback.md)
- [IDiaReadExeAtRVACallback](../../debugger/debug-interface-access/idiareadexeatrvacallback.md)
- [IDiaDataSource::loadDataFromPdb](../../debugger/debug-interface-access/idiadatasource-loaddatafrompdb.md)
- [IDiaDataSource::loadAndValidateDataFromPdb](../../debugger/debug-interface-access/idiadatasource-loadandvalidatedatafrompdb.md)
- [IDiaDataSource::loadDataFromIStream](../../debugger/debug-interface-access/idiadatasource-loaddatafromistream.md)
