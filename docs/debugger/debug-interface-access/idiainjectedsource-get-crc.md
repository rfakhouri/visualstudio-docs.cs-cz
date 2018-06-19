---
title: Idiainjectedsource::get_crc – | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaInjectedSource::get_crc method
ms.assetid: 2ecdda93-950e-40d6-b79b-4ae3c55b6cfc
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: aa3aba392769465b03aecafc7e135a15e748879e
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/18/2018
ms.locfileid: "31467164"
---
# <a name="idiainjectedsourcegetcrc"></a>IDiaInjectedSource::get_crc
Načte kontrolu cyklické redundance (CRC) vypočítaných z bajtů zdrojového kódu.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT get_crc (   
   DWORD* pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pRetVal`  
 [out] Vrátí kontrolní součet vypočítaných z bajtů zdrojového kódu.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`. Vrátí `S_FALSE` -li tato vlastnost není podporována. Jinak vrátí kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [IDiaInjectedSource](../../debugger/debug-interface-access/idiainjectedsource.md)