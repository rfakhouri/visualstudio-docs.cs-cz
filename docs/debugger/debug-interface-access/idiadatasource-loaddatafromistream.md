---
title: Idiadatasource::loaddatafromistream – | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaDataSource::loadDataFromIStream method
ms.assetid: 8fe33eea-1457-4b8c-ae19-f1ede5578483
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 9fcc3066a9918e766ee541f03ad2f38b0ec39899
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="idiadatasourceloaddatafromistream"></a>IDiaDataSource::loadDataFromIStream
Připraví ladění data uložená v souboru databáze (.pdb) program přistupovat prostřednictvím v paměti datového proudu.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT loadDataFromIStream (   
   IStream* pIStream  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 pIStream  
 [v] <xref:IStream> Objektu, který představuje datový proud používat.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby. V následující tabulce jsou uvedeny možné návratové hodnoty pro tuto metodu.  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|E_PDB_FORMAT|Došlo k pokusu o přístup k souboru ve formátu, zastaralé.|  
|E_INVALIDARG|Invalidparameter.|  
|E_UNEXPECTED|Zdroj dat již byla připravena.|  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda umožňuje data ladění spustitelného souboru získat z paměti prostřednictvím <xref:IStream> objektu.  
  
 Chcete-li načíst soubor .pdb bez ověřování, použijte [idiadatasource::loaddatafrompdb –](../../debugger/debug-interface-access/idiadatasource-loaddatafrompdb.md) metoda.  
  
 K ověření na soubor .pdb proti určitá kritéria, použijte [idiadatasource::loadandvalidatedatafrompdb –](../../debugger/debug-interface-access/idiadatasource-loadandvalidatedatafrompdb.md) metoda.  
  
 Chcete-li získat přístup k proces načtení dat (prostřednictvím mechanismus zpětného volání), použijte [idiadatasource::loaddataforexe –](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md) metoda.  
  
## <a name="see-also"></a>Viz také  
 [Idiadatasource –](../../debugger/debug-interface-access/idiadatasource.md)   
 [Idiadatasource::loaddataforexe –](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md)   
 [Idiadatasource::loaddatafrompdb –](../../debugger/debug-interface-access/idiadatasource-loaddatafrompdb.md)   
 [IDiaDataSource::loadAndValidateDataFromPdb](../../debugger/debug-interface-access/idiadatasource-loadandvalidatedatafrompdb.md)