---
title: Idiainjectedsource::get_virtualfilename – | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaInjectedSource::get_virtualFilename method
ms.assetid: b9977075-8fd1-4b11-bfff-d87e9f2586dc
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b82a1cf2c998a141d52af3d996ee7c0763f56992
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/18/2018
ms.locfileid: "31467765"
---
# <a name="idiainjectedsourcegetvirtualfilename"></a>IDiaInjectedSource::get_virtualFilename
Načte název přidělený nepocházející ze souborů zdrojového kódu; To znamená, kód, který byl vložit.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT get_virtualFilename (   
   BSTR* pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pRetVal`  
 [out] Vrací název zadané vloženého nepocházející ze souborů zdrojového kódu.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`. Vrátí `S_FALSE` -li tato vlastnost není podporována. Jinak vrátí kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [IDiaInjectedSource](../../debugger/debug-interface-access/idiainjectedsource.md)