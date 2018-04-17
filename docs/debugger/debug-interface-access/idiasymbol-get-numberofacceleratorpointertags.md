---
title: IDiaSymbol::get_numberOfAcceleratorPointerTags | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 1886e3ec-b227-4187-8d93-c5144b4b77ae
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 3122c5a237b28ee9e5c4aea9aa8f36de639c2875
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="idiasymbolgetnumberofacceleratorpointertags"></a>IDiaSymbol::get_numberOfAcceleratorPointerTags
Vrátí počet značek ukazatel akcelerátoru ve funkci se zakázaným inzerováním C++ AMP.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT get_numberOfAcceleratorPointerTags(   
   DWORD* count);  
```  
  
#### <a name="parameters"></a>Parametry  
 `count`  
 [out] Ukazatel na `DWORD` , počet akcelerátoru obsahuje ukazatele značky ve funkci se zakázaným inzerováním C++ AMP.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí `S_FALSE` nebo chybový kód.  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda je volána v `IDiaSymbol` rozhraní, která odpovídá funkci se zakázaným inzerováním C++ AMP akcelerátoru.  
  
## <a name="see-also"></a>Viz také  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)