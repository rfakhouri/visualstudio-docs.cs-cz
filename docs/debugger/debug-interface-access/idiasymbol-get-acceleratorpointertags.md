---
title: IDiaSymbol::get_acceleratorPointerTags | Microsoft Docs
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
ms.assetid: 30e13cee-e511-49ec-affd-99b0097071b2
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: e5190496258cfb4ed66334e10a3d727a1c9555b6
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
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