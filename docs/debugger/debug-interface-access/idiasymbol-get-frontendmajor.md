---
title: Idiasymbol::get_frontendmajor – | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_frontEndMajor method
ms.assetid: f8a067c5-3306-4fc5-bc20-8910a47ed504
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 7c11b948c63e8eda535c9a651046af4246b500b2
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54981022"
---
# <a name="idiasymbolgetfrontendmajor"></a>IDiaSymbol::get_frontEndMajor
Získá číslo hlavní verze front-endu.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT get_frontEndMajor (   
   DWORD* pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pRetVal`  
 [out] Vrátí číslo hlavní verze front-endu. Viz poznámky.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí `S_FALSE` nebo kód chyby.  
  
> [!NOTE]
>  Vrácená hodnota `S_FALSE` znamená, že vlastnost není k dispozici pro symbol.  
  
## <a name="remarks"></a>Poznámky  
 Kompilátor se obvykle skládá z dvou základní prvky: front-endu (Analyzátor), která zpracovává analýzu zdrojového kódu do zprostředkující formuláře, a back-endu (generátor kódu), který převádí zprostředkující formuláře do sestavení. Není, front-endu mít jinou verzi než back-endu.  
  
 Front-end nebo back-endu číslo verze se skládá ze tří částí: \<hlavní >.\< podverze >. \<sestavení >, kde \<hlavní > je číslo hlavní verze \<podverze > je číslo podverze a \<sestavení > je číslo sestavení. Například 13.10.3077.  
  
## <a name="requirements"></a>Požadavky  
  
|Požadavek|Popis|  
|-----------------|-----------------|  
|Záhlaví:|dia2.h|  
|Verze:|V7.0 DIA SDK|  
  
## <a name="see-also"></a>Viz také  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)