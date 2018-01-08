---
title: "Idiadatasource::loadandvalidatedatafrompdb – | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaDataSource::loadAndValidateDataFromPdb method
ms.assetid: d66712dd-6c24-4192-919a-cce262066f0e
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: bcd82116c7499d2a2289fc0c198a2be053226721
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idiadatasourceloadandvalidatedatafrompdb"></a>IDiaDataSource::loadAndValidateDataFromPdb
Otevře a ověřuje, že soubor databáze (.pdb) programu shoduje podpis informací a připraví na soubor .pdb jako zdroj dat ladění.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT loadAndValidateDataFromPdb (   
   LPCOLESTR pdbPath,  
   GUID*     pcsig70,  
   DWORD     sig,  
   DWORD     age  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pdbPath`  
 [v] Cesta k souboru pdb.  
  
 `pcsig70`  
 [v] Identifikátor GUID podpis ověření proti podpis souboru pdb. Soubory PDB pouze [!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)] a novějším mají podpisy identifikátor GUID.  
  
 `sig`  
 [v] 32-bit podpis ověření proti podpis souboru pdb.  
  
 `age`  
 [v] Stáří hodnota ověření. Stáří neodpovídá nutně na jakoukoli hodnotu známý časový, se používá k určení, zda je soubor .pdb synchronizován s odpovídající soubor .exe.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby. V následující tabulce jsou uvedeny možné návratové hodnoty pro tuto metodu.  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|E_PDB_NOT_FOUND|Nepodařilo se otevřít soubor nebo soubor má neplatný formát.|  
|E_PDB_FORMAT|Došlo k pokusu o přístup k souboru ve formátu, zastaralé.|  
|E_PDB_INVALID_SIG|Podpis neodpovídá.|  
|E_PDB_INVALID_AGE|Stáří neodpovídá.|  
|E_INVALIDARG|Neplatný parametr.|  
|E_UNEXPECTED|Zdroj dat již byla připravena.|  
  
## <a name="remarks"></a>Poznámky  
 Soubor .pdb obsahuje podpis a stáří hodnoty. Tyto hodnoty jsou replikované v souboru .exe nebo .dll, který odpovídá na soubor .pdb. Než začnete připravovat zdroj dat, tato metoda ověří, jestli podpis a stáří souboru s názvem PDB shodují s hodnotami zadat.  
  
 Chcete-li načíst soubor .pdb bez ověřování, použijte [idiadatasource::loaddatafrompdb –](../../debugger/debug-interface-access/idiadatasource-loaddatafrompdb.md) metoda.  
  
 Chcete-li získat přístup k proces načtení dat (prostřednictvím mechanismus zpětného volání), použijte [idiadatasource::loaddataforexe –](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md) metoda.  
  
 Chcete-li načíst soubor .pdb přímo z paměti, použijte [idiadatasource::loaddatafromistream –](../../debugger/debug-interface-access/idiadatasource-loaddatafromistream.md) metoda.  
  
## <a name="example"></a>Příklad  
  
```C++  
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
 [Idiadatasource –](../../debugger/debug-interface-access/idiadatasource.md)   
 [Idiadatasource::loaddataforexe –](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md)   
 [Idiadatasource::loaddatafrompdb –](../../debugger/debug-interface-access/idiadatasource-loaddatafrompdb.md)   
 [IDiaDataSource::loadDataFromIStream](../../debugger/debug-interface-access/idiadatasource-loaddatafromistream.md)