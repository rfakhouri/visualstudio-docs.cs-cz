---
title: "Kopírování (zachytávání prostřednictvím kódu programu) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 30ec235a-0abb-44b9-8852-61bc9e67ce22
caps.latest.revision: "4"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a0b8cb397afd4f1ba58dca30b4314471b4647576
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="copy-programmatic-capture"></a>Copy (zachytávání prostřednictvím kódu programu)
Zkopíruje obsah souboru protokolu (.vsglog) active grafiky do nového souboru.  
  
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
 Pokud chcete zkopírovat grafických informací do nového souboru, musí již zachycení některé grafických informací; jinak nedojde k žádné akci.