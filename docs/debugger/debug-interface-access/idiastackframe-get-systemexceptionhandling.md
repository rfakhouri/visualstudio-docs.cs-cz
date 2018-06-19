---
title: IDiaStackFrame::get_systemExceptionHandling | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaStackFrame::get_systemExceptionHandling
ms.assetid: c76cf265-dea0-4159-883f-32b50bbef044
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 033122a925313117d007c20bb7a6d4f5f513b76c
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/18/2018
ms.locfileid: "31463462"
---
# <a name="idiastackframegetsystemexceptionhandling"></a>IDiaStackFrame::get_systemExceptionHandling
Načte příznak, který určuje, zda je systém zpracování výjimek v platnosti.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT get_systemExceptionHandling (   
   BOOL* pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pRetVal`  
 [out] Vrátí `TRUE` systému zpracování výjimek v případě platí pro tento snímek; jinak vrátí `FALSE`.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`. Vrátí `S_FALSE` Pokud vlastnost není podporována. Jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Zpracovávání výjimek v jazyce systému se taky říká strukturované zpracování výjimek. Toto není totéž jako zpracovávání výjimek v jazyce C++.  
  
 Pokud chcete zjistit, pokud je v platnosti zpracovávání výjimek v jazyce C++, volání [idiastackframe::get_cplusplusexceptionhandling –](../../debugger/debug-interface-access/idiastackframe-get-cplusplusexceptionhandling.md) metoda.  
  
## <a name="see-also"></a>Viz také  
 [Idiastackframe –](../../debugger/debug-interface-access/idiastackframe.md)   
 [IDiaStackFrame::get_cplusplusExceptionHandling](../../debugger/debug-interface-access/idiastackframe-get-cplusplusexceptionhandling.md)