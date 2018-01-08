---
title: "Idiadatasource::opensession – | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaDataSource::openSession method
ms.assetid: a3319ed0-3979-483b-9852-c0af96852c48
caps.latest.revision: "7"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 6b7cfaf3e2cf7331576ca79b9820bafb761fc44c
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idiadatasourceopensession"></a>IDiaDataSource::openSession
Otevře relaci pro dotazování symboly.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT openSession (   
   IDiaSession** ppSession  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 ppSession  
 [out] Vrátí [idiasession –](../../debugger/debug-interface-access/idiasession.md) objekt reprezentující otevřít relaci.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby. V následující tabulce jsou uvedeny možné návratové hodnoty pro tuto metodu.  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|E_UNEXPECTED|[Idiadatasource –](../../debugger/debug-interface-access/idiadatasource.md) objekt nebyl inicializován dříve se zdrojem symbolů.|  
|E_INVALIDARG|Neplatný `ppSession` parametr.|  
|E_OUTOFMEMORY|K otevření relace není dostatek paměti.|  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda otevře [idiasession –](../../debugger/debug-interface-access/idiasession.md) objekt zdroje dat.  
  
 `IDiaSession`objekty implementovat dotazy do zdroje dat. Relace spravuje jeden adresní prostor pro každou sadu ladicími symboly. Pokud soubor .exe nebo .dll popsaného symboly zdroj dat je aktivní v více adres rozsahy (například proto více procesy mít ji načíst) a potom slouží jedna relace pro každý rozsah adres.  
  
## <a name="example"></a>Příklad  
  
```C++  
IDiaSession* pSession;  
HRESULT hr = pSource->openSession( &pSession );  
if (FAILED(hr))  
{  
   // report error  
}  
```  
  
## <a name="see-also"></a>Viz také  
 [Idiadatasource –](../../debugger/debug-interface-access/idiadatasource.md)   
 [Přehled](../../debugger/debug-interface-access/overview-debug-interface-access-sdk.md)   
 [Idiasession –](../../debugger/debug-interface-access/idiasession.md)   
 [Dotazování na soubor .Pdb](../../debugger/debug-interface-access/querying-the-dot-pdb-file.md)