---
title: Idiadatasource::loaddataforexe – | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaDataSource::loadDataForExe method
ms.assetid: d94a1068-f53f-44b5-b6fb-00dec361a7f2
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8ce90f3f46b040662f0b0dc1026dbbed0b5c1166
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/18/2018
ms.locfileid: "31465162"
---
# <a name="idiadatasourceloaddataforexe"></a>IDiaDataSource::loadDataForExe
Otevře a připraví ladění data související s.exe/.dll souboru.  
  
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
 [v] Cesta k souboru .exe nebo .dll.  
  
 searchPath  
 [v] Alternativní cestu můžete prohledat data ladění.  
  
 pCallback  
 [v] `IUnknown` Rozhraní pro objekt, který podporuje ladění rozhraní pro zpětné volání, jako [idialoadcallback –](../../debugger/debug-interface-access/idialoadcallback.md), [idialoadcallback2 –](../../debugger/debug-interface-access/idialoadcallback2.md), [idiareadexeatoffsetcallback –](../../debugger/debug-interface-access/idiareadexeatoffsetcallback.md), nebo [idiareadexeatrvacallback –](../../debugger/debug-interface-access/idiareadexeatrvacallback.md) rozhraní.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby. V následující tabulce jsou uvedeny některé možné chybové kódy pro tuto metodu.  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|E_PDB_NOT_FOUND|Nepodařilo se otevřít soubor nebo soubor má neplatný formát.|  
|E_PDB_FORMAT|Došlo k pokusu o přístup k souboru ve formátu, zastaralé.|  
|E_PDB_INVALID_SIG|Podpis neodpovídá.|  
|E_PDB_INVALID_AGE|Stáří neodpovídá.|  
|E_INVALIDARG|Neplatný parametr.|  
|E_UNEXPECTED|Zdroj dat již byla připravena.|  
  
## <a name="remarks"></a>Poznámky  
 Ladění záhlaví souboru.exe/.dll názvy umístění dat přidružené ladění.  
  
 Tato metoda načte záhlaví ladění a pak hledá a připraví data ladění. Probíhá hledání může volitelně hlášené a řízeny prostřednictvím zpětných volání. Například [idialoadcallback::notifydebugdir –](../../debugger/debug-interface-access/idialoadcallback-notifydebugdir.md) je voláno, když `IDiaDataSource::loadDataForExe` metoda vyhledá a zpracuje adresář ladění.  
  
 [Idiareadexeatoffsetcallback –](../../debugger/debug-interface-access/idiareadexeatoffsetcallback.md) a [idiareadexeatrvacallback –](../../debugger/debug-interface-access/idiareadexeatrvacallback.md) rozhraní povolit klientskou aplikaci poskytnout alternativní metody pro čtení dat z spustitelný soubor souboru, když soubor Nelze přistupovat přímo přes standardní soubor vstupně-výstupní operace.  
  
 Chcete-li načíst soubor .pdb bez ověřování, použijte [idiadatasource::loaddatafrompdb –](../../debugger/debug-interface-access/idiadatasource-loaddatafrompdb.md) metoda.  
  
 K ověření na soubor .pdb proti určitá kritéria, použijte [idiadatasource::loadandvalidatedatafrompdb –](../../debugger/debug-interface-access/idiadatasource-loadandvalidatedatafrompdb.md) metoda.  
  
 Chcete-li načíst soubor .pdb přímo z paměti, použijte [idiadatasource::loaddatafromistream –](../../debugger/debug-interface-access/idiadatasource-loaddatafromistream.md) metoda.  
  
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
 [Idiadatasource –](../../debugger/debug-interface-access/idiadatasource.md)   
 [Idialoadcallback –](../../debugger/debug-interface-access/idialoadcallback.md)   
 [Idialoadcallback2 –](../../debugger/debug-interface-access/idialoadcallback2.md)   
 [Idialoadcallback::notifydebugdir –](../../debugger/debug-interface-access/idialoadcallback-notifydebugdir.md)   
 [Idiareadexeatoffsetcallback –](../../debugger/debug-interface-access/idiareadexeatoffsetcallback.md)   
 [Idiareadexeatrvacallback –](../../debugger/debug-interface-access/idiareadexeatrvacallback.md)   
 [Idiadatasource::loaddatafrompdb –](../../debugger/debug-interface-access/idiadatasource-loaddatafrompdb.md)   
 [Idiadatasource::loadandvalidatedatafrompdb –](../../debugger/debug-interface-access/idiadatasource-loadandvalidatedatafrompdb.md)   
 [IDiaDataSource::loadDataFromIStream](../../debugger/debug-interface-access/idiadatasource-loaddatafromistream.md)