---
title: Idiadatasource::opensession – | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaDataSource::openSession method
ms.assetid: a3319ed0-3979-483b-9852-c0af96852c48
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: bea16f7ff0f723979ded9962a8ff9e620227f8ea
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53843109"
---
# <a name="idiadatasourceopensession"></a>IDiaDataSource::openSession
Otevře relaci pro dotazování na symboly.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT openSession (   
   IDiaSession** ppSession  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 ppSession  
 [out] Vrátí [idiasession –](../../debugger/debug-interface-access/idiasession.md) objekt představující otevřít relaci.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby. V následující tabulce jsou uvedeny možné návratové hodnoty pro tuto metodu.  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|E_UNEXPECTED, JE-|[Idiadatasource –](../../debugger/debug-interface-access/idiadatasource.md) objekt nebyl inicializován dříve se zdrojem symboly.|  
|E_INVALIDARG|Neplatný `ppSession` parametru.|  
|E_OUTOFMEMORY|Nedostatek paměti k otevření relace.|  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda se otevře [idiasession –](../../debugger/debug-interface-access/idiasession.md) objekt pro zdroj dat.  
  
 `IDiaSession` objekty implementovat dotazy do zdroje dat. Relace slouží ke správě více adresních prostorů pro každou sadu symboly ladění. Pokud je soubor .exe nebo .dll popsal symboly zdroje dat aktivní více adresy rozsahů adres (například, protože více procesů byl načten) a pak jednu relaci pro každý rozsah adres by měl sloužit.  
  
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