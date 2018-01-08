---
title: "Idialinenumber::get_compilandid – | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaLineNumber::get_compilandId method
ms.assetid: 2cd6f551-8091-47c7-803f-3f79a766a211
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: b47a5faa6da14977a7dfb28810cfe273e09105c0
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idialinenumbergetcompilandid"></a>IDiaLineNumber::get_compilandId
Načte jedinečný identifikátor kompilace, která podílí tohoto řádku.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT get_compilandId (   
   DWORD* pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pRetVal`  
 [out] Vrátí `DWORD` obsahující jedinečný identifikátor pro kompilace, která podílí tohoto řádku.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`. Vrátí `S_FALSE` -li tato vlastnost není podporována. Jinak vrátí kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [IDiaLineNumber](../../debugger/debug-interface-access/idialinenumber.md)