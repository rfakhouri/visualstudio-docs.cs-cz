---
title: "Idiasymbol::get_backendminor – | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaSymbol::get_backEndMinor method
ms.assetid: 37f38d19-6685-440d-a477-7127c4f8699e
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 474b62f702655472327f94370f75955695192795
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="idiasymbolgetbackendminor"></a>IDiaSymbol::get_backEndMinor
Načte číslo podverze back-endu kompilátoru.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT get_backEndMinor (   
   DWORD* pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pRetVal`  
 [out] Vrátí číslo podverze back-end. V části poznámky.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí `S_FALSE` nebo chybový kód.  
  
> [!NOTE]
>  Vrácená hodnota `S_FALSE` znamená, že vlastnost není k dispozici pro symbol.  
  
## <a name="remarks"></a>Poznámky  
 Kompilátor se obvykle skládá ze dvou primárních prvků: front-endu (Analyzátor), který zpracovává analýzu zdrojový kód do formuláře zprostředkující, a back-end (generátor kódu), který převádí zprostředkující formuláře do sestavení. Je běžné pro front-endu má jinou verzi než back-end.  
  
 Front-end nebo back-end číslo verze se skládá ze tří částí: \<hlavní >.\< méně závažné >. \<sestavení >, kde \<hlavní > je hlavní číslo verze, \<menší > je číslo podverze a \<sestavení > je číslo sestavení. Například 13.10.3077.  
  
## <a name="requirements"></a>Požadavky  
  
|Požadavek|Popis|  
|-----------------|-----------------|  
|Hlavičky:|dia2.h|  
|Verze:|V7.0 DIA SDK|  
  
## <a name="see-also"></a>Viz také  
 [Idiasymbol –](../../debugger/debug-interface-access/idiasymbol.md)