---
title: Idialoadcallback2::restrictreferencepathaccess – | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
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
ms.openlocfilehash: 3a2ba01723edae02034c90bde32e49c9e4bf5fc6
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42628499"
---
# <a name="idialoadcallback2restrictreferencepathaccess"></a>IDiaLoadCallback2::RestrictReferencePathAccess
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [idialoadcallback2::restrictreferencepathaccess –](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idialoadcallback2-restrictreferencepathaccess).  
  
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



