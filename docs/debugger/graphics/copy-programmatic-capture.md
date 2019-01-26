---
title: Copy (zachytávání prostřednictvím kódu programu) | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 30ec235a-0abb-44b9-8852-61bc9e67ce22
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 35558a9ad6a4e7d31103910f3fe71c0a12374c22
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55042250"
---
# <a name="copy-programmatic-capture"></a>Copy (zachytávání prostřednictvím kódu programu)
Zkopíruje obsah aktivní grafiky (.vsglog) protokolu do nového souboru.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
void Copy(  
  wchar_t const * szNewVSGLog  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `szNewVSGLog`  
 Název souboru nový soubor protokolu grafiky.  
  
## <a name="remarks"></a>Poznámky  
 Kopírování informací grafiky na nový soubor, musí již zaznamenáte některé informace grafiky; v opačném případě nic se nestane.