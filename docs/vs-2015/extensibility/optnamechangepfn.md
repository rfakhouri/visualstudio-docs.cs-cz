---
title: OPTNAMECHANGEPFN | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- OPTNAMECHANGEPFN
helpviewer_keywords:
- OPTNAMECHANGEPFN callback function
ms.assetid: 147303f3-c7f1-438a-81b7-db891ea3d076
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: f729e00805fa1c73fe1e64197788dd31f2a2a41d
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42629834"
---
# <a name="optnamechangepfn"></a>OPTNAMECHANGEPFN
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [OPTNAMECHANGEPFN](https://docs.microsoft.com/visualstudio/extensibility/optnamechangepfn).  
  
Toto je zadána ve volání funkce zpětného volání [sccsetoption –](../extensibility/sccsetoption-function.md) (pomocí možnosti `SCC_OPT_NAMECHANGEPFN`) a slouží ke komunikaci název změny správy zdrojového kódu modulu plug-in zpět do integrovaného vývojového prostředí.  
  
## <a name="signature"></a>podpis  
  
```cpp#  
typedef void (*OPTNAMECHANGEPFN)(  
   LPVOID pvCallerData,  
   LPCSTR pszOldName,  
   LPCSTR pszNewName  
);  
```  
  
## <a name="parameters"></a>Parametry  
 pvCallerData  
 [in] Zadanou v předchozím volání hodnotu uživatele [sccsetoption –](../extensibility/sccsetoption-function.md) (pomocí možnosti `SCC_OPT_USERDATA`).  
  
 pszOldName  
 [in] Původní název souboru.  
  
 pszNewName  
 [in] Název souboru se přejmenoval na.  
  
## <a name="return-value"></a>Návratová hodnota  
 Žádné  
  
## <a name="remarks"></a>Poznámky  
 Pokud je soubor přejmenován při operaci správy zdrojových kódů, může upozornit modul plug-in správy zdrojového kódu rozhraní IDE o změnu názvu prostřednictvím tohoto zpětného volání.  
  
 Pokud prostředí IDE nepodporuje toto zpětné volání, nebude volat [sccsetoption –](../extensibility/sccsetoption-function.md) k jeho zadání. Pokud modul plug-in nepodporuje toto zpětné volání, vrátí `SCC_E_OPNOTSUPPORTED` z `SccSetOption` fungovat v případě, že rozhraní IDE, pokusí se nastavit zpětného volání.  
  
## <a name="see-also"></a>Viz také  
 [Funkce zpětného volání implementované integrovaným vývojovým prostředím](../extensibility/callback-functions-implemented-by-the-ide.md)   
 [Sccsetoption –](../extensibility/sccsetoption-function.md)

