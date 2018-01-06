---
title: IManagedAddin::Load | Microsoft Docs
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords: 
ms.assetid: 3faf9312-8ab4-4960-b2e7-8ca9859a3dcf
caps.latest.revision: "9"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 91a2909d407dbdc7629e189585333a3e4702483d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
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
  
  