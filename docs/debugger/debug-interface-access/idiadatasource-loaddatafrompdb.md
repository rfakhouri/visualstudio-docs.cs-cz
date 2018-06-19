---
title: Idiadatasource::loaddatafrompdb – | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaDataSource::loadDataFromPdb method
ms.assetid: 02159073-8144-47f8-a0b0-aa0edcb92b5b
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 1910d54ad1a9d2964869beb4854ea97600569b7c
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/18/2018
ms.locfileid: "31468356"
---
# <a name="idiadatasourceloaddatafrompdb"></a>IDiaDataSource::loadDataFromPdb
Otevře a připraví soubor programu databáze (.pdb) jako zdroj dat ladění.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT loadDataFromPdb (  
   LPCOLESTR pdbPath  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 pdbPath  
 [v] Cesta k souboru pdb.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby. V následující tabulce jsou uvedeny možné návratové hodnoty pro tuto metodu.  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|E_PDB_NOT_FOUND|Nepodařilo se otevřít soubor, nebo určit, že soubor má neplatný formát.|  
|E_PDB_FORMAT|Došlo k pokusu o přístup k souboru ve formátu, zastaralé.|  
|E_INVALIDARG|Neplatný parametr.|  
|E_UNEXPECTED|Zdroj dat již byla připravena.|  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda načte ladění data přímo ze souboru pdb.  
  
 K ověření na soubor .pdb proti určitá kritéria, použijte [idiadatasource::loadandvalidatedatafrompdb –](../../debugger/debug-interface-access/idiadatasource-loadandvalidatedatafrompdb.md) metoda.  
  
 Chcete-li získat přístup k proces načtení dat (prostřednictvím mechanismus zpětného volání), použijte [idiadatasource::loaddataforexe –](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md) metoda.  
  
 Chcete-li načíst soubor .pdb přímo z paměti, použijte [idiadatasource::loaddatafromistream –](../../debugger/debug-interface-access/idiadatasource-loaddatafromistream.md) metoda.  
  
## <a name="example"></a>Příklad  
  
```C++  
HRESULT hr = pSource->loadDataFromPdb( L"myprog.pdb" );  
if (FAILED(hr))  
{  
    // report error  
}  
```  
  
## <a name="see-also"></a>Viz také  
 [Idiadatasource –](../../debugger/debug-interface-access/idiadatasource.md)   
 [Idiadatasource::loaddataforexe –](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md)   
 [Idiadatasource::loadandvalidatedatafrompdb –](../../debugger/debug-interface-access/idiadatasource-loadandvalidatedatafrompdb.md)   
 [IDiaDataSource::loadDataFromIStream](../../debugger/debug-interface-access/idiadatasource-loaddatafromistream.md)