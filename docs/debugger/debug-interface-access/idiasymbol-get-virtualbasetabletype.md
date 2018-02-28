---
title: "Idiasymbol::get_virtualbasetabletype – | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_virtualBaseTableType method
ms.assetid: e0581c4f-0343-49b5-9754-a48477460e9f
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: da79744ab31b4d8edee83e0ab5b159edbb495cb7
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idiasymbolgetvirtualbasetabletype"></a>IDiaSymbol::get_virtualBaseTableType
Načte typ ukazatele virtuální základní tabulky.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT get_virtualBaseTableType(  
   IDiaSymbol *pRetVal  
};  
```  
  
#### <a name="parameters"></a>Parametry  
  
|Parametr|Popis|  
|---------------|-----------------|  
|`pRetVal`|[out] Vrátí [idiasymbol –](../../debugger/debug-interface-access/idiasymbol.md) objekt, který určuje typ základní tabulky.|  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí `S_FALSE` nebo chybový kód.  
  
> [!NOTE]
>  Vrácená hodnota `S_FALSE` znamená vlastnost není k dispozici pro symbol.  
  
## <a name="remarks"></a>Poznámky  
 Ukazatel virtuální základní tabulky (`vbtptr`) je skrytý ukazatel v [!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)] virtuální tabulku, která zpracovává dědění ze základní virtuální třídy. A `vbtptr` může mít různě v závislosti na zděděné třídy.  
  
 Tato metoda vrátí [idiasymbol –](../../debugger/debug-interface-access/idiasymbol.md) objekt, který můžete použít k určení velikosti vbtptr.  
  
## <a name="requirements"></a>Požadavky  
  
|Požadavek|Popis|  
|-----------------|-----------------|  
|Hlavičky:|dia2.h|  
|Verze:|V8.0 DIA SDK|  
  
## <a name="see-also"></a>Viz také  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)