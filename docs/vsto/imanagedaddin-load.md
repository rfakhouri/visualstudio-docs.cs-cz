---
title: IManagedAddin::Load | Microsoft Docs
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
ms.openlocfilehash: 545560c5f02437925c2f93e9c6dc3113e1cddd0b
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="imanagedaddinload"></a>IManagedAddin::Load
  Volá se při načtení spravované Add-in VSTO.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT Load([in] BSTR bstrManifestURL,   
             [in] IDispatch *pdispApplication);  
```  
  
#### <a name="parameters"></a>Parametry  
  
|Parametr|Popis|  
|---------------|-----------------|  
|*bstrManifestURL*|Úplná cesta manifestu pro doplňku VSTO.|  
|*pdispApplication*|Ukazatel IDispatch, který představuje hostitelskou aplikaci, která je načítání doplňku VSTO.|  
  
## <a name="return-value"></a>Návratová hodnota  
 Hodnota HRESULT, která určuje, zda metoda byla úspěšně dokončena.  
  
## <a name="remarks"></a>Poznámky  
 Manifest je soubor (obvykle soubor XML), který poskytuje informace, které se používají pro načtení doplňku VSTO. Manifest můžete například zadat umístění doplňku VSTO sestavení a třída vstupní bod pro vytvoření instance při načítání doplňku VSTO.  
  
 *BstrManifestURL* parametr obsahuje hodnotu `Manifest` položky v rámci HKEY_CURRENT_USER\Software\Microsoft\Office\\*\<název aplikace >*\Addins\\*\<ID doplněk >* klíč registru pro doplňku VSTO. Další informace najdete v tématu [imanagedaddin – rozhraní](../vsto/imanagedaddin-interface.md).  
  
 Implementace [IManagedAddIn::Load](../vsto/imanagedaddin-load.md) metoda k provádění úloh, jako je například konfigurace zásad domény a zabezpečení aplikací pro VSTO doplněk, který je právě načítán.  
  
## <a name="see-also"></a>Viz také  
 [Imanagedaddin – rozhraní](../vsto/imanagedaddin-interface.md)   
 [IManagedAddin::Unload](../vsto/imanagedaddin-unload.md)  
  
  