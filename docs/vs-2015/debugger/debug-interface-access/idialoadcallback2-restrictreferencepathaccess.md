---
title: Idialoadcallback2::restrictreferencepathaccess – | Dokumentace Microsoftu
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- IDiaLoadCallback2::RestrictReferencePathAccess method
ms.assetid: e20cb45c-0360-4ff0-a92c-b1b6f76d6e85
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 61e3a7735760a74eb81f94a86ffd4de3329eb355
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/12/2018
ms.locfileid: "49260101"
---
# <a name="idialoadcallback2restrictreferencepathaccess"></a>IDiaLoadCallback2::RestrictReferencePathAccess
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Určuje, jestli hledá soubor PDB je povolený v cestě, kde je umístěn soubor .exe.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT RestrictReferencePathAccess();  
```  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Žádné jiné než návratový kód `S_OK` zabránit najít soubor .pdb v cestě, kde je umístěn soubor .exe.  
  
## <a name="see-also"></a>Viz také  
 [IDiaLoadCallback2](../../debugger/debug-interface-access/idialoadcallback2.md)



