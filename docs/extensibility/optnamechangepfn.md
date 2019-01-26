---
title: OPTNAMECHANGEPFN | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- OPTNAMECHANGEPFN
helpviewer_keywords:
- OPTNAMECHANGEPFN callback function
ms.assetid: 147303f3-c7f1-438a-81b7-db891ea3d076
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 31f46f8b392d5d3b37aed91a6867d80835be0d23
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54963915"
---
# <a name="optnamechangepfn"></a>OPTNAMECHANGEPFN
Toto je zadána ve volání funkce zpětného volání [sccsetoption –](../extensibility/sccsetoption-function.md) (pomocí možnosti `SCC_OPT_NAMECHANGEPFN`) a slouží ke komunikaci název změny správy zdrojového kódu modulu plug-in zpět do integrovaného vývojového prostředí.  
  
## <a name="signature"></a>podpis  
  
```cpp  
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
  
## <a name="see-also"></a>Viz také:  
 [Funkce zpětného volání implementované integrovaným vývojovým prostředím](../extensibility/callback-functions-implemented-by-the-ide.md)   
 [SccSetOption](../extensibility/sccsetoption-function.md)