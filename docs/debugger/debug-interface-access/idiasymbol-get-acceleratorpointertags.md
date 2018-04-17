---
title: IDiaSymbol::get_acceleratorPointerTags | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 30e13cee-e511-49ec-affd-99b0097071b2
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 159464305063fd2d40109ba000421f0e5cc72d09
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="idiasymbolgetacceleratorpointertags"></a>IDiaSymbol::get_acceleratorPointerTags
Vrátí všechny hodnoty značky ukazatel akcelerátoru, které odpovídají na funkci se zakázaným inzerováním C++ AMP akcelerátoru.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT get_acceleratorPointerTags(   
   DWORD          cnt,  
   DWORD*         pcnt,  
   DWORD*         pPointerTags);  
```  
  
#### <a name="parameters"></a>Parametry  
 `cnt`  
 [v] Velikost pole výstup `pPointerTags`.  
  
 `pcnt`  
 [out] Počet značek ukazatel akcelerátoru ve funkci se zakázaným inzerováním akcelerátoru C++ AMP.  
  
 `pPointerTags`  
 [out] A `DWORD` pole ukazatele, který je vyplněn hodnot značek ukazatel akcelerátoru v C++ AMP akcelerátoru se zakázaným inzerováním funkce.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí `S_FALSE` nebo chybový kód.  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda je volána v `IDiaSymbol` rozhraní, která odpovídá funkci se zakázaným inzerováním C++ AMP akcelerátoru.  
  
## <a name="see-also"></a>Viz také  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)