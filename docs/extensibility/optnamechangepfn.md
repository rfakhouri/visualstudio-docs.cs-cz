---
title: OPTNAMECHANGEPFN | Dokumentace Microsoftu
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- OPTNAMECHANGEPFN
helpviewer_keywords:
- OPTNAMECHANGEPFN callback function
ms.assetid: 147303f3-c7f1-438a-81b7-db891ea3d076
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 083b91dd44101f387c89e2313dba3ffb9a9ee737
ms.sourcegitcommit: 06db1892fff22572f0b0a11994dc547c2b7e2a48
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/08/2018
ms.locfileid: "39636513"
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
 [Sccsetoption –](../extensibility/sccsetoption-function.md)