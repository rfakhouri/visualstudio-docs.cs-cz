---
title: Copy (zachytávání prostřednictvím kódu programu) | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 30ec235a-0abb-44b9-8852-61bc9e67ce22
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: aab2b18c8c349211f4b5bd26b055d6ee5b65f0c6
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53990945"
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