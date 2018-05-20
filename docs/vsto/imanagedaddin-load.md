---
title: IManagedAddin::Load
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords: ''
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: b5f8e94ebcd0aec8e17cac8d651017ed1565d2ec
ms.sourcegitcommit: 209c2c068ff0975994ed892b62aa9b834a7f6077
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/17/2018
---
# <a name="imanagedaddinload"></a>IManagedAddin::Load
  Volá se při načtení spravované Add-in VSTO.  
  
## <a name="syntax"></a>Syntaxe  
  
```c++
HRESULT Load([in] BSTR bstrManifestURL,   
             [in] IDispatch *pdispApplication);  
```  
  
### <a name="parameters"></a>Parametry  
  
|Parametr|Popis|  
|---------------|-----------------|  
|*bstrManifestURL*|Úplná cesta manifestu pro doplňku VSTO.|  
|*pdispApplication*|Ukazatel IDispatch, který představuje hostitelskou aplikaci, která je načítání doplňku VSTO.|  
  
## <a name="return-value"></a>Návratová hodnota  
 Hodnota HRESULT, která určuje, zda metoda byla úspěšně dokončena.  
  
## <a name="remarks"></a>Poznámky  
 Manifest je soubor (obvykle soubor XML), který poskytuje informace, které se používají pro načtení doplňku VSTO. Manifest můžete například zadat umístění doplňku VSTO sestavení a třída vstupní bod pro vytvoření instance při načítání doplňku VSTO.  
  
 *BstrManifestURL* parametr obsahuje hodnotu `Manifest` položka v části **HKEY_CURRENT_USER\Software\Microsoft\Office\\_\<název aplikace >_ \Addins\\_\<ID doplněk >_**  klíč registru pro doplňku VSTO. Další informace najdete v tématu [imanagedaddin – rozhraní](../vsto/imanagedaddin-interface.md).  
  
 Implementace [IManagedAddIn::Load](../vsto/imanagedaddin-load.md) metoda k provádění úloh, jako je například konfigurace zásad domény a zabezpečení aplikací pro VSTO doplněk, který je právě načítán.  
  
## <a name="see-also"></a>Viz také  
 [Imanagedaddin – rozhraní](../vsto/imanagedaddin-interface.md)   
 [IManagedAddin::Unload](../vsto/imanagedaddin-unload.md)  
  
  