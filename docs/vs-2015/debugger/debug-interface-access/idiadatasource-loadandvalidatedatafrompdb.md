---
title: Idiadatasource::loadandvalidatedatafrompdb – | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IDiaDataSource::loadAndValidateDataFromPdb method
ms.assetid: d66712dd-6c24-4192-919a-cce262066f0e
caps.latest.revision: 11
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: f19a910af45ed70ae74c72441890ecae6c81d2a4
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68198621"
---
# <a name="idiadatasourceloadandvalidatedatafrompdb"></a>IDiaDataSource::loadAndValidateDataFromPdb
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Otevře a ověřuje, že soubor databáze (PDB) programu odpovídá podpis informací uvedených a připraví soubor typu .pdb jako zdroj dat ladění.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT loadAndValidateDataFromPdb (   
   LPCOLESTR pdbPath,  
   GUID*     pcsig70,  
   DWORD     sig,  
   DWORD     age  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pdbPath`  
 [in] Cesta k souboru .pdb.  
  
 `pcsig70`  
 [in] Identifikátor GUID podpis ověření proti podpis souboru pdb. Soubory PDB pouze [!INCLUDE[vcprvc](../../includes/vcprvc-md.md)] a později máte podpisů identifikátor GUID.  
  
 `sig`  
 [in] 32-bit podpis ověření proti podpis souboru pdb.  
  
 `age`  
 [in] Stáří hodnotu pro ověření. Stáří neodpovídá nutně na libovolnou hodnotu známý čas, se používá k určení, zda je soubor PDB synchronizován s odpovídající soubor .exe.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby. V následující tabulce jsou uvedeny možné návratové hodnoty pro tuto metodu.  
  
|Value|Popis|  
|-----------|-----------------|  
|E_PDB_NOT_FOUND|Nepovedlo se otevřít soubor nebo soubor má neplatný formát.|  
|E_PDB_FORMAT|Došlo k pokusu o přístup k souboru se zastaralý formát.|  
|E_PDB_INVALID_SIG|Podpis neodpovídá.|  
|E_PDB_INVALID_AGE|Stáří neodpovídá.|  
|E_INVALIDARG|Neplatný parametr.|  
|E_UNEXPECTED, JE-|Zdroj dat je už připraven.|  
  
## <a name="remarks"></a>Poznámky  
 Soubor PDB obsahuje podpis a stáří hodnoty. Tyto hodnoty jsou replikované v souboru .exe nebo .dll, který odpovídá souboru .pdb. Než začnete připravovat zdroj dat, tato metoda ověří, že podpis a stáří souboru .pdb s názvem odpovídat hodnotám, které jsou k dispozici.  
  
 Chcete-li načíst soubor PDB bez ověřování, použijte [idiadatasource::loaddatafrompdb –](../../debugger/debug-interface-access/idiadatasource-loaddatafrompdb.md) metody.  
  
 Chcete-li získat přístup k procesu načítání dat (prostřednictvím mechanismu zpětné volání), použijte [idiadatasource::loaddataforexe –](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md) metody.  
  
 Chcete-li načíst soubor PDB přímo z paměti, použijte [idiadatasource::loaddatafromistream –](../../debugger/debug-interface-access/idiadatasource-loaddatafromistream.md) metody.  
  
## <a name="example"></a>Příklad  
  
```cpp#  
IDiaDataSource* pSource;  // Previously created data source.  
DEFINE_GUID(expectedGUIDSignature,0x1234,0x5678,0x01,0x02,0x03,0x04,0x05,0x06,0x07,0x08);  
DWORD expectedFileSignature = 0x12345678;  
DWORD expectedAge           = 128;  
  
HRESULT hr;  
hr = pSource->loadAndValidateDataFromPdb( L"yprog.pdb",  
                                          &expectedGUIDSignature,  
                                          expectedFileSignature,  
                                          expectedAge);  
if (FAILED(hr))  
{  
    // Report an error  
}  
  
```  
  
## <a name="see-also"></a>Viz také  
 [IDiaDataSource](../../debugger/debug-interface-access/idiadatasource.md)   
 [IDiaDataSource::loadDataForExe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md)   
 [IDiaDataSource::loadDataFromPdb](../../debugger/debug-interface-access/idiadatasource-loaddatafrompdb.md)   
 [IDiaDataSource::loadDataFromIStream](../../debugger/debug-interface-access/idiadatasource-loaddatafromistream.md)
